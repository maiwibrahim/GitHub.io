<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>GLSL Hero — Mai W. Ibrahim</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=Space+Mono:wght@400;700&family=Lora:ital,wght@0,400;0,500;1,400&display=swap');

:root {
  --teal: #0dbfb4;
  --pink: #ff3d82;
  --yellow-soft: #f9edaa;
  --hero-bg: #0b1b2e;
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

body {
  background: var(--hero-bg);
  overflow: hidden;
  font-family: 'Lora', Georgia, serif;
  width: 100vw; height: 100vh;
}

/* Three individual shader canvases — one per avatar */
.shader-canvas {
  position: absolute;
  border-radius: 50%;
  z-index: 1;
  pointer-events: none;
  opacity: 0;
  transition: opacity 1.6s ease;
}

/* NAV */
.site-nav {
  position: fixed; top: 0; left: 0; right: 0; z-index: 99;
  background: rgba(11,27,46,.88); backdrop-filter: blur(14px);
  display: flex; gap: 2rem; align-items: center; justify-content: flex-end;
  height: 60px; padding: 0 3rem;
  border-bottom: .5px solid rgba(13,191,180,.18);
}
.site-nav a {
  font-family: 'Space Mono', monospace; font-size: 12px;
  color: #fff; text-decoration: none;
  letter-spacing: .18em; text-transform: uppercase;
}

.hero {
  position: relative; z-index: 2;
  width: 100vw; height: 100vh;
  display: flex; align-items: center;
  padding: 60px 6vw 0;
  pointer-events: none;
}

/* Avatar label groups */
.av-label-group {
  position: absolute;
  display: flex; flex-direction: column;
  align-items: center; gap: 6px;
  z-index: 10;
  opacity: 0;
  animation: labelIn .9s ease forwards;
}
@keyframes labelIn {
  from { opacity: 0; transform: translateY(10px); }
  to   { opacity: 0.42; transform: translateY(0); }
}
.av-label {
  font-family: 'Space Mono', monospace;
  font-size: 9.5px; letter-spacing: .06em;
  background: rgba(0,0,0,.4);
  padding: 2px 8px; border-radius: 2px;
  white-space: nowrap;
}

/* Tags */
.hero-tag {
  position: absolute; z-index: 10;
  opacity: 0; animation: tagIn .7s ease forwards;
}
@keyframes tagIn {
  from { opacity: 0; transform: translateY(8px); }
  to   { opacity: 0.4; transform: translateY(0); }
}
.hero-tag-inner {
  background: rgba(255,255,255,.08);
  border: .5px solid rgba(255,255,255,.2);
  padding: 5px 13px;
  font-family: 'Space Mono', monospace;
  font-size: 11px; color: rgba(255,255,255,.8);
  white-space: nowrap; border-radius: 6px;
  display: inline-flex; align-items: center; gap: 6px;
}

/* Hero content */
.hero-content {
  position: relative; z-index: 10;
  display: flex; flex-direction: column; gap: 14px;
  max-width: 600px; pointer-events: auto;
}
.hero-name {
  font-family: 'DM Serif Display', Georgia, serif;
  font-size: clamp(37px, 6.8vw, 76px);
  font-weight: 400; line-height: .92;
  white-space: nowrap; letter-spacing: -.01em;
}
.hero-name .first { color: var(--yellow-soft); }
.hero-name .rest  { color: #e0f0f8; }
.hero-name em     { font-style: italic; color: rgba(13,191,180,.45); }
.hero-desc {
  font-size: clamp(14px, 2vw, 18px);
  color: #fff; font-style: italic; line-height: 1.6;
}
.hero-btn a {
  font-family: 'Space Mono', monospace; font-size: 11px;
  letter-spacing: .15em; text-transform: uppercase;
  color: #0b1b2e; background: var(--teal);
  padding: 12px 28px; text-decoration: none; display: inline-block;
}

.ui-dots {
  position: absolute; top: 18px; right: 20px;
  display: flex; gap: 5px; z-index: 20;
}
.ui-dots span { width: 6px; height: 6px; border-radius: 50%; }

.version-badge {
  position: fixed; bottom: 20px; left: 50%; transform: translateX(-50%);
  font-family: 'Space Mono', monospace; font-size: 10px;
  letter-spacing: .14em; text-transform: uppercase;
  color: rgba(13,191,180,.5); z-index: 100;
  background: rgba(11,27,46,.7); padding: 6px 16px; border-radius: 20px;
  border: .5px solid rgba(13,191,180,.2);
}
</style>
</head>
<body>

<!-- One WebGL canvas per avatar concept -->
<canvas class="shader-canvas" id="c-intensity"  width="280" height="280"></canvas>
<canvas class="shader-canvas" id="c-extraction" width="280" height="280"></canvas>
<canvas class="shader-canvas" id="c-glitch"     width="280" height="280"></canvas>

<nav class="site-nav">
  <a href="#">About</a>
  <a href="#">Publications</a>
  <a href="#">CV</a>
  <a href="#">Contact</a>
</nav>

<div class="hero">
  <div class="ui-dots">
    <span style="background:#0dbfb4;"></span>
    <span style="background:#ff3d82;"></span>
    <span style="background:#f5e27a;"></span>
  </div>

  <div class="av-label-group" style="top:16%;right:11%;animation-delay:.8s;">
    <div class="av-label" style="color:rgba(249,237,170,.9);">intensity02</div>
  </div>
  <div class="av-label-group" style="top:22%;right:40%;animation-delay:1s;">
    <div class="av-label" style="color:rgba(255,111,163,.9);">extraction05</div>
  </div>
  <div class="av-label-group" style="top:42%;right:28%;animation-delay:1.2s;">
    <div class="av-label" style="color:rgba(128,232,227,.9);">glitch_24</div>
  </div>

  <div class="hero-tag" style="top:30%;right:24%;animation-delay:1.3s;">
    <div class="hero-tag-inner">digital media</div>
  </div>
  <div class="hero-tag" style="top:54%;right:9%;animation-delay:1.45s;">
    <div class="hero-tag-inner">
      <svg width="11" height="11" viewBox="0 0 12 12" fill="none">
        <circle cx="5" cy="5" r="3.4" stroke="rgba(255,255,255,0.65)" stroke-width="1.3"/>
        <line x1="7.4" y1="7.4" x2="11" y2="11" stroke="rgba(255,255,255,0.65)" stroke-width="1.4" stroke-linecap="round"/>
      </svg>
      researching
    </div>
  </div>

  <div class="hero-content">
    <h1 class="hero-name">
      <span class="first">Mai</span><span class="rest"> W. <em>Ibrahim</em></span>
    </h1>
    <p class="hero-desc">is a media theorist &amp; researcher of digital cultures.</p>
    <div class="hero-btn" style="margin-top:10px;"><a href="#">Enter ↓</a></div>
  </div>
</div>

<div class="version-badge">Version B — GLSL Shaders</div>

<script>
// ── Shared WebGL boilerplate ─────────────────────────────────────────────────
function createShaderProgram(gl, vert, frag) {
  function compile(type, src) {
    const s = gl.createShader(type);
    gl.shaderSource(s, src);
    gl.compileShader(s);
    return s;
  }
  const prog = gl.createProgram();
  gl.attachShader(prog, compile(gl.VERTEX_SHADER, vert));
  gl.attachShader(prog, compile(gl.FRAGMENT_SHADER, frag));
  gl.linkProgram(prog);
  return prog;
}

function initCanvas(canvas) {
  const gl = canvas.getContext('webgl', { premultipliedAlpha: false, alpha: true });
  gl.clearColor(0, 0, 0, 0);

  const verts = new Float32Array([-1,-1, 1,-1, -1,1, 1,1]);
  const buf = gl.createBuffer();
  gl.bindBuffer(gl.ARRAY_BUFFER, buf);
  gl.bufferData(gl.ARRAY_BUFFER, verts, gl.STATIC_DRAW);

  const vert = `
    attribute vec2 a_pos;
    varying vec2 v_uv;
    void main() {
      v_uv = a_pos * 0.5 + 0.5;
      gl_Position = vec4(a_pos, 0.0, 1.0);
    }
  `;
  return { gl, vert };
}

function drawQuad(gl, prog) {
  gl.useProgram(prog);
  const loc = gl.getAttribLocation(prog, 'a_pos');
  gl.enableVertexAttribArray(loc);
  gl.vertexAttribPointer(loc, 2, gl.FLOAT, false, 0, 0);
  gl.enable(gl.BLEND);
  gl.blendFunc(gl.ONE, gl.ONE_MINUS_SRC_ALPHA);
  gl.drawArrays(gl.TRIANGLE_STRIP, 0, 4);
}

// ── Position canvases to match CSS avatar positions ──────────────────────────
function positionCanvas(canvas, rightPct, topPct, size) {
  canvas.style.width  = size + 'px';
  canvas.style.height = size + 'px';
  canvas.style.right  = (rightPct / 100 * window.innerWidth  - size / 2) + 'px';
  canvas.style.top    = (topPct  / 100 * window.innerHeight - size / 2 + 60) + 'px';
}

const SZ = 240;
positionCanvas(document.getElementById('c-intensity'),  11, 16, SZ);
positionCanvas(document.getElementById('c-extraction'), 40, 22, SZ);
positionCanvas(document.getElementById('c-glitch'),     28, 42, SZ);

// ════════════════════════════════════════════════════════════════════════════
// INTENSITY02 — Massumi's affect: pre-conscious, unresolved, never forming
// A field that almost coheres — golden warmth pooling, never crystallising.
// Uses layered fbm (fractal Brownian motion) with time-morphing domain warp.
// ════════════════════════════════════════════════════════════════════════════
(function () {
  const canvas = document.getElementById('c-intensity');
  const { gl, vert } = initCanvas(canvas);

  const frag = `
    precision highp float;
    varying vec2 v_uv;
    uniform float u_time;

    // Permutation hash
    vec3 hash3(vec2 p) {
      vec3 q = vec3(dot(p,vec2(127.1,311.7)),
                    dot(p,vec2(269.5,183.3)),
                    dot(p,vec2(419.2,371.9)));
      return fract(sin(q) * 43758.5453);
    }

    // Smooth value noise
    float noise(vec2 p) {
      vec2 i = floor(p);
      vec2 f = fract(p);
      vec2 u = f*f*(3.0-2.0*f);
      return mix(mix(dot(hash3(i+vec2(0,0)).xy, f-vec2(0,0)),
                     dot(hash3(i+vec2(1,0)).xy, f-vec2(1,0)), u.x),
                 mix(dot(hash3(i+vec2(0,1)).xy, f-vec2(0,1)),
                     dot(hash3(i+vec2(1,1)).xy, f-vec2(1,1)), u.x), u.y);
    }

    // FBM — fractal Brownian motion
    float fbm(vec2 p) {
      float v = 0.0; float a = 0.5;
      mat2 rot = mat2(cos(0.5),sin(0.5),-sin(0.5),cos(0.5));
      for(int i=0; i<5; i++){
        v += a * noise(p);
        p = rot * p * 2.02;
        a *= 0.5;
      }
      return v;
    }

    void main() {
      vec2 uv = v_uv * 2.0 - 1.0;
      float r = length(uv);

      // Soft circular mask — feathered edge
      float mask = 1.0 - smoothstep(0.70, 1.0, r);
      if(mask < 0.001) { gl_FragColor = vec4(0.0); return; }

      float t = u_time * 0.18;

      // Domain warp — two fbm layers twist the coordinate
      vec2 q = vec2(fbm(uv + vec2(0.0, 0.0) + t),
                    fbm(uv + vec2(5.2, 1.3) + t * 0.7));
      vec2 r2 = vec2(fbm(uv + 4.0*q + vec2(1.7, 9.2) + t * 0.4),
                     fbm(uv + 4.0*q + vec2(8.3, 2.8) + t * 0.3));

      float f = fbm(uv + 4.0*r2 + t * 0.2);
      f = f*f*f + 0.6*f*f + 0.5*f;

      // Colour: deep navy → warm gold → pale cream
      vec3 col = mix(
        vec3(0.04, 0.11, 0.22),   // deep navy
        vec3(0.96, 0.89, 0.48),   // warm gold
        clamp(f * 2.0, 0.0, 1.0)
      );
      col = mix(col,
        vec3(0.99, 0.96, 0.82),   // pale cream at peaks
        clamp((f - 0.5) * 2.0, 0.0, 1.0)
      );

      // Radial vignette — brighter at centre
      col *= (0.5 + 0.5 * (1.0 - r * 0.9));

      // Master opacity: 0.36 so name leads
      float alpha = mask * 0.36 * smoothstep(0.0, 0.4, f + 0.2);
      col *= alpha;
      gl_FragColor = vec4(col, alpha);
    }
  `;

  const prog = createShaderProgram(gl, vert, frag);
  const uTime = gl.getUniformLocation(prog, 'u_time');

  let t = Math.random() * 100;
  function loop() {
    requestAnimationFrame(loop);
    t += 0.016;
    gl.clear(gl.COLOR_BUFFER_BIT);
    gl.useProgram(prog);
    gl.uniform1f(uTime, t);
    drawQuad(gl, prog);
  }
  loop();
  setTimeout(() => { canvas.style.opacity = '1'; }, 400);
})();


// ════════════════════════════════════════════════════════════════════════════
// EXTRACTION05 — platform capitalism's body-as-site: a vortex pulling inward.
// Spiralling pink field with silver particles raining into a black void.
// ════════════════════════════════════════════════════════════════════════════
(function () {
  const canvas = document.getElementById('c-extraction');
  const { gl, vert } = initCanvas(canvas);

  const frag = `
    precision highp float;
    varying vec2 v_uv;
    uniform float u_time;

    float hash(vec2 p) {
      return fract(sin(dot(p, vec2(127.1, 311.7))) * 43758.5453);
    }

    // Smooth noise
    float noise(vec2 p) {
      vec2 i = floor(p); vec2 f = fract(p);
      vec2 u = f*f*(3.0-2.0*f);
      float a = hash(i);
      float b = hash(i+vec2(1,0));
      float c = hash(i+vec2(0,1));
      float d = hash(i+vec2(1,1));
      return mix(mix(a,b,u.x), mix(c,d,u.x), u.y);
    }

    // Silver particle dots — discrete squares of luminance
    float particles(vec2 uv, float t) {
      float result = 0.0;
      // 18 particles in 3 rows
      for(int i = 0; i < 18; i++) {
        float fi = float(i);
        float col_f = mod(fi, 6.0);
        float row_f = floor(fi / 6.0);
        // x spread, y rains downward toward centre
        float px = -0.55 + col_f * 0.22 + sin(fi * 2.3 + t * 0.4) * 0.04;
        float baseY = 0.75 - row_f * 0.28;
        float py = baseY - mod(t * (0.12 + hash(vec2(fi,0.0)) * 0.08) + hash(vec2(fi,1.0)), 1.2);
        float d = length(uv - vec2(px, py));
        // taper opacity as they converge downward
        float fade = 1.0 - smoothstep(-0.2, 0.5, py);
        result += (1.0 - smoothstep(0.012, 0.030, d)) * fade * 0.85;
      }
      return clamp(result, 0.0, 1.0);
    }

    void main() {
      vec2 uv = v_uv * 2.0 - 1.0;
      float r  = length(uv);
      float ang = atan(uv.y, uv.x);
      float t  = u_time * 0.22;

      float mask = 1.0 - smoothstep(0.72, 1.0, r);
      if(mask < 0.001) { gl_FragColor = vec4(0.0); return; }

      // Funnel field — tighter spin toward centre
      float spin = ang - t * 1.4 + r * 3.5;
      float funnel = sin(spin * 3.0) * 0.5 + 0.5;
      funnel *= smoothstep(0.0, 0.55, r); // hollow centre
      funnel *= (1.0 - smoothstep(0.40, 0.72, r)); // fade edge

      // Noise turbulence
      float turb = noise(uv * 3.5 + vec2(t * 0.5, -t * 0.3));

      // Void at centre: deep black hole
      float voidMask = 1.0 - smoothstep(0.0, 0.22, r);

      // Funnel colour: deep rose → hot pink → void black
      vec3 funnelCol = mix(
        vec3(0.55, 0.04, 0.22),   // deep rose
        vec3(1.0,  0.24, 0.51),   // hot pink
        clamp(funnel * 1.5 + turb * 0.4, 0.0, 1.0)
      );
      funnelCol = mix(funnelCol, vec3(0.0), voidMask);

      // Silver particles
      float pts = particles(uv, t);
      vec3 silverCol = mix(funnelCol,
        vec3(0.75, 0.82, 0.88),   // silver
        pts
      );

      // Build alpha
      float alpha = mask * 0.36 * (funnel * 0.8 + turb * 0.2 + pts * 0.7 + 0.05);
      alpha = clamp(alpha, 0.0, 0.36);
      silverCol *= alpha / max(alpha, 0.001);
      gl_FragColor = vec4(silverCol * alpha, alpha);
    }
  `;

  const prog = createShaderProgram(gl, vert, frag);
  const uTime = gl.getUniformLocation(prog, 'u_time');

  let t = Math.random() * 100;
  function loop() {
    requestAnimationFrame(loop);
    t += 0.016;
    gl.clear(gl.COLOR_BUFFER_BIT);
    gl.useProgram(prog);
    gl.uniform1f(uTime, t);
    drawQuad(gl, prog);
  }
  loop();
  setTimeout(() => { canvas.style.opacity = '1'; }, 700);
})();


// ════════════════════════════════════════════════════════════════════════════
// GLITCH_24 — corrupted signal; time as broken data.
// A screen that tears, displaces, bleeds RGB channels continuously.
// CRT scanlines, digital noise blocks, chromatic aberration as lived time.
// ════════════════════════════════════════════════════════════════════════════
(function () {
  const canvas = document.getElementById('c-glitch');
  const { gl, vert } = initCanvas(canvas);

  const frag = `
    precision highp float;
    varying vec2 v_uv;
    uniform float u_time;

    float hash(float x) { return fract(sin(x) * 43758.5453); }
    float hash2(vec2 p) { return fract(sin(dot(p, vec2(127.1, 311.7))) * 43758.5453); }

    float noise(vec2 p) {
      vec2 i = floor(p); vec2 f = fract(p);
      vec2 u = f*f*(3.0-2.0*f);
      return mix(mix(hash2(i),         hash2(i+vec2(1,0)), u.x),
                 mix(hash2(i+vec2(0,1)),hash2(i+vec2(1,1)),u.x), u.y);
    }

    void main() {
      vec2 uv = v_uv;
      float t = u_time;

      // Circular mask
      vec2 c = uv * 2.0 - 1.0;
      float r = length(c);
      float mask = 1.0 - smoothstep(0.70, 1.0, r);
      if(mask < 0.001) { gl_FragColor = vec4(0.0); return; }

      // ── GLITCH DISPLACEMENT ──────────────────────────────
      // Large horizontal slice tears
      float sliceY = floor(uv.y * 18.0) / 18.0;
      float sliceSeed = hash(sliceY + floor(t * 7.0) * 0.3);
      float tearStrength = step(0.82, sliceSeed) * hash(sliceY * 31.7 + t) * 0.18;
      float uvX = uv.x + tearStrength * (hash(sliceY + t * 2.0) - 0.5);

      // Fine scanline micro-jitter
      float scanSeed = hash(floor(uv.y * 80.0) + floor(t * 14.0));
      float microJitter = (step(0.94, scanSeed) - 0.5) * 0.025;
      uvX += microJitter;

      vec2 uvD = vec2(clamp(uvX, 0.0, 1.0), uv.y);

      // ── RGB CHANNEL SPLIT (chromatic aberration) ─────────
      float caAmt = 0.014 + sin(t * 0.9) * 0.006;
      vec2 uvR = vec2(uvD.x + caAmt, uvD.y);
      vec2 uvG = uvD;
      vec2 uvB = vec2(uvD.x - caAmt, uvD.y);

      // ── SCREEN CONTENT (generated stripes + noise) ───────
      float stripeR = 0.0, stripeG = 0.0, stripeB = 0.0;

      // Horizontal coloured bands (the "content" being corrupted)
      float band = floor(uvD.y * 7.0);
      float bandCol = hash(band + 0.5);

      // Teal bands
      stripeR += step(0.55, bandCol) * step(bandCol, 0.70) * 0.20 * noise(uvR * vec2(6.0, 1.0) + t*0.3);
      stripeG += step(0.55, bandCol) * step(bandCol, 0.70) * 0.88 * noise(uvG * vec2(6.0, 1.0) + t*0.3);
      stripeB += step(0.55, bandCol) * step(bandCol, 0.70) * 0.84 * noise(uvB * vec2(6.0, 1.0) + t*0.3);

      // Pink bands
      stripeR += step(0.30, bandCol) * step(bandCol, 0.45) * 0.90 * noise(uvR * vec2(4.0, 1.0) - t*0.2);
      stripeG += step(0.30, bandCol) * step(bandCol, 0.45) * 0.15 * noise(uvG * vec2(4.0, 1.0));
      stripeB += step(0.30, bandCol) * step(bandCol, 0.45) * 0.42 * noise(uvB * vec2(4.0, 1.0));

      // Yellow band
      stripeR += step(0.72, bandCol) * 0.95 * noise(uvR * vec2(5.0,1.0) + t*0.4);
      stripeG += step(0.72, bandCol) * 0.88 * noise(uvG * vec2(5.0,1.0) + t*0.4);
      stripeB += step(0.72, bandCol) * 0.25;

      // White fragment
      stripeR += step(0.15, bandCol) * step(bandCol, 0.22) * 0.70;
      stripeG += step(0.15, bandCol) * step(bandCol, 0.22) * 0.70;
      stripeB += step(0.15, bandCol) * step(bandCol, 0.22) * 0.70;

      vec3 screenCol = vec3(stripeR, stripeG, stripeB);

      // ── NOISE BLOCKS — random coloured rectangles ────────
      for(int i = 0; i < 6; i++) {
        float fi = float(i);
        float bx = hash(fi * 7.3 + floor(t * 5.0));
        float by = hash(fi * 13.1 + floor(t * 4.0));
        float bw = 0.06 + hash(fi * 3.7) * 0.12;
        float bh = 0.04 + hash(fi * 5.2) * 0.08;
        if(uvD.x > bx && uvD.x < bx+bw && uvD.y > by && uvD.y < by+bh) {
          vec3 noiseCol = vec3(hash(fi + t*0.5), hash(fi*2.0+t*0.3), hash(fi*3.0+t*0.4));
          // Bias toward palette colours
          noiseCol = mix(noiseCol,
            mix(vec3(0.05, 0.75, 0.71), vec3(1.0, 0.24, 0.51), hash(fi)),
            0.7);
          screenCol = mix(screenCol, noiseCol, 0.9);
        }
      }

      // ── SCANLINES ────────────────────────────────────────
      float scan = sin(uv.y * 180.0 + t * 0.5) * 0.5 + 0.5;
      screenCol *= 0.82 + scan * 0.18;

      // ── CRT VIGNETTE ─────────────────────────────────────
      float vig = (1.0 - r * 0.6);
      screenCol *= vig;

      // ── DARK BASE (screen off-state underneath) ──────────
      vec3 dark = vec3(0.008, 0.03, 0.07);
      float contentStr = clamp(stripeR + stripeG + stripeB, 0.0, 1.0) * 0.7 + 0.15;
      screenCol = mix(dark, screenCol, contentStr);

      // ── ALPHA ─────────────────────────────────────────────
      float alpha = mask * 0.37;
      screenCol *= alpha;
      gl_FragColor = vec4(screenCol, alpha);
    }
  `;

  const prog = createShaderProgram(gl, vert, frag);
  const uTime = gl.getUniformLocation(prog, 'u_time');

  // Ambient drift: oscillate canvas position slightly
  const canvasEl = canvas;
  const baseRight = parseFloat(canvasEl.style.right);
  const baseTop   = parseFloat(canvasEl.style.top);

  let t = Math.random() * 100;
  function loop() {
    requestAnimationFrame(loop);
    t += 0.016;
    gl.clear(gl.COLOR_BUFFER_BIT);
    gl.useProgram(prog);
    gl.uniform1f(uTime, t);
    drawQuad(gl, prog);

    // Very gentle float
    canvasEl.style.right = (baseRight + Math.sin(t * 0.28) * 5) + 'px';
    canvasEl.style.top   = (baseTop   + Math.sin(t * 0.21) * 6) + 'px';
  }
  loop();
  setTimeout(() => { canvas.style.opacity = '1'; }, 1000);
})();

// Ambient float for intensity and extraction canvases
(function() {
  const ci = document.getElementById('c-intensity');
  const ce = document.getElementById('c-extraction');
  const ri = parseFloat(ci.style.right), ti = parseFloat(ci.style.top);
  const re = parseFloat(ce.style.right), te = parseFloat(ce.style.top);
  let t = 0;
  function drift() {
    requestAnimationFrame(drift);
    t += 0.016;
    ci.style.right = (ri + Math.sin(t * 0.34 + 0.5) * 6) + 'px';
    ci.style.top   = (ti + Math.sin(t * 0.26 + 1.2) * 7) + 'px';
    ce.style.right = (re + Math.sin(t * 0.29 + 2.1) * 5) + 'px';
    ce.style.top   = (te + Math.sin(t * 0.22 + 0.8) * 6) + 'px';
  }
  drift();
})();

window.addEventListener('resize', () => location.reload());
</script>
</body>
</html>
