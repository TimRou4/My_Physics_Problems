<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Damped Harmonic Oscillator - RK4</title>
  <style>
    :root {
      --bg: #0f1220;
      --panel: #171b2e;
      --soft: #232845;
      --text: #eef1ff;
      --muted: #a8b0d8;
      --accent: #7db6ff;
      --line: #32385c;
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
    h1, h2, h3 {
      margin: 0 0 12px 0;
    }
    .grid {
      display: grid;
      grid-template-columns: 330px 1fr;
      gap: 18px;
    }
    .panel {
      background: var(--panel);
      border: 1px solid var(--line);
      border-radius: 14px;
      padding: 16px;
    }
    .controls {
      display: grid;
      gap: 12px;
    }
    .row {
      display: grid;
      grid-template-columns: 1fr auto;
      gap: 10px;
      align-items: center;
    }
    .stack {
      display: grid;
      gap: 8px;
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
      border-color: var(--accent);
    }
    .btns {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
    }
    .tag {
      display: inline-block;
      padding: 6px 10px;
      border-radius: 999px;
      background: var(--soft);
      border: 1px solid var(--line);
      color: var(--muted);
      font-size: 14px;
    }
    .status {
      padding: 12px;
      background: #12162a;
      border-radius: 12px;
      border: 1px solid var(--line);
      line-height: 1.5;
    }
    .canvas-grid {
      display: grid;
      gap: 18px;
    }
    canvas {
      width: 100%;
      background: #0c1020;
      border: 1px solid var(--line);
      border-radius: 14px;
      display: block;
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
      .grid {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>
  <div class="wrap">
    <h1>Damped Harmonic Oscillator</h1>
    <p class="small">
      Numerical solution of
      <code>m x'' + b x' + k x = 0</code>
      using the fourth-order Runge-Kutta method (RK4).
      The graphs show the displacement history <code>x(t)</code> and the phase portrait <code>(x, v)</code>.
    </p>

    <div class="grid">
      <div class="panel controls">
        <h2>Parameters</h2>

        <div class="status" id="summary"></div>

        <div class="stack">
          <div class="row">
            <label for="bSlider">Damping coefficient b</label>
            <strong id="bValue">0.50</strong>
          </div>
          <input id="bSlider" type="range" min="0" max="4" step="0.01" value="0.5" />
        </div>

        <div class="small">
          Fixed values in this demo:
          <br />
          <code>m = 1</code>, <code>k = 1</code>, <code>x(0) = 1</code>, <code>v(0) = 0</code>
        </div>

        <div class="btns">
          <button id="underBtn">Underdamped</button>
          <button id="criticalBtn">Critical</button>
          <button id="overBtn">Overdamped</button>
          <button id="playBtn">Pause</button>
          <button id="resetBtn">Reset marker</button>
        </div>

        <h3>General solution</h3>
        <div class="small">
          <strong>Underdamped:</strong><br />
          <code>x(t) = e^{-γt}(C₁ cos(ω_d t) + C₂ sin(ω_d t))</code><br />
          where <code>γ = b / (2m)</code> and <code>ω_d = sqrt(k/m - γ²)</code>
          <br /><br />

          <strong>Critically damped:</strong><br />
          <code>x(t) = (C₁ + C₂ t)e^{-ω₀ t}</code><br />
          where <code>ω₀ = sqrt(k/m)</code>
          <br /><br />

          <strong>Overdamped:</strong><br />
          <code>x(t) = C₁ e^{r₁ t} + C₂ e^{r₂ t}</code><br />
          where
          <code>r₁, r₂ = (-b ± sqrt(b² - 4mk)) / (2m)</code>
        </div>

        <h3>Classification</h3>
        <div class="small">
          The critical value is
          <code>b_c = 2 sqrt(mk)</code>.
          For this demo:
          <code>b_c = 2</code>.
          <br /><br />
          - <code>b &lt; 2</code>: underdamped<br />
          - <code>b = 2</code>: critically damped<br />
          - <code>b &gt; 2</code>: overdamped
        </div>
      </div>

      <div class="canvas-grid">
        <div class="panel">
          <h2>Displacement x(t)</h2>
          <canvas id="timeCanvas" width="820" height="320"></canvas>
        </div>

        <div class="panel">
          <h2>Phase portrait</h2>
          <canvas id="phaseCanvas" width="820" height="320"></canvas>
        </div>
      </div>
    </div>
  </div>

  <script>
    const m = 1;
    const k = 1;
    const x0 = 1;
    const v0 = 0;
    const dt = 0.01;
    const T = 24;
    const steps = Math.floor(T / dt);
    const critical = 2 * Math.sqrt(m * k);

    const bSlider = document.getElementById("bSlider");
    const bValue = document.getElementById("bValue");
    const summary = document.getElementById("summary");
    const playBtn = document.getElementById("playBtn");
    const resetBtn = document.getElementById("resetBtn");
    const underBtn = document.getElementById("underBtn");
    const criticalBtn = document.getElementById("criticalBtn");
    const overBtn = document.getElementById("overBtn");

    const timeCanvas = document.getElementById("timeCanvas");
    const phaseCanvas = document.getElementById("phaseCanvas");
    const tctx = timeCanvas.getContext("2d");
    const pctx = phaseCanvas.getContext("2d");

    let trajectory = [];
    let markerIndex = 0;
    let playing = true;
    let lastTime = performance.now();

    function deriv(state, b) {
      return {
        dx: state.v,
        dv: -(b / m) * state.v - (k / m) * state.x
      };
    }

    function rk4Solve(b) {
      const data = [];
      let state = { x: x0, v: v0 };

      for (let i = 0; i <= steps; i++) {
        data.push({
          t: i * dt,
          x: state.x,
          v: state.v
        });

        const k1 = deriv(state, b);
        const k2 = deriv({
          x: state.x + 0.5 * dt * k1.dx,
          v: state.v + 0.5 * dt * k1.dv
        }, b);
        const k3 = deriv({
          x: state.x + 0.5 * dt * k2.dx,
          v: state.v + 0.5 * dt * k2.dv
        }, b);
        const k4 = deriv({
          x: state.x + dt * k3.dx,
          v: state.v + dt * k3.dv
        }, b);

        state = {
          x: state.x + (dt / 6) * (k1.dx + 2 * k2.dx + 2 * k3.dx + k4.dx),
          v: state.v + (dt / 6) * (k1.dv + 2 * k2.dv + 2 * k3.dv + k4.dv)
        };
      }

      return data;
    }

    function classify(b) {
      const eps = 1e-6;
      if (b < critical - eps) return "Underdamped";
      if (Math.abs(b - critical) <= eps) return "Critically damped";
      return "Overdamped";
    }

    function updateSummary(b) {
      const gamma = b / (2 * m);
      const omega0 = Math.sqrt(k / m);
      const cls = classify(b);

      let extra = "";
      if (cls === "Underdamped") {
        const omegaD = Math.sqrt(Math.max(0, omega0 * omega0 - gamma * gamma));
        extra = `Damped angular frequency: ${omegaD.toFixed(4)}`;
      } else if (cls === "Critically damped") {
        extra = "Fastest non-oscillatory return to equilibrium.";
      } else {
        const disc = Math.sqrt(Math.max(0, b * b - 4 * m * k));
        const r1 = (-b + disc) / (2 * m);
        const r2 = (-b - disc) / (2 * m);
        extra = `Real decay rates: r₁ = ${r1.toFixed(4)}, r₂ = ${r2.toFixed(4)}`;
      }

      summary.innerHTML = `
        <strong>Current case:</strong> ${cls}<br />
        <strong>Critical damping:</strong> b<sub>c</sub> = ${critical.toFixed(2)}<br />
        <strong>Current b:</strong> ${b.toFixed(2)}<br />
        <strong>γ = b / (2m):</strong> ${gamma.toFixed(4)}<br />
        <strong>ω₀ = sqrt(k/m):</strong> ${omega0.toFixed(4)}<br />
        <strong>Observation:</strong> ${extra}
      `;
    }

    function niceRange(min, max) {
      if (min === max) {
        min -= 1;
        max += 1;
      }
      const pad = 0.12 * (max - min);
      return [min - pad, max + pad];
    }

    function drawAxes(ctx, w, h, padding, xLabel, yLabel) {
      ctx.strokeStyle = "#32385c";
      ctx.lineWidth = 1;
      ctx.beginPath();
      ctx.moveTo(padding, h - padding);
      ctx.lineTo(w - padding, h - padding);
      ctx.moveTo(padding, padding);
      ctx.lineTo(padding, h - padding);
      ctx.stroke();

      ctx.fillStyle = "#a8b0d8";
      ctx.font = "14px Arial";
      ctx.fillText(xLabel, w - padding - 18, h - padding + 24);
      ctx.fillText(yLabel, padding - 18, padding - 10);
    }

    function drawTimeGraph(data, idx) {
      const w = timeCanvas.width;
      const h = timeCanvas.height;
      const padding = 50;

      tctx.clearRect(0, 0, w, h);
      drawAxes(tctx, w, h, padding, "t", "x");

      const xs = data.map(p => p.t);
      const ys = data.map(p => p.x);
      const [yMin, yMax] = niceRange(Math.min(...ys), Math.max(...ys));

      const xToPx = x => padding + (x / T) * (w - 2 * padding);
      const yToPx = y => h - padding - ((y - yMin) / (yMax - yMin)) * (h - 2 * padding);

      tctx.strokeStyle = "#7db6ff";
      tctx.lineWidth = 2;
      tctx.beginPath();
      data.forEach((p, i) => {
        const px = xToPx(p.t);
        const py = yToPx(p.x);
        if (i === 0) tctx.moveTo(px, py);
        else tctx.lineTo(px, py);
      });
      tctx.stroke();

      const current = data[Math.min(idx, data.length - 1)];
      const mx = xToPx(current.t);
      const my = yToPx(current.x);

      tctx.fillStyle = "#ffffff";
      tctx.beginPath();
      tctx.arc(mx, my, 5, 0, Math.PI * 2);
      tctx.fill();

      tctx.fillStyle = "#a8b0d8";
      tctx.font = "13px Arial";
      tctx.fillText(`x range: [${yMin.toFixed(2)}, ${yMax.toFixed(2)}]`, padding, 24);
      tctx.fillText(`marker: t = ${current.t.toFixed(2)} s, x = ${current.x.toFixed(3)}`, padding, h - 16);
    }

    function drawPhaseGraph(data, idx) {
      const w = phaseCanvas.width;
      const h = phaseCanvas.height;
      const padding = 50;

      pctx.clearRect(0, 0, w, h);
      drawAxes(pctx, w, h, padding, "x", "v");

      const xs = data.map(p => p.x);
      const vs = data.map(p => p.v);
      const [xMin, xMax] = niceRange(Math.min(...xs), Math.max(...xs));
      const [vMin, vMax] = niceRange(Math.min(...vs), Math.max(...vs));

      const xToPx = x => padding + ((x - xMin) / (xMax - xMin)) * (w - 2 * padding);
      const yToPx = v => h - padding - ((v - vMin) / (vMax - vMin)) * (h - 2 * padding);

      pctx.strokeStyle = "#7db6ff";
      pctx.lineWidth = 2;
      pctx.beginPath();
      data.forEach((p, i) => {
        const px = xToPx(p.x);
        const py = yToPx(p.v);
        if (i === 0) pctx.moveTo(px, py);
        else pctx.lineTo(px, py);
      });
      pctx.stroke();

      const current = data[Math.min(idx, data.length - 1)];
      const mx = xToPx(current.x);
      const my = yToPx(current.v);

      pctx.fillStyle = "#ffffff";
      pctx.beginPath();
      pctx.arc(mx, my, 5, 0, Math.PI * 2);
      pctx.fill();

      pctx.fillStyle = "#a8b0d8";
      pctx.font = "13px Arial";
      pctx.fillText(`marker: x = ${current.x.toFixed(3)}, v = ${current.v.toFixed(3)}`, padding, h - 16);
    }

    function recompute() {
      const b = parseFloat(bSlider.value);
      bValue.textContent = b.toFixed(2);
      trajectory = rk4Solve(b);
      updateSummary(b);
      drawTimeGraph(trajectory, markerIndex);
      drawPhaseGraph(trajectory, markerIndex);
    }

    function resetMarker() {
      markerIndex = 0;
      drawTimeGraph(trajectory, markerIndex);
      drawPhaseGraph(trajectory, markerIndex);
    }

    bSlider.addEventListener("input", () => {
      resetMarker();
      recompute();
    });

    playBtn.addEventListener("click", () => {
      playing = !playing;
      playBtn.textContent = playing ? "Pause" : "Play";
    });

    resetBtn.addEventListener("click", resetMarker);

    underBtn.addEventListener("click", () => {
      bSlider.value = "0.50";
      resetMarker();
      recompute();
    });

    criticalBtn.addEventListener("click", () => {
      bSlider.value = critical.toFixed(2);
      resetMarker();
      recompute();
    });

    overBtn.addEventListener("click", () => {
      bSlider.value = "3.00";
      resetMarker();
      recompute();
    });

    function animate(now) {
      const delta = (now - lastTime) / 1000;
      lastTime = now;

      if (playing && trajectory.length > 1) {
        markerIndex += Math.max(1, Math.floor(delta / dt * 0.75));
        if (markerIndex >= trajectory.length) markerIndex = 0;
        drawTimeGraph(trajectory, markerIndex);
        drawPhaseGraph(trajectory, markerIndex);
      }

      requestAnimationFrame(animate);
    }

    recompute();
    requestAnimationFrame(animate);
  </script>
</body>
</html>
