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

/* ── Avatar wrapper: circle frame + label stacked ── */
.av-wrap {
  position: absolute;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 7px;
  z-index: 5;
  pointer-events: none;
  opacity: 0;
  animation: avIn 1s ease forwards;
}
@keyframes avIn {
  from { opacity: 0; transform: translateY(12px); }
  to   { opacity: 0.42; transform: translateY(0); }
}

/* The circle border that frames the shader canvas */
.av-circle {
  width: 160px;
  height: 160px;
  border-radius: 50%;
  position: relative;
  flex-shrink: 0;
  /* coloured ring — overridden per avatar via inline style */
  box-shadow: 0 0 0 1.5px rgba(255,255,255,0.12), 0 4px 24px rgba(0,0,0,0.4);
}

/* Shader canvas sits inside the circle, clipped to it */
.av-circle canvas {
  position: absolute;
  top: 0; left: 0;
  width: 100% !important;
  height: 100% !important;
  border-radius: 50%;
  display: block;
  opacity: 0;
  transition: opacity 1.6s ease;
}

/* Thin inner shadow to reinforce the circle edge */
.av-circle::after {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: 50%;
  box-shadow: inset 0 0 12px rgba(0,0,0,0.55);
  pointer-events: none;
  z-index: 2;
}

.av-label {
  font-family: 'Space Mono', monospace;
  font-size: 9px;
  letter-spacing: .08em;
  background: rgba(0,0,0,.42);
  padding: 3px 9px;
  border-radius: 2px;
  white-space: nowrap;
}

/* ── Tags ── */
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

/* ── NAV ── */
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

/* ── Hero layout ── */
.hero {
  position: relative; z-index: 2;
  width: 100vw; height: 100vh;
  display: flex; align-items: center;
  padding: 60px 6vw 0;
  pointer-events: none;
}

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
</style>
</head>
<body>

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

  <!--
    Positioning logic:
    The hero name sits at ~50% vertically (flex align-items:center + 60px nav offset).
    We want the HIGHEST avatar top edge to be just above that — so we use top:38% for
    intensity02 (the topmost). The others cascade below it.
    right% values mirror the original layout but condensed inward a touch.
  -->

  <!-- intensity02 — top-right, just above name level -->
  <div class="av-wrap" id="wrap-intensity" style="top:38%; right:10%; animation-delay:.6s;">
    <div class="av-circle" style="border: 1.5px solid rgba(245,226,122,0.45); box-shadow: 0 0 0 1px rgba(245,226,122,0.12), 0 0 18px rgba(245,226,122,0.12), 0 4px 20px rgba(0,0,0,0.4);">
      <canvas id="c-intensity" width="320" height="320"></canvas>
    </div>
    <div class="av-label" style="color:rgba(249,237,170,.9);">intensity02</div>
  </div>

  <!-- extraction05 — centre-right, slightly lower -->
  <div class="av-wrap" id="wrap-extraction" style="top:46%; right:36%; animation-delay:.8s;">
    <div class="av-circle" style="border: 1.5px solid rgba(255,61,130,0.45); box-shadow: 0 0 0 1px rgba(255,61,130,0.12), 0 0 18px rgba(255,61,130,0.10), 0 4px 20px rgba(0,0,0,0.4);">
      <canvas id="c-extraction" width="320" height="320"></canvas>
    </div>
    <div class="av-label" style="color:rgba(255,111,163,.9);">extraction05</div>
  </div>

  <!-- glitch_24 — lower, between the other two -->
  <div class="av-wrap" id="wrap-glitch" style="top:58%; right:22%; animation-delay:1s;">
    <div class="av-circle" style="border: 1.5px solid rgba(13,191,180,0.45); box-shadow: 0 0 0 1px rgba(13,191,180,0.12), 0 0 18px rgba(13,191,180,0.10), 0 4px 20px rgba(0,0,0,0.4);">
      <canvas id="c-glitch" width="320" height="320"></canvas>
    </div>
    <div class="av-label" style="color:rgba(128,232,227,.9);">glitch_24</div>
  </div>

  <!-- Floating tags — repositioned to sit near the avatar cluster -->
  <div class="hero-tag" style="top:44%; right:24%; animation-delay:1.1s;">
    <div class="hero-tag-inner">digital media</div>
  </div>
  <div class="hero-tag" style="top:68%; right:8%; animation-delay:1.25s;">
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

