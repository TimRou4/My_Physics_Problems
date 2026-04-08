<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Wave Sources - Superposition</title>
  <style>
    :root {
      --bg: #0e1120;
      --panel: #171b2e;
      --soft: #222845;
      --line: #333a5c;
      --text: #eef2ff;
      --muted: #aab2d6;
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
      flex-wrap: wrap;
      gap: 8px;
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
    <h1>Wave Sources - Superposition</h1>
    <p class="small">
      Left-click inside the field to add a source. Right-click near a source to remove it.
      The displacement is computed as
      <code>u(r,t) = A / |r-r₀|^α · sin(k|r-r₀| - ωt)</code>
      and the total field is the sum over all sources.
    </p>

    <div class="layout">
      <div class="panel stack">
        <div class="row">
          <label for="alpha">Attenuation exponent α</label>
          <strong id="alphaVal">1.00</strong>
        </div>
        <input id="alpha" type="range" min="0" max="2" step="0.01" value="1" />

        <div class="row">
          <label for="lambda">Wavelength λ (pixels)</label>
          <strong id="lambdaVal">60</strong>
        </div>
        <input id="lambda" type="range" min="20" max="120" step="1" value="60" />

        <div class="row">
          <label for="amp">Amplitude A</label>
          <strong id="ampVal">120</strong>
        </div>
        <input id="amp" type="range" min="20" max="200" step="1" value="120" />

        <div class="row">
          <label for="freq">Frequency f (Hz)</label>
          <strong id="freqVal">1.20</strong>
        </div>
        <input id="freq" type="range" min="0.2" max="3" step="0.01" value="1.2" />

        <div class="btns">
          <button id="pauseBtn">Pause</button>
          <button id="clearBtn">Clear all sources</button>
          <button id="demoBtn">Load demo sources</button>
        </div>

        <div class="small" id="info"></div>
      </div>

      <div class="panel">
        <canvas id="field" width="820" height="520"></canvas>
      </div>
    </div>
  </div>

  <script>
    const canvas = document.getElementById("field");
    const ctx = canvas.getContext("2d");
    const W = canvas.width;
    const H = canvas.height;

    const alphaSlider = document.getElementById("alpha");
    const lambdaSlider = document.getElementById("lambda");
    const ampSlider = document.getElementById("amp");
    const freqSlider = document.getElementById("freq");

    const alphaVal = document.getElementById("alphaVal");
    const lambdaVal = document.getElementById("lambdaVal");
    const ampVal = document.getElementById("ampVal");
    const freqVal = document.getElementById("freqVal");
    const info = document.getElementById("info");

    const pauseBtn = document.getElementById("pauseBtn");
    const clearBtn = document.getElementById("clearBtn");
    const demoBtn = document.getElementById("demoBtn");

    const lowW = 205;
    const lowH = 130;
    const off = document.createElement("canvas");
    off.width = lowW;
    off.height = lowH;
    const offCtx = off.getContext("2d");
    let image = offCtx.createImageData(lowW, lowH);

    let paused = false;
    let sources = [];

    function syncLabels() {
      alphaVal.textContent = Number(alphaSlider.value).toFixed(2);
      lambdaVal.textContent = lambdaSlider.value;
      ampVal.textContent = ampSlider.value;
      freqVal.textContent = Number(freqSlider.value).toFixed(2);

      info.innerHTML = `
        Sources: <strong>${sources.length}</strong><br />
        The field is rendered on a coarse grid and scaled for speed.<br />
        Set <code>α = 0</code> for no distance attenuation.
      `;
    }

    function addDemo() {
      sources = [
        { x: W * 0.30, y: H * 0.35 },
        { x: W * 0.55, y: H * 0.55 },
        { x: W * 0.72, y: H * 0.30 }
      ];
      syncLabels();
    }

    function screenToCanvas(e) {
      const rect = canvas.getBoundingClientRect();
      return {
        x: (e.clientX - rect.left) * (W / rect.width),
        y: (e.clientY - rect.top) * (H / rect.height)
      };
    }

    canvas.addEventListener("click", (e) => {
      const p = screenToCanvas(e);
      sources.push({ x: p.x, y: p.y });
      syncLabels();
    });

    canvas.addEventListener("contextmenu", (e) => {
      e.preventDefault();
      if (!sources.length) return;
      const p = screenToCanvas(e);
      let best = 0;
      let bestDist = Infinity;
      sources.forEach((s, i) => {
        const d = Math.hypot(p.x - s.x, p.y - s.y);
        if (d < bestDist) {
          bestDist = d;
          best = i;
        }
      });
      if (bestDist < 30) {
        sources.splice(best, 1);
        syncLabels();
      }
    });

    [alphaSlider, lambdaSlider, ampSlider, freqSlider].forEach(el => {
      el.addEventListener("input", syncLabels);
    });

    pauseBtn.addEventListener("click", () => {
      paused = !paused;
      pauseBtn.textContent = paused ? "Play" : "Pause";
    });

    clearBtn.addEventListener("click", () => {
      sources = [];
      syncLabels();
    });

    demoBtn.addEventListener("click", addDemo);

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

    function renderField(t) {
      const alpha = parseFloat(alphaSlider.value);
      const lambda = parseFloat(lambdaSlider.value);
      const A = parseFloat(ampSlider.value);
      const f = parseFloat(freqSlider.value);

      const k = 2 * Math.PI / lambda;
      const omega = 2 * Math.PI * f;
      const data = image.data;

      for (let j = 0; j < lowH; j++) {
        for (let i = 0; i < lowW; i++) {
          const x = (i + 0.5) * W / lowW;
          const y = (j + 0.5) * H / lowH;

          let u = 0;

          for (const s of sources) {
            const dx = x - s.x;
            const dy = y - s.y;
            const r = Math.hypot(dx, dy);
            const rr = Math.max(r, 2);

            let scale = 1;
            if (alpha > 0) {
              scale = 1 / Math.pow(rr, alpha);
            }

            u += A * scale * Math.sin(k * r - omega * t);
          }

          const norm = (2 / Math.PI) * Math.atan(u * 0.12);
          const [rCol, gCol, bCol] = colorMap(norm);
          const p = 4 * (j * lowW + i);

          data[p] = rCol;
          data[p + 1] = gCol;
          data[p + 2] = bCol;
          data[p + 3] = 255;
        }
      }

      offCtx.putImageData(image, 0, 0);
      ctx.clearRect(0, 0, W, H);
      ctx.drawImage(off, 0, 0, W, H);

      ctx.strokeStyle = "rgba(255,255,255,0.85)";
      ctx.fillStyle = "rgba(0,0,0,0.85)";
      ctx.lineWidth = 2;

      for (const s of sources) {
        ctx.beginPath();
        ctx.arc(s.x, s.y, 6, 0, Math.PI * 2);
        ctx.fill();
        ctx.stroke();
      }

      ctx.fillStyle = "rgba(255,255,255,0.9)";
      ctx.font = "14px Arial";
      ctx.fillText("Left-click: add source", 14, 24);
      ctx.fillText("Right-click: remove nearest source", 14, 44);
    }

    function loop(now) {
      const t = now / 1000;
      renderField(paused ? 0 : t);
      requestAnimationFrame(loop);
    }

    addDemo();
    syncLabels();
    requestAnimationFrame(loop);
  </script>
</body>
</html>
