<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Two-Slit Interference</title>
  <style>
    :root {
      --bg: #0e1222;
      --panel: #171c31;
      --soft: #222844;
      --line: #333b5f;
      --text: #eef2ff;
      --muted: #a8b0d8;
    }
    * { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: Arial, Helvetica, sans-serif;
      background: var(--bg);
      color: var(--text);
    }
    .wrap {
      max-width: 1200px;
      margin: 0 auto;
      padding: 20px;
    }
    .layout {
      display: grid;
      grid-template-columns: 320px 1fr;
      gap: 18px;
    }
    .panel {
      background: var(--panel);
      border: 1px solid var(--line);
      border-radius: 14px;
      padding: 16px;
    }
    .stack {
      display: grid;
      gap: 12px;
    }
    .row {
      display: grid;
      grid-template-columns: 1fr auto;
      gap: 10px;
      align-items: center;
    }
    input[type="range"] {
      width: 100%;
    }
    button {
      border: 1px solid var(--line);
      background: var(--soft);
      color: var(--text);
      padding: 10px 12px;
      border-radius: 10px;
      cursor: pointer;
    }
    button:hover {
      border-color: #78afff;
    }
    .btns {
      display: flex;
      gap: 8px;
      flex-wrap: wrap;
    }
    canvas {
      display: block;
      width: 100%;
      background: #0b1020;
      border: 1px solid var(--line);
      border-radius: 14px;
      image-rendering: pixelated;
    }
    .small {
      color: var(--muted);
      font-size: 14px;
      line-height: 1.5;
    }
    code {
      color: #bfe0ff;
    }
    @media (max-width: 960px) {
      .layout {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>
  <div class="wrap">
    <h1>Young's Two-Slit Interference</h1>
    <p class="small">
      The field is computed from two coherent point sources located at the slit positions.
      The animated color field shows the instantaneous displacement.
      The bright vertical strip on the right shows the time-averaged interference intensity on the screen.
    </p>

    <div class="layout">
      <div class="panel stack">
        <div class="row">
          <label for="d">Slit distance d (pixels)</label>
          <strong id="dVal">90</strong>
        </div>
        <input id="d" type="range" min="20" max="220" step="1" value="90" />

        <div class="row">
          <label for="lambda">Wavelength λ (pixels)</label>
          <strong id="lambdaVal">48</strong>
        </div>
        <input id="lambda" type="range" min="18" max="110" step="1" value="48" />

        <div class="row">
          <label for="freq">Frequency f (Hz)</label>
          <strong id="freqVal">1.20</strong>
        </div>
        <input id="freq" type="range" min="0.2" max="3" step="0.01" value="1.2" />

        <div class="btns">
          <button id="pauseBtn">Pause</button>
          <button id="resetBtn">Reset defaults</button>
        </div>

        <div class="small" id="info"></div>
      </div>

      <div class="panel">
        <canvas id="field" width="860" height="520"></canvas>
      </div>
    </div>
  </div>

  <script>
    const canvas = document.getElementById("field");
    const ctx = canvas.getContext("2d");
    const W = canvas.width;
    const H = canvas.height;

    const dSlider = document.getElementById("d");
    const lambdaSlider = document.getElementById("lambda");
    const freqSlider = document.getElementById("freq");

    const dVal = document.getElementById("dVal");
    const lambdaVal = document.getElementById("lambdaVal");
    const freqVal = document.getElementById("freqVal");
    const info = document.getElementById("info");

    const pauseBtn = document.getElementById("pauseBtn");
    const resetBtn = document.getElementById("resetBtn");

    const lowW = 215;
    const lowH = 130;
    const off = document.createElement("canvas");
    off.width = lowW;
    off.height = lowH;
    const offCtx = off.getContext("2d");
    let image = offCtx.createImageData(lowW, lowH);

    const barrierX = 120;
    const slitRadius = 9;
    const screenX = W - 42;
    const intensityWidth = 18;

    let paused = false;
    let intensity = new Array(H).fill(0);

    function syncLabels() {
      dVal.textContent = dSlider.value;
      lambdaVal.textContent = lambdaSlider.value;
      freqVal.textContent = Number(freqSlider.value).toFixed(2);

      const d = parseFloat(dSlider.value);
      const lambda = parseFloat(lambdaSlider.value);
      info.innerHTML = `
        Current ratio: <code>d / λ = ${(d / lambda).toFixed(2)}</code><br />
        Larger <code>d</code> usually gives more closely spaced fringes.<br />
        Larger <code>λ</code> usually gives wider fringe spacing.
      `;
    }

    function getSources() {
      const d = parseFloat(dSlider.value);
      return {
        r1: { x: barrierX, y: H / 2 - d / 2 },
        r2: { x: barrierX, y: H / 2 + d / 2 }
      };
    }

    function colorMap(norm) {
      const c = Math.max(-1, Math.min(1, norm));
      if (c >= 0) {
        return [
          255,
          Math.round(255 * (1 - c)),
          Math.round(255 * (1 - c))
        ];
      }
      return [
        Math.round(255 * (1 + c)),
        Math.round(255 * (1 + c)),
        255
      ];
    }

    function recomputeIntensity() {
      const lambda = parseFloat(lambdaSlider.value);
      const k = 2 * Math.PI / lambda;
      const { r1, r2 } = getSources();

      let maxI = 0;
      for (let y = 0; y < H; y++) {
        const rr1 = Math.max(Math.hypot(screenX - r1.x, y - r1.y), 4);
        const rr2 = Math.max(Math.hypot(screenX - r2.x, y - r2.y), 4);

        const I = 1 / (rr1 * rr1) + 1 / (rr2 * rr2) + 2 * Math.cos(k * (rr1 - rr2)) / (rr1 * rr2);
        intensity[y] = Math.max(0, I);
        if (intensity[y] > maxI) maxI = intensity[y];
      }

      if (maxI > 0) {
        for (let y = 0; y < H; y++) {
          intensity[y] /= maxI;
        }
      }
    }

    function drawBarrier(r1, r2) {
      ctx.fillStyle = "rgba(15, 18, 30, 0.96)";
      ctx.fillRect(barrierX - 4, 0, 8, H);

      ctx.clearRect(barrierX - 4, r1.y - slitRadius, 8, slitRadius * 2);
      ctx.clearRect(barrierX - 4, r2.y - slitRadius, 8, slitRadius * 2);

      ctx.strokeStyle = "rgba(255,255,255,0.9)";
      ctx.lineWidth = 2;
      ctx.beginPath();
      ctx.arc(r1.x, r1.y, 4, 0, Math.PI * 2);
      ctx.arc(r2.x, r2.y, 4, 0, Math.PI * 2);
      ctx.stroke();

      ctx.fillStyle = "rgba(255,255,255,0.85)";
      ctx.font = "14px Arial";
      ctx.fillText("Barrier", barrierX - 22, 20);
      ctx.fillText("Screen", screenX - 10, 20);
    }

    function drawIntensityScreen() {
      for (let y = 0; y < H; y++) {
        const v = Math.pow(intensity[y], 0.45);
        const c = Math.round(255 * v);
        ctx.fillStyle = `rgb(${c}, ${c}, ${c})`;
        ctx.fillRect(screenX, y, intensityWidth, 1);
      }

      ctx.strokeStyle = "rgba(255,255,255,0.7)";
      ctx.strokeRect(screenX, 0, intensityWidth, H);
    }

    function renderField(t) {
      const lambda = parseFloat(lambdaSlider.value);
      const f = parseFloat(freqSlider.value);

      const k = 2 * Math.PI / lambda;
      const omega = 2 * Math.PI * f;
      const { r1, r2 } = getSources();

      const data = image.data;

      for (let j = 0; j < lowH; j++) {
        for (let i = 0; i < lowW; i++) {
          const x = (i + 0.5) * W / lowW;
          const y = (j + 0.5) * H / lowH;
          const p = 4 * (j * lowW + i);

          const inBarrier =
            x >= barrierX - 4 &&
            x <= barrierX + 4 &&
            Math.abs(y - r1.y) > slitRadius &&
            Math.abs(y - r2.y) > slitRadius;

          if (inBarrier) {
            data[p] = 18;
            data[p + 1] = 22;
            data[p + 2] = 38;
            data[p + 3] = 255;
            continue;
          }

          const rr1 = Math.max(Math.hypot(x - r1.x, y - r1.y), 4);
          const rr2 = Math.max(Math.hypot(x - r2.x, y - r2.y), 4);

          const u =
            (1 / rr1) * Math.sin(k * rr1 - omega * t) +
            (1 / rr2) * Math.sin(k * rr2 - omega * t);

          const norm = (2 / Math.PI) * Math.atan(u * 18);
          const [rCol, gCol, bCol] = colorMap(norm);

          data[p] = rCol;
          data[p + 1] = gCol;
          data[p + 2] = bCol;
          data[p + 3] = 255;
        }
      }

      offCtx.putImageData(image, 0, 0);
      ctx.clearRect(0, 0, W, H);
      ctx.drawImage(off, 0, 0, W, H);

      drawIntensityScreen();
      drawBarrier(r1, r2);

      ctx.fillStyle = "rgba(255,255,255,0.9)";
      ctx.font = "14px Arial";
      ctx.fillText("Two coherent sources at the slit positions", 14, 24);
    }

    [dSlider, lambdaSlider, freqSlider].forEach(el => {
      el.addEventListener("input", () => {
        syncLabels();
        recomputeIntensity();
      });
    });

    pauseBtn.addEventListener("click", () => {
      paused = !paused;
      pauseBtn.textContent = paused ? "Play" : "Pause";
    });

    resetBtn.addEventListener("click", () => {
      dSlider.value = 90;
      lambdaSlider.value = 48;
      freqSlider.value = 1.2;
      syncLabels();
      recomputeIntensity();
    });

    function loop(now) {
      const t = now / 1000;
      renderField(paused ? 0 : t);
      requestAnimationFrame(loop);
    }

    syncLabels();
    recomputeIntensity();
    requestAnimationFrame(loop);
  </script>
</body>
</html>