<script>
// ── Shared WebGL boilerplate ──────────────────────────────────────────────────
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

// ════════════════════════════════════════════════════════════════════════════
// INTENSITY02 — domain-warped FBM, golden warmth that never resolves
// ════════════════════════════════════════════════════════════════════════════
(function () {
  const canvas = document.getElementById('c-intensity');
  const { gl, vert } = initCanvas(canvas);

  const frag = `
    precision highp float;
    varying vec2 v_uv;
    uniform float u_time;

    vec3 hash3(vec2 p) {
      vec3 q = vec3(dot(p,vec2(127.1,311.7)),
                    dot(p,vec2(269.5,183.3)),
                    dot(p,vec2(419.2,371.9)));
      return fract(sin(q) * 43758.5453);
    }
    float noise(vec2 p) {
      vec2 i = floor(p); vec2 f = fract(p);
      vec2 u = f*f*(3.0-2.0*f);
      return mix(mix(dot(hash3(i+vec2(0,0)).xy, f-vec2(0,0)),
                     dot(hash3(i+vec2(1,0)).xy, f-vec2(1,0)), u.x),
                 mix(dot(hash3(i+vec2(0,1)).xy, f-vec2(0,1)),
                     dot(hash3(i+vec2(1,1)).xy, f-vec2(1,1)), u.x), u.y);
    }
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
      float mask = 1.0 - smoothstep(0.70, 1.0, r);
      if(mask < 0.001) { gl_FragColor = vec4(0.0); return; }

      float t = u_time * 0.18;
      vec2 q = vec2(fbm(uv + vec2(0.0, 0.0) + t),
                    fbm(uv + vec2(5.2, 1.3) + t * 0.7));
      vec2 r2 = vec2(fbm(uv + 4.0*q + vec2(1.7, 9.2) + t * 0.4),
                     fbm(uv + 4.0*q + vec2(8.3, 2.8) + t * 0.3));
      float f = fbm(uv + 4.0*r2 + t * 0.2);
      f = f*f*f + 0.6*f*f + 0.5*f;

      vec3 col = mix(vec3(0.04, 0.11, 0.22), vec3(0.96, 0.89, 0.48),
                     clamp(f * 2.0, 0.0, 1.0));
      col = mix(col, vec3(0.99, 0.96, 0.82),
                clamp((f - 0.5) * 2.0, 0.0, 1.0));
      col *= (0.5 + 0.5 * (1.0 - r * 0.9));

      float alpha = mask * 0.82 * smoothstep(0.0, 0.4, f + 0.2);
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
  setTimeout(() => { canvas.style.opacity = '1'; }, 300);
})();

// ════════════════════════════════════════════════════════════════════════════
// EXTRACTION05 — vortex + silver particle rain into void
// ════════════════════════════════════════════════════════════════════════════
(function () {
  const canvas = document.getElementById('c-extraction');
  const { gl, vert } = initCanvas(canvas);

  const frag = `
    precision highp float;
    varying vec2 v_uv;
    uniform float u_time;

    float hash(float x) { return fract(sin(x) * 43758.5453); }
    float hash2(vec2 p)  { return fract(sin(dot(p, vec2(127.1, 311.7))) * 43758.5453); }
    float noise(vec2 p) {
      vec2 i = floor(p); vec2 f = fract(p);
      vec2 u = f*f*(3.0-2.0*f);
      float a = hash2(i), b = hash2(i+vec2(1,0)),
            c = hash2(i+vec2(0,1)), d = hash2(i+vec2(1,1));
      return mix(mix(a,b,u.x), mix(c,d,u.x), u.y);
    }

    float particles(vec2 uv, float t) {
      float result = 0.0;
      for(int i = 0; i < 18; i++) {
        float fi = float(i);
        float col_f = mod(fi, 6.0);
        float row_f = floor(fi / 6.0);
        float px = -0.55 + col_f * 0.22 + sin(fi * 2.3 + t * 0.4) * 0.04;
        float baseY = 0.75 - row_f * 0.28;
        float py = baseY - mod(t * (0.12 + hash(vec2(fi,0.0)) * 0.08) + hash(vec2(fi,1.0)), 1.2);
        float d = length(uv - vec2(px, py));
        float fade = 1.0 - smoothstep(-0.2, 0.5, py);
        result += (1.0 - smoothstep(0.012, 0.030, d)) * fade * 0.85;
      }
      return clamp(result, 0.0, 1.0);
    }

    void main() {
      vec2 uv = v_uv * 2.0 - 1.0;
      float r   = length(uv);
      float ang = atan(uv.y, uv.x);
      float t   = u_time * 0.22;

      float mask = 1.0 - smoothstep(0.72, 1.0, r);
      if(mask < 0.001) { gl_FragColor = vec4(0.0); return; }

      float spin   = ang - t * 1.4 + r * 3.5;
      float funnel = sin(spin * 3.0) * 0.5 + 0.5;
      funnel *= smoothstep(0.0, 0.55, r);
      funnel *= (1.0 - smoothstep(0.40, 0.72, r));

      float turb     = noise(uv * 3.5 + vec2(t * 0.5, -t * 0.3));
      float voidMask = 1.0 - smoothstep(0.0, 0.22, r);

      vec3 funnelCol = mix(vec3(0.55, 0.04, 0.22), vec3(1.0, 0.24, 0.51),
                           clamp(funnel * 1.5 + turb * 0.4, 0.0, 1.0));
      funnelCol = mix(funnelCol, vec3(0.0), voidMask);

      float pts = particles(uv, t);
      vec3 silverCol = mix(funnelCol, vec3(0.75, 0.82, 0.88), pts);

      float alpha = mask * 0.82 * (funnel * 0.8 + turb * 0.2 + pts * 0.7 + 0.05);
      alpha = clamp(alpha, 0.0, 0.82);
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
  setTimeout(() => { canvas.style.opacity = '1'; }, 600);
})();

// ════════════════════════════════════════════════════════════════════════════
// GLITCH_24 — CRT corruption: scanlines, slice tears, RGB channel split
// ════════════════════════════════════════════════════════════════════════════
(function () {
  const canvas = document.getElementById('c-glitch');
  const { gl, vert } = initCanvas(canvas);

  const frag = `
    precision highp float;
    varying vec2 v_uv;
    uniform float u_time;

    float hash(float x)  { return fract(sin(x) * 43758.5453); }
    float hash2(vec2 p)  { return fract(sin(dot(p, vec2(127.1, 311.7))) * 43758.5453); }
    float noise(vec2 p) {
      vec2 i = floor(p); vec2 f = fract(p);
      vec2 u = f*f*(3.0-2.0*f);
      return mix(mix(hash2(i),          hash2(i+vec2(1,0)), u.x),
                 mix(hash2(i+vec2(0,1)), hash2(i+vec2(1,1)), u.x), u.y);
    }

    void main() {
      vec2 uv = v_uv;
      float t = u_time;
      vec2 c = uv * 2.0 - 1.0;
      float r = length(c);
      float mask = 1.0 - smoothstep(0.70, 1.0, r);
      if(mask < 0.001) { gl_FragColor = vec4(0.0); return; }

      float sliceY    = floor(uv.y * 18.0) / 18.0;
      float sliceSeed = hash(sliceY + floor(t * 7.0) * 0.3);
      float tearStr   = step(0.82, sliceSeed) * hash(sliceY * 31.7 + t) * 0.18;
      float uvX       = uv.x + tearStr * (hash(sliceY + t * 2.0) - 0.5);
      float scanSeed  = hash(floor(uv.y * 80.0) + floor(t * 14.0));
      uvX += (step(0.94, scanSeed) - 0.5) * 0.025;
      vec2 uvD = vec2(clamp(uvX, 0.0, 1.0), uv.y);

      float caAmt = 0.014 + sin(t * 0.9) * 0.006;
      vec2 uvR = vec2(uvD.x + caAmt, uvD.y);
      vec2 uvG = uvD;
      vec2 uvB = vec2(uvD.x - caAmt, uvD.y);

      float stripeR = 0.0, stripeG = 0.0, stripeB = 0.0;
      float band    = floor(uvD.y * 7.0);
      float bandCol = hash(band + 0.5);

      stripeR += step(0.55,bandCol)*step(bandCol,0.70)*0.20*noise(uvR*vec2(6.,1.)+t*.3);
      stripeG += step(0.55,bandCol)*step(bandCol,0.70)*0.88*noise(uvG*vec2(6.,1.)+t*.3);
      stripeB += step(0.55,bandCol)*step(bandCol,0.70)*0.84*noise(uvB*vec2(6.,1.)+t*.3);
      stripeR += step(0.30,bandCol)*step(bandCol,0.45)*0.90*noise(uvR*vec2(4.,1.)-t*.2);
      stripeG += step(0.30,bandCol)*step(bandCol,0.45)*0.15*noise(uvG*vec2(4.,1.));
      stripeB += step(0.30,bandCol)*step(bandCol,0.45)*0.42*noise(uvB*vec2(4.,1.));
      stripeR += step(0.72,bandCol)*0.95*noise(uvR*vec2(5.,1.)+t*.4);
      stripeG += step(0.72,bandCol)*0.88*noise(uvG*vec2(5.,1.)+t*.4);
      stripeB += step(0.72,bandCol)*0.25;
      stripeR += step(0.15,bandCol)*step(bandCol,0.22)*0.70;
      stripeG += step(0.15,bandCol)*step(bandCol,0.22)*0.70;
      stripeB += step(0.15,bandCol)*step(bandCol,0.22)*0.70;

      vec3 screenCol = vec3(stripeR, stripeG, stripeB);

      for(int i = 0; i < 6; i++) {
        float fi = float(i);
        float bx = hash(fi*7.3+floor(t*5.0));
        float by = hash(fi*13.1+floor(t*4.0));
        float bw = 0.06+hash(fi*3.7)*0.12;
        float bh = 0.04+hash(fi*5.2)*0.08;
        if(uvD.x>bx && uvD.x<bx+bw && uvD.y>by && uvD.y<by+bh) {
          vec3 nc = vec3(hash(fi+t*.5),hash(fi*2.+t*.3),hash(fi*3.+t*.4));
          nc = mix(nc, mix(vec3(.05,.75,.71),vec3(1.,.24,.51),hash(fi)), .7);
          screenCol = mix(screenCol, nc, 0.9);
        }
      }

      float scan = sin(uv.y * 180.0 + t * 0.5) * 0.5 + 0.5;
      screenCol *= 0.82 + scan * 0.18;
      screenCol *= (1.0 - r * 0.6);

      vec3 dark = vec3(0.008, 0.03, 0.07);
      float cStr = clamp(stripeR+stripeG+stripeB,0.,1.)*0.7+0.15;
      screenCol = mix(dark, screenCol, cStr);

      float alpha = mask * 0.82;
      screenCol *= alpha;
      gl_FragColor = vec4(screenCol, alpha);
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
  setTimeout(() => { canvas.style.opacity = '1'; }, 900);
})();

// ── Ambient drift — gently float each wrapper div ───────────────────────────
(function () {
  const avatars = [
    { el: document.getElementById('wrap-intensity'),  px: 0.0,  py: 0.0,  fx: 0.34, fy: 0.26, ax: 5, ay: 7 },
    { el: document.getElementById('wrap-extraction'), px: 0.0,  py: 0.0,  fx: 0.29, fy: 0.22, ax: 4, ay: 5 },
    { el: document.getElementById('wrap-glitch'),     px: 0.0,  py: 0.0,  fx: 0.28, fy: 0.21, ax: 6, ay: 5 },
  ];

  // Store natural CSS transform offsets (none — we drive via translateX/Y)
  let t = 0;
  function drift() {
    requestAnimationFrame(drift);
    t += 0.016;
    avatars.forEach((av, i) => {
      const dx = Math.sin(t * av.fx + i * 1.8) * av.ax;
      const dy = Math.sin(t * av.fy + i * 2.4) * av.ay;
      av.el.style.transform = `translate(${dx}px, ${dy}px)`;
    });
  }
  drift();
})();

window.addEventListener('resize', () => location.reload());
</script>
</body>
</html>
