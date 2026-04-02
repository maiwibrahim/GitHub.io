<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>GLSL Hero — Mai W. Ibrahim</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=Space+Mono:wght@400;700&family=Lora:ital,wght@0,400;0,500;1,400&display=swap');

:root {
  --teal:        #0dbfb4;
  --teal-soft:   #35d4ca;
  --pink:        #ff3d82;
  --yellow-soft: #f9edaa;
  --hero-bg:     #0b1b2e;
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

body {
  background: var(--hero-bg);
  overflow: hidden;
  font-family: 'Lora', Georgia, serif;
  width: 100vw; height: 100vh;
}

/* NAV */
.site-nav {
  position: fixed; top: 0; left: 0; right: 0; z-index: 200;
  background: rgba(11,27,46,.92); backdrop-filter: blur(14px);
  display: flex; gap: 2rem; align-items: center; justify-content: flex-end;
  height: 60px; padding: 0 3rem;
  border-bottom: .5px solid rgba(13,191,180,.18);
}
.site-nav a {
  font-family: 'Space Mono', monospace; font-size: 12px;
  color: #fff; text-decoration: none;
  letter-spacing: .18em; text-transform: uppercase;
}

/* HERO */
.hero {
  position: relative; z-index: 2;
  width: 100vw; height: 100vh;
  display: flex; align-items: center;
  padding: 60px 6vw 0;
}

/* HERO TEXT */
.hero-content {
  position: relative; z-index: 20;
  display: flex; flex-direction: column; gap: 14px;
  max-width: 600px;
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
.hero-btn { margin-top: 10px; }
.hero-btn a {
  font-family: 'Space Mono', monospace; font-size: 11px;
  letter-spacing: .15em; text-transform: uppercase;
  color: #0b1b2e; background: var(--teal);
  padding: 12px 28px; text-decoration: none; display: inline-block;
}

/* UI dots */
.ui-dots {
  position: absolute; top: 18px; right: 20px;
  display: flex; gap: 5px; z-index: 20;
}
.ui-dots span { width: 6px; height: 6px; border-radius: 50%; }

/* ─── AVATAR WRAPPERS ───────────────────────────────────────────────────── */
/*
  Each avatar is a positioned div containing:
    - a <canvas> for the WebGL shader
    - an oval border overlay (::before pseudo)
    - an inner glow overlay (::after pseudo)
    - a label below

  We do NOT clip the canvas with border-radius — WebGL canvases get clipped
  by the SHADER itself (circular/oval mask in GLSL). The border is purely CSS.
*/

.av-wrap {
  position: absolute;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
  z-index: 10;
  pointer-events: none;
}

/* The oval "frame" div that holds the canvas */
.av-frame {
  position: relative;
  /* Each avatar gets its own width/height via inline style */
}

/* Oval border ring — sits on top of canvas via z-index */
.av-frame::before {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: inherit;
  z-index: 3;
  pointer-events: none;
  /* border colour set per-avatar via inline style on av-frame */
}

/* Inner shadow to deepen edges */
.av-frame::after {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: inherit;
  box-shadow: inset 0 0 18px rgba(0,0,0,.6);
  z-index: 4;
  pointer-events: none;
}

/* Canvas fills the frame exactly — NO CSS border-radius on canvas itself
   because that breaks WebGL on some browsers. Shape comes from GLSL mask. */
.av-frame canvas {
  display: block;
  width: 100%;
  height: 100%;
}

.av-label {
  font-family: 'Space Mono', monospace;
  font-size: 9px; letter-spacing: .08em;
  background: rgba(0,0,0,.45);
  padding: 3px 9px; border-radius: 2px;
  white-space: nowrap;
  /* colour set per-avatar */
}

/* Fade-in animation — each wrapper fades to its final opacity */
@keyframes avFadeIn {
  from { opacity: 0; transform: translateY(14px); }
  to   { opacity: var(--final-op, .42); transform: translateY(0); }
}

/* ─── FLOATING TAGS ──────────────────────────────────────────────────────── */
.hero-tag {
  position: absolute; z-index: 15;
  opacity: 0;
  animation: tagFadeIn .8s ease forwards;
}
@keyframes tagFadeIn {
  from { opacity: 0; transform: translateY(8px); }
  to   { opacity: .38; transform: translateY(0); }
}
.hero-tag-inner {
  background: rgba(255,255,255,.08);
  border: .5px solid rgba(255,255,255,.22);
  padding: 5px 13px;
  font-family: 'Space Mono', monospace;
  font-size: 11px; color: rgba(255,255,255,.8);
  white-space: nowrap; border-radius: 6px;
  display: inline-flex; align-items: center; gap: 6px;
}
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

  <!-- ═══════════════════════════════════════════════════
       AVATAR 1 — intensity02
       Oval shape: wider than tall, tilted slightly
       Position: upper right, just above name level
  ══════════════════════════════════════════════════════ -->
  <div class="av-wrap" id="av-intensity"
       style="top:36%; right:9%;
              opacity:0;
              animation: avFadeIn 1s ease .5s forwards;
              --final-op: .42;">
    <div class="av-frame"
         style="width:154px; height:130px;
                border-radius: 52% 48% 55% 45% / 48% 52% 48% 52%;
                border: 1.5px solid rgba(245,226,122,.5);
                box-shadow: 0 0 22px rgba(245,226,122,.15), 0 4px 20px rgba(0,0,0,.5);">
      <!-- canvas pixel size matches display size exactly -->
      <canvas id="c-intensity" width="154" height="130"></canvas>
    </div>
    <div class="av-label" style="color:rgba(249,237,170,.9);">intensity02</div>
  </div>

  <!-- ═══════════════════════════════════════════════════
       AVATAR 2 — extraction05
       Oval shape: taller than wide, different border-radius
       Position: centre-right cluster
  ══════════════════════════════════════════════════════ -->
  <div class="av-wrap" id="av-extraction"
       style="top:47%; right:33%;
              opacity:0;
              animation: avFadeIn 1s ease .75s forwards;
              --final-op: .42;">
    <div class="av-frame"
         style="width:138px; height:158px;
                border-radius: 45% 55% 48% 52% / 55% 45% 55% 45%;
                border: 1.5px solid rgba(255,61,130,.5);
                box-shadow: 0 0 22px rgba(255,61,130,.14), 0 4px 20px rgba(0,0,0,.5);">
      <canvas id="c-extraction" width="138" height="158"></canvas>
    </div>
    <div class="av-label" style="color:rgba(255,111,163,.9);">extraction05</div>
  </div>

  <!-- ═══════════════════════════════════════════════════
       AVATAR 3 — glitch_24
       Oval shape: slightly landscape, irregular
       Position: lower, between the two above
  ══════════════════════════════════════════════════════ -->
  <div class="av-wrap" id="av-glitch"
       style="top:59%; right:18%;
              opacity:0;
              animation: avFadeIn 1s ease 1s forwards;
              --final-op: .42;">
    <div class="av-frame"
         style="width:148px; height:122px;
                border-radius: 48% 52% 44% 56% / 52% 48% 56% 44%;
                border: 1.5px solid rgba(13,191,180,.5);
                box-shadow: 0 0 22px rgba(13,191,180,.14), 0 4px 20px rgba(0,0,0,.5);">
      <canvas id="c-glitch" width="148" height="122"></canvas>
    </div>
    <div class="av-label" style="color:rgba(128,232,227,.9);">glitch_24</div>
  </div>

  <!-- FLOATING TAGS -->
  <div class="hero-tag" style="top:44%; right:22%; animation-delay:1.1s;">
    <div class="hero-tag-inner">digital media</div>
  </div>
  <div class="hero-tag" style="top:68%; right:7%; animation-delay:1.25s;">
    <div class="hero-tag-inner">
      <svg width="11" height="11" viewBox="0 0 12 12" fill="none">
        <circle cx="5" cy="5" r="3.4" stroke="rgba(255,255,255,.65)" stroke-width="1.3"/>
        <line x1="7.4" y1="7.4" x2="11" y2="11" stroke="rgba(255,255,255,.65)" stroke-width="1.4" stroke-linecap="round"/>
      </svg>
      researching
    </div>
  </div>

  <!-- HERO TEXT -->
  <div class="hero-content">
    <h1 class="hero-name">
      <span class="first">Mai</span><span class="rest"> W. <em>Ibrahim</em></span>
    </h1>
    <p class="hero-desc">is a media theorist &amp; researcher of digital cultures.</p>
    <div class="hero-btn"><a href="#">Enter ↓</a></div>
  </div>
</div>

<script>
'use strict';

/* ═══════════════════════════════════════════════════════════════════════════
   SHARED WEBGL UTILITIES
   Key principle: canvas pixel dimensions (width/height attributes) must
   match exactly what the CSS renders. We set them in HTML and never touch
   them again. drawQuad is called after useProgram + uniforms.
══════════════════════════════════════════════════════════════════════════════ */

function buildGL(canvasId) {
  const canvas = document.getElementById(canvasId);
  const gl = canvas.getContext('webgl', { alpha: true, premultipliedAlpha: false });
  if (!gl) return null;
  gl.clearColor(0, 0, 0, 0);
  gl.enable(gl.BLEND);
  gl.blendFunc(gl.SRC_ALPHA, gl.ONE_MINUS_SRC_ALPHA);

  // Full-screen quad
  const buf = gl.createBuffer();
  gl.bindBuffer(gl.ARRAY_BUFFER, buf);
  gl.bufferData(gl.ARRAY_BUFFER,
    new Float32Array([-1,-1, 1,-1, -1,1, 1,1]),
    gl.STATIC_DRAW);

  return { gl, canvas };
}

function buildProgram(gl, fragSrc) {
  const vertSrc = `
    attribute vec2 pos;
    varying   vec2 vUV;
    void main(){
      vUV = pos * .5 + .5;
      gl_Position = vec4(pos, 0., 1.);
    }`;

  function shader(type, src) {
    const s = gl.createShader(type);
    gl.shaderSource(s, src);
    gl.compileShader(s);
    return s;
  }
  const prog = gl.createProgram();
  gl.attachShader(prog, shader(gl.VERTEX_SHADER, vertSrc));
  gl.attachShader(prog, shader(gl.FRAGMENT_SHADER, fragSrc));
  gl.linkProgram(prog);
  return prog;
}

function drawFrame(gl, prog, uniforms) {
  gl.clear(gl.COLOR_BUFFER_BIT);
  gl.useProgram(prog);
  // bind pos attribute
  const posLoc = gl.getAttribLocation(prog, 'pos');
  gl.enableVertexAttribArray(posLoc);
  gl.vertexAttribPointer(posLoc, 2, gl.FLOAT, false, 0, 0);
  // set uniforms
  uniforms.forEach(([name, val]) => {
    const loc = gl.getUniformLocation(prog, name);
    if (loc !== null) gl.uniform1f(loc, val);
  });
  gl.drawArrays(gl.TRIANGLE_STRIP, 0, 4);
}

/* ═══════════════════════════════════════════════════════════════════════════
   AVATAR 1 — intensity02
   Concept: Massumi's pre-conscious affect — a field of warmth that continuously
   pools and shifts without ever resolving into a stable form.
   Technique: domain-warped fractal Brownian motion (FBM on FBM).
   The oval mask in GLSL uses the canvas aspect ratio so it fills correctly.
══════════════════════════════════════════════════════════════════════════════ */
(function intensity02() {
  const { gl, canvas } = buildGL('c-intensity');

  const frag = `
    precision highp float;
    varying vec2 vUV;
    uniform float uT;
    uniform float uAR; /* width / height */

    /* --- noise helpers --- */
    vec2 hash2(vec2 p){
      p = vec2(dot(p,vec2(127.1,311.7)), dot(p,vec2(269.5,183.3)));
      return fract(sin(p)*43758.5453);
    }
    float vnoise(vec2 p){
      vec2 i=floor(p), f=fract(p), u=f*f*(3.-2.*f);
      float a=dot(hash2(i),          f);
      float b=dot(hash2(i+vec2(1,0)),f-vec2(1,0));
      float c=dot(hash2(i+vec2(0,1)),f-vec2(0,1));
      float d=dot(hash2(i+vec2(1,1)),f-vec2(1,1));
      return mix(mix(a,b,u.x),mix(c,d,u.x),u.y)*0.5+0.5;
    }
    float fbm(vec2 p){
      float v=0.,a=.5;
      mat2 R=mat2(.8,.6,-.6,.8);
      for(int i=0;i<5;i++){ v+=a*vnoise(p); p=R*p*2.1; a*=.5; }
      return v;
    }

    void main(){
      /* aspect-corrected UV centred at 0,0 */
      vec2 uv = (vUV*2.-1.) * vec2(uAR, 1.);

      /* oval mask: x scaled by aspect ratio so oval fits frame */
      float rx = uAR * 0.82;
      float ry = 0.82;
      float oval = (uv.x*uv.x)/(rx*rx) + (uv.y*uv.y)/(ry*ry);
      float mask = 1. - smoothstep(0.80, 1.02, oval);
      if(mask < 0.001){ gl_FragColor=vec4(0.); return; }

      float t = uT * 0.15;

      /* two-layer domain warp */
      vec2 q = vec2(fbm(uv*1.2 + t),
                    fbm(uv*1.2 + vec2(4.1,2.7) + t*.8));
      vec2 r2= vec2(fbm(uv*1.1 + 3.8*q + vec2(1.7,9.2) + t*.5),
                    fbm(uv*1.1 + 3.8*q + vec2(8.3,2.8) + t*.3));
      float f = fbm(uv + 3.5*r2 + t*.2);
      f = f*f*f + .55*f*f + .5*f;

      /* palette: deep navy → warm gold → pale cream */
      vec3 col = mix(vec3(.04,.10,.22), vec3(.96,.88,.40), clamp(f*2.2,0.,1.));
      col = mix(col, vec3(.99,.96,.80), clamp((f-.45)*2.5,0.,1.));

      /* radial vignette — brightest at centre */
      float rLen = sqrt((uv.x*uv.x)/(uAR*uAR) + uv.y*uv.y);
      col *= .45 + .55*(1.-rLen*.85);

      /* soft edge feather */
      float alpha = mask * (0.55 + 0.45*smoothstep(0.,0.35,f));
      gl_FragColor = vec4(col * alpha, alpha);
    }
  `;

  const prog = buildProgram(gl, frag);
  const AR = canvas.width / canvas.height;
  let t = Math.random() * 100;

  function loop() {
    requestAnimationFrame(loop);
    t += 0.016;
    drawFrame(gl, prog, [['uT', t], ['uAR', AR]]);
  }
  loop();
  setTimeout(() => { canvas.style.opacity = '1'; canvas.style.transition = 'opacity 1.4s ease'; }, 200);
})();


/* ═══════════════════════════════════════════════════════════════════════════
   AVATAR 2 — extraction05
   Concept: Platform capitalism extracting affect from bodies.
   A downward spiral vortex with silver particle dots raining into a void.
   Built simply and reliably — no complex loops that might silently fail.
══════════════════════════════════════════════════════════════════════════════ */
(function extraction05() {
  const { gl, canvas } = buildGL('c-extraction');

  const frag = `
    precision highp float;
    varying vec2 vUV;
    uniform float uT;
    uniform float uAR;

    float h(float n){ return fract(sin(n)*43758.5453); }
    float h2(vec2 p){ return fract(sin(dot(p,vec2(127.1,311.7)))*43758.5453); }

    float vnoise(vec2 p){
      vec2 i=floor(p), f=fract(p), u=f*f*(3.-2.*f);
      return mix(mix(h2(i),h2(i+vec2(1,0)),u.x),
                 mix(h2(i+vec2(0,1)),h2(i+vec2(1,1)),u.x),u.y);
    }

    void main(){
      vec2 uv = (vUV*2.-1.) * vec2(uAR, 1.);

      /* oval mask */
      float rx = uAR * 0.84;
      float oval = (uv.x*uv.x)/(rx*rx) + uv.y*uv.y/(0.84*0.84);
      float mask = 1. - smoothstep(0.80, 1.02, oval);
      if(mask < 0.001){ gl_FragColor=vec4(0.); return; }

      float t = uT * 0.20;
      float r = length(uv);
      float ang = atan(uv.y, uv.x);

      /* ── VORTEX SPIRAL ── */
      /* spin speed increases toward centre = extraction pull */
      float spin = ang - t * 1.6 + r * 4.2;
      float vortex = sin(spin * 3.5) * .5 + .5;
      /* hollow eye at very centre, fade at edge */
      vortex *= smoothstep(0.0, 0.50, r);
      vortex *= 1. - smoothstep(0.38, 0.84, r);

      float turb = vnoise(uv * 3.2 + vec2(t*.6, -t*.35)) * .5 + .5;

      /* void at centre — darkens strongly near origin */
      float voidDepth = 1. - smoothstep(0., 0.28, r);

      /* ── SILVER PARTICLE DOTS ── */
      /* 15 particles: column index 0..4, row 0..2 */
      float pts = 0.;
      for(int row=0; row<3; row++){
        for(int col=0; col<5; col++){
          float fi = float(row)*5. + float(col);
          /* x: spread across width, slight lateral sway */
          float px = -0.60 + float(col)*0.30 + sin(fi*2.1 + t*.5)*0.05;
          /* y: start above, rain downward, loop */
          float spd = 0.11 + h(fi)*0.07;
          float phase = h(fi + 7.3);
          float py = 0.85 - mod(t * spd + phase * 1.5, 1.7);
          /* fade as they approach void */
          float fade = smoothstep(-0.1, 0.6, py);
          float d = length(uv - vec2(px, py));
          pts += (1. - smoothstep(0.015, 0.038, d)) * fade;
        }
      }
      pts = clamp(pts, 0., 1.);

      /* ── COLOUR ── */
      vec3 vortexCol = mix(
        vec3(0.50, 0.03, 0.20),   /* deep crimson */
        vec3(1.00, 0.22, 0.50),   /* hot pink */
        clamp(vortex*1.6 + turb*0.4 - 0.1, 0., 1.)
      );
      /* void eats colour at centre */
      vortexCol = mix(vortexCol, vec3(0.01,0.01,0.03), voidDepth);

      /* silver overlay for particles */
      vec3 col = mix(vortexCol, vec3(0.78, 0.85, 0.90), pts);

      /* very faint field base so interior isn't fully black */
      col = mix(vec3(0.04,0.02,0.10), col,
                clamp(vortex*1.2 + pts*0.8 + 0.12, 0., 1.));

      float alpha = mask * (vortex*0.75 + pts*0.70 + turb*0.10 + 0.08);
      alpha = clamp(alpha, 0., 0.88);

      gl_FragColor = vec4(col * alpha, alpha);
    }
  `;

  const prog = buildProgram(gl, frag);
  const AR = canvas.width / canvas.height;
  let t = Math.random() * 100;

  function loop() {
    requestAnimationFrame(loop);
    t += 0.016;
    drawFrame(gl, prog, [['uT', t], ['uAR', AR]]);
  }
  loop();
  setTimeout(() => { canvas.style.opacity = '1'; canvas.style.transition = 'opacity 1.4s ease'; }, 500);
})();


/* ═══════════════════════════════════════════════════════════════════════════
   AVATAR 3 — glitch_24
   Concept: Corrupted digital time — CRT screen tearing, RGB fringing,
   scanline displacement, noise blocks regenerating every frame.
══════════════════════════════════════════════════════════════════════════════ */
(function glitch24() {
  const { gl, canvas } = buildGL('c-glitch');

  const frag = `
    precision highp float;
    varying vec2 vUV;
    uniform float uT;
    uniform float uAR;

    float h(float n)  { return fract(sin(n)*43758.5453); }
    float h2(vec2 p)  { return fract(sin(dot(p,vec2(127.1,311.7)))*43758.5453); }
    float vnoise(vec2 p){
      vec2 i=floor(p),f=fract(p),u=f*f*(3.-2.*f);
      return mix(mix(h2(i),h2(i+vec2(1,0)),u.x),
                 mix(h2(i+vec2(0,1)),h2(i+vec2(1,1)),u.x),u.y);
    }

    void main(){
      vec2 uv = vUV; /* 0..1 */
      vec2 c  = uv*2.-1.;
      vec2 ca = c * vec2(uAR, 1.);

      /* oval mask */
      float rx = uAR * 0.84;
      float oval = (ca.x*ca.x)/(rx*rx) + ca.y*ca.y/(0.84*0.84);
      float mask = 1. - smoothstep(0.80, 1.02, oval);
      if(mask < 0.001){ gl_FragColor=vec4(0.); return; }

      float t = uT;

      /* ── SCANLINE SLICE TEARS ── */
      float sliceRow  = floor(uv.y * 20.0);
      float sliceSeed = h(sliceRow + floor(t * 6.0) * 0.37);
      float tear      = step(0.80, sliceSeed) * h(sliceRow*17.3 + t*1.1) * 0.16;
      float uvX       = uv.x + tear * (h(sliceRow + t*1.8) - 0.5);

      /* micro-jitter on random scanlines */
      float jSeed = h(floor(uv.y*90.) + floor(t*15.)*0.5);
      uvX += (step(0.93, jSeed) - 0.5) * 0.022;
      uvX  = clamp(uvX, 0., 1.);

      vec2 uvD = vec2(uvX, uv.y);

      /* ── RGB CHANNEL ABERRATION ── */
      float ca2 = 0.013 + sin(t*0.85)*0.005;
      vec2 uvR = vec2(clamp(uvD.x+ca2,0.,1.), uvD.y);
      vec2 uvB = vec2(clamp(uvD.x-ca2,0.,1.), uvD.y);

      /* ── COLOURED HORIZONTAL BANDS (corrupted "content") ── */
      float band    = floor(uvD.y * 8.0);
      float bandTag = h(band + 0.5);

      float R=0.,G=0.,B=0.;

      /* teal bands */
      float isTeal = step(0.55,bandTag)*step(bandTag,0.70);
      R += isTeal * 0.18 * vnoise(uvR*vec2(7.,1.)+t*.4);
      G += isTeal * 0.88 * vnoise(uvD*vec2(7.,1.)+t*.4);
      B += isTeal * 0.82 * vnoise(uvB*vec2(7.,1.)+t*.4);

      /* pink bands */
      float isPink = step(0.28,bandTag)*step(bandTag,0.43);
      R += isPink * 0.92 * vnoise(uvR*vec2(5.,1.)-t*.3);
      G += isPink * 0.14 * vnoise(uvD*vec2(5.,1.));
      B += isPink * 0.40 * vnoise(uvB*vec2(5.,1.));

      /* yellow band */
      float isYellow = step(0.72,bandTag)*step(bandTag,0.87);
      R += isYellow * 0.95 * vnoise(uvR*vec2(6.,1.)+t*.5);
      G += isYellow * 0.86 * vnoise(uvD*vec2(6.,1.)+t*.5);
      B += isYellow * 0.20;

      /* white flash band */
      float isWhite = step(0.12,bandTag)*step(bandTag,0.20);
      R += isWhite * 0.72;
      G += isWhite * 0.72;
      B += isWhite * 0.72;

      vec3 col = vec3(R, G, B);

      /* ── NOISE BLOCKS (regenerate at ~5fps) ── */
      float blockT = floor(t * 5.0);
      for(int i=0;i<5;i++){
        float fi=float(i);
        float bx = h(fi*7.3 + blockT);
        float by = h(fi*13.1+ blockT*1.3);
        float bw = 0.05 + h(fi*3.7)*0.14;
        float bh = 0.04 + h(fi*5.2)*0.10;
        if(uvD.x>bx && uvD.x<bx+bw && uvD.y>by && uvD.y<by+bh){
          vec3 nc = mix(
            mix(vec3(0.05,0.75,0.71), vec3(1.,0.24,0.51), h(fi+blockT)),
            vec3(h(fi+blockT*.7), h(fi*2.+blockT*.5), h(fi*3.+blockT*.3)),
            0.35
          );
          col = mix(col, nc, 0.92);
        }
      }

      /* ── SCANLINES ── */
      float scan = sin(uv.y * 200.0 + t) * 0.5 + 0.5;
      col *= 0.80 + scan * 0.20;

      /* ── VIGNETTE ── */
      float rr = length(ca) / uAR;
      col *= 1. - rr * 0.55;

      /* ── DARK BASE ── */
      float brightness = clamp(R+G+B, 0.,1.)*0.65 + 0.18;
      col = mix(vec3(0.01,0.03,0.07), col, brightness);

      float alpha = mask * 0.82;
      gl_FragColor = vec4(col * alpha, alpha);
    }
  `;

  const prog = buildProgram(gl, frag);
  const AR = canvas.width / canvas.height;
  let t = Math.random() * 100;

  function loop() {
    requestAnimationFrame(loop);
    t += 0.016;
    drawFrame(gl, prog, [['uT', t], ['uAR', AR]]);
  }
  loop();
  setTimeout(() => { canvas.style.opacity = '1'; canvas.style.transition = 'opacity 1.4s ease'; }, 800);
})();


/* ═══════════════════════════════════════════════════════════════════════════
   AMBIENT DRIFT — gently float each avatar wrapper using CSS transform.
   Does NOT alter top/right positioning — only adds a small translate.
══════════════════════════════════════════════════════════════════════════════ */
(function ambientDrift() {
  const avatars = [
    { el: document.getElementById('av-intensity'),  fx: 0.33, fy: 0.25, ax: 5, ay: 7, ph: 0.0 },
    { el: document.getElementById('av-extraction'), fx: 0.28, fy: 0.21, ax: 4, ay: 5, ph: 1.8 },
    { el: document.getElementById('av-glitch'),     fx: 0.26, fy: 0.20, ax: 6, ay: 5, ph: 3.4 },
  ];

  let t = 0;
  // We track the CSS animation's final translateY and blend drift on top.
  // By the time drift runs the CSS animation has settled (animation-delay + 1s).
  // We override transform entirely — the fade-in animation has already fired.

  function drift() {
    requestAnimationFrame(drift);
    t += 0.016;
    avatars.forEach(av => {
      const dx = Math.sin(t * av.fx + av.ph)       * av.ax;
      const dy = Math.sin(t * av.fy + av.ph + 1.2) * av.ay;
      av.el.style.transform = `translate(${dx}px, ${dy}px)`;
    });
  }

  // Start drift after all CSS fade-ins complete (longest delay = 1s + 1s anim = 2s)
  setTimeout(drift, 2100);
})();

window.addEventListener('resize', () => location.reload());
</script>
</body>
</html>
