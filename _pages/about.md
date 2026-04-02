---
layout: about
title: ""
permalink: /
nav: false
news: false
selected_papers: false
social: false
---

<style>
@import url('https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=Space+Mono:wght@400;700&family=Lora:ital,wght@0,400;0,500;1,400&display=swap');

:root {
  --hero-bg: #1e2a1a;
  --accent: #7a9e6e;
  --accent-soft: #96b88a;
  --accent-muted: #b5cca8;
}

body { overflow-x: hidden; }

.container, .container-fluid, .container-md,
main, #main-content, .col, .col-md,
.row, .wrapper, .post, .profile {
  max-width: 100% !important;
  width: 100% !important;
  padding: 0 !important;
  margin: 0 !important;
  float: none !important;
}

.page {
  font-family: 'Lora', Georgia, serif;
  width: 100vw;
  position: relative;
  left: 50%;
  margin-left: -50vw;
  overflow-x: hidden;
}

.page *, .page *::before, .page *::after { box-sizing: border-box; }

.post { padding: 0 !important; margin: 0 !important; }
article { padding: 0 !important; margin: 0 !important; }
.post-header { display: none !important; }
.navbar, nav.navbar { display: none !important; }
.p-name, .sidebar-header, .profile-name { display: none !important; }

/* ── SCROLL PROGRESS ── */
.scroll-bar {
  position: fixed;
  top: 0; left: 0;
  height: 3px;
  width: 0%;
  background: var(--accent-soft);
  z-index: 999999;
  transition: width 0.05s linear;
  pointer-events: none;
  box-shadow: 0 0 8px rgba(150,184,138,0.65);
}

/* ── NAV ── */
.site-nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 99999;
  background: rgba(30, 42, 26, 0.9);
  backdrop-filter: blur(12px);
  display: flex;
  gap: 2rem;
  align-items: center;
  justify-content: flex-end;
  height: 52px;
  padding: 0 3rem;
}
.site-nav a {
  font-family: 'Space Mono', monospace;
  font-size: 11px;
  color: rgba(181,204,168,0.5);
  text-decoration: none;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  transition: color 0.2s;
}
.site-nav a:hover { color: var(--accent-muted); }

/* ── HERO ── */
.hero {
  background: var(--hero-bg);
  min-height: 100vh;
  width: 100vw;
  display: flex;
  align-items: center;
  padding: 0 6vw;
  position: relative;
  overflow: hidden;
}

.floor-grid {
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 240px;
  background-image:
    linear-gradient(rgba(122,158,110,0.13) 1px, transparent 1px),
    linear-gradient(90deg, rgba(122,158,110,0.13) 1px, transparent 1px);
  background-size: 50px 30px;
  transform: perspective(500px) rotateX(55deg);
  transform-origin: bottom;
  z-index: 2;
}
.floor-glow {
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 240px;
  background: linear-gradient(0deg, rgba(40,70,30,0.22), transparent);
  border-top: 1px solid rgba(122,158,110,0.2);
  z-index: 2;
}

.hero-blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  pointer-events: none;
  z-index: 1;
}
.hero-blob-a {
  width: 480px; height: 480px;
  background: rgba(60,100,45,0.25);
  top: -120px; right: 5%;
}
.hero-blob-b {
  width: 300px; height: 300px;
  background: rgba(100,140,60,0.14);
  bottom: 12%; right: 30%;
}

.ui-dots {
  position: absolute;
  top: 16px; right: 20px;
  display: flex;
  gap: 5px;
  z-index: 10;
}
.ui-dots span { width: 6px; height: 6px; border-radius: 50%; }

/* ── AVATARS ── */
.av {
  position: absolute;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 3px;
  z-index: 5;
  opacity: 0;
  animation: avFloat 0.7s ease forwards;
}
@keyframes avFloat {
  from { opacity: 0; transform: translateY(14px); }
  to   { opacity: 1; transform: translateY(0); }
}
.av-body {
  border-radius: 50% 50% 40% 40%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 16px;
}
.av-shadow { border-radius: 50%; height: 5px; }
.av-label {
  font-family: 'Space Mono', monospace;
  font-size: 8px;
  letter-spacing: 0.05em;
  background: rgba(0,0,0,0.38);
  padding: 1px 5px;
  border-radius: 2px;
  white-space: nowrap;
}
.speech {
  position: absolute;
  background: rgba(255,255,255,0.07);
  border: 0.5px solid rgba(255,255,255,0.14);
  padding: 3px 8px;
  font-size: 8px;
  font-family: 'Space Mono', monospace;
  color: rgba(255,255,255,0.55);
  white-space: nowrap;
  border-radius: 6px 6px 6px 0;
}

/* ── HERO CONTENT ── */
.hero-content {
  position: relative;
  z-index: 10;
  display: flex;
  flex-direction: column;
  gap: 14px;
  max-width: 600px;
}
.hero-name {
  font-family: 'DM Serif Display', Georgia, serif;
  font-size: clamp(44px, 8vw, 90px);
  font-weight: 400;
  line-height: 0.92;
  white-space: nowrap;
  letter-spacing: -0.01em;
  margin: 0;
}
.hero-name .first { color: var(--accent-muted); }
.hero-name .rest { color: #e8f0e2; }
.hero-name em { font-style: italic; color: rgba(220,235,210,0.48); }
.hero-desc {
  font-size: clamp(14px, 2vw, 18px);
  color: rgba(181,204,168,0.42);
  font-style: italic;
  line-height: 1.6;
  margin: 0;
}
.hero-btn { margin-top: 10px; }
.hero-btn a {
  font-family: 'Space Mono', monospace;
  font-size: 11px;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: #1e2a1a;
  background: var(--accent-soft);
  padding: 12px 28px;
  text-decoration: none;
  display: inline-block;
  transition: background 0.2s;
}
.hero-btn a:hover { background: var(--accent-muted); }

/* ── ABOUT ── */
.about-section {
  background: #f7f3ec;
  width: 100vw;
  padding: 130px max(2.5rem, 6vw) 140px;
  margin-top: -60px;
  clip-path: polygon(0 60px, 100% 0, 100% 100%, 0 100%);
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
}
.about-section::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image: repeating-linear-gradient(
    0deg,
    transparent,
    transparent 47px,
    rgba(90,110,70,0.05) 47px,
    rgba(90,110,70,0.05) 48px
  );
  pointer-events: none;
}

.section-label {
  font-size: 11px;
  letter-spacing: 0.28em;
  text-transform: uppercase;
  color: #5a6e48;
  margin-bottom: 2.5rem;
  font-style: normal;
  font-family: 'Space Mono', monospace;
  text-align: center;
  width: 100%;
  position: relative;
}

.about-inner {
  display: flex;
  gap: 7rem;
  align-items: flex-start;
  justify-content: center;
  flex-wrap: wrap;
  position: relative;
}

.about-img-wrap {
  flex-shrink: 0;
  transform: rotate(-4deg);
  background: #fff;
  padding: 8px 8px 32px;
  box-shadow: 2px 5px 22px rgba(60,70,40,0.13);
  position: relative;
  top: 12px;
}
.about-img {
  width: 230px;
  height: 298px;
  object-fit: cover;
  object-position: top;
  display: block;
}

.text-col {
  display: flex;
  flex-direction: column;
  gap: 1.4rem;
  max-width: 520px;
  transform: rotate(1.5deg);
  min-width: 280px;
  padding-top: 24px;
}
.about-text {
  font-size: 17px;
  line-height: 1.95;
  color: #3a3a28;
  margin: 0;
}

/* ── PUBLICATIONS ── */
@keyframes floatA { 0%,100%{transform:translateY(0px) rotate(-3deg);} 50%{transform:translateY(-18px) rotate(-3deg);} }
@keyframes floatB { 0%,100%{transform:translateY(0px) rotate(2deg);} 50%{transform:translateY(-14px) rotate(2deg);} }
@keyframes floatC { 0%,100%{transform:translateY(0px) rotate(-1.5deg);} 50%{transform:translateY(-20px) rotate(-1.5deg);} }
@keyframes floatD { 0%,100%{transform:translateY(0px) rotate(4deg);} 50%{transform:translateY(-12px) rotate(4deg);} }

.pubs-section {
  background: #fefcf8;
  min-height: 100vh;
  width: 100vw;
  color: #38342a;
  margin-top: -60px;
  clip-path: polygon(0 0, 100% 60px, 100% 100%, 0 100%);
  padding: 130px max(2.5rem, 6vw) 6rem;
  position: relative;
  overflow: hidden;
}
.pubs-section * { color: #38342a; }
.pubs-section a { color: #38342a !important; border-bottom: 0.5px solid rgba(56,52,42,0.28); text-decoration: none; }
.pubs-section a:hover { color: #4e6840 !important; border-bottom-color: #4e6840; }
.pubs-section .section-label { color: #4e6840; margin-bottom: 2rem; text-align: left; }

.pub-img-float {
  position: absolute;
  z-index: 2;
  overflow: hidden;
  border-radius: 4px;
  box-shadow: 0 8px 32px rgba(0,0,0,0.09);
  cursor: pointer;
}
.pub-img-float img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  opacity: 0.16;
  filter: grayscale(15%);
  transition: opacity 0.45s ease, transform 0.45s ease;
}
.pub-img-float:hover img {
  opacity: 0.9;
  transform: scale(1.04);
}

/*
  Reduced to ~2× original (1/3 less than previous 3× sizes).
  Carefully positioned in a two-column stack on the right so none overlap.
  Left column (b, c): right: 370px+
  Right column (a, d): right: 22px
  Vertical spacing checked so no two images share y-range.
*/
.pub-img-a { width: 320px; height: 230px; top: 110px;  right: 22px;  animation: floatA 8s  ease-in-out infinite; }
.pub-img-d { width: 280px; height: 258px; top: 400px;  right: 60px;  animation: floatD 7s  ease-in-out infinite; }
.pub-img-b { width: 260px; height: 330px; top: 110px;  right: 380px; animation: floatB 10s ease-in-out infinite; }
/* vr-space: tall container, object-fit:contain shows entire photo */
.pub-img-c { width: 280px; height: 380px; top: 490px;  right: 370px; animation: floatC 9s  ease-in-out infinite; }
.pub-img-c img { object-fit: contain; object-position: center; }

.pub-content { position: relative; z-index: 10; max-width: 660px; }

.pub-type-block { margin-bottom: 2.8rem; }
.pub-type-block:last-child { margin-bottom: 0; }
.pub-type-label {
  font-size: 10px;
  font-weight: 500;
  letter-spacing: 0.14em;
  text-transform: uppercase;
  margin-bottom: 1rem;
  padding: 4px 14px;
  display: inline-block;
  border-radius: 3px;
  font-family: 'Space Mono', monospace;
}
.type-chapters  .pub-type-label { background: #e8f0de; color: #3a5828; }
.type-articles  .pub-type-label { background: #deeae8; color: #265450; }
.type-reviews   .pub-type-label { background: #e8e8da; color: #4a4a28; }
.type-interview .pub-type-label { background: #e4e8d8; color: #3c4828; }

.pub-entry {
  font-size: 16px;
  line-height: 1.9;
  color: #38342a;
  margin-bottom: 0.9rem;
  font-family: 'Lora', serif;
}
.pub-entry:last-child { margin-bottom: 0; }
.pub-entry em { font-style: italic; }
.pub-entry a { color: inherit; text-decoration: none; border-bottom: 0.5px solid rgba(56,52,42,0.28); }
.pub-entry a:hover { border-bottom-color: #4e6840; color: #4e6840 !important; }

/* ── CV + CONTACT ── */
.cv-contact-section {
  background: #232d1e;
  min-height: 100vh;
  width: 100vw;
  display: grid;
  grid-template-columns: 1fr 1px 1fr;
  position: relative;
  overflow: hidden;
}

.cv-blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(90px);
  pointer-events: none;
  z-index: 0;
}
.cv-blob-a {
  width: 500px; height: 500px;
  background: rgba(60,100,45,0.15);
  top: -120px; left: -100px;
}
.cv-blob-b {
  width: 380px; height: 380px;
  background: rgba(90,130,60,0.1);
  bottom: -80px; right: -80px;
}

.cv-top-stripe {
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 3px;
  background: var(--accent-soft);
  z-index: 10;
}

.cv-divider {
  background: rgba(122,158,110,0.16);
  align-self: stretch;
  position: relative;
  z-index: 2;
}

.cv-panel {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 6rem max(2rem, 5vw) 6rem max(2.5rem, 6vw);
  position: relative;
  z-index: 2;
}
.cv-panel .section-label {
  color: rgba(150,184,138,0.62);
  text-align: left;
  margin-bottom: 2rem;
}
.cv-download {
  font-family: 'Space Mono', monospace;
  font-size: 11px;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: #232d1e;
  background: var(--accent-soft);
  text-decoration: none;
  padding: 14px 32px;
  display: inline-flex;
  align-items: center;
  gap: 10px;
  transition: background 0.2s;
  width: fit-content;
}
.cv-download:hover { background: var(--accent-muted); color: #232d1e; }
.cv-download::after { content: '↓'; font-size: 16px; }

.cv-watermark {
  position: absolute;
  right: -10px;
  bottom: -30px;
  font-family: 'DM Serif Display', Georgia, serif;
  font-size: 220px;
  color: rgba(122,158,110,0.05);
  line-height: 1;
  pointer-events: none;
  user-select: none;
  z-index: 1;
}

.contact-panel {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 6rem max(2.5rem, 6vw) 6rem max(2rem, 5vw);
  position: relative;
  z-index: 2;
}
.contact-panel .section-label {
  color: rgba(150,184,138,0.62);
  text-align: left;
  margin-bottom: 2rem;
}
.contact-grid {
  display: flex;
  flex-direction: column;
  gap: 0;
  max-width: 420px;
}
.contact-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1.3rem 0;
  border-bottom: 0.5px solid rgba(122,158,110,0.15);
  text-decoration: none;
  color: rgba(215,228,208,0.8);
  transition: padding-left 0.25s, color 0.2s;
}
.contact-row:first-child { border-top: 0.5px solid rgba(122,158,110,0.15); }
.contact-row:hover { padding-left: 0.65rem; color: var(--accent-muted); }
.contact-label {
  font-family: 'Space Mono', monospace;
  font-size: 9px;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: rgba(150,184,138,0.4);
  min-width: 100px;
}
.contact-value {
  font-family: 'Lora', serif;
  font-size: 16px;
  font-style: italic;
  color: inherit;
  flex: 1;
  padding: 0 1rem;
}
.contact-arrow {
  font-family: 'Space Mono', monospace;
  font-size: 13px;
  color: rgba(150,184,138,0.36);
  transition: transform 0.2s, color 0.2s;
}
.contact-row:hover .contact-arrow { transform: translateX(5px); color: var(--accent-muted); }

/* ── MOBILE ── */
@media (max-width: 640px) {
  .site-nav { justify-content: flex-start; padding: 0 1.5rem; gap: 1.25rem; }
  .site-nav a { font-size: 9px; }
  .hero { padding: 0 1.5rem; align-items: flex-end; padding-bottom: 70px; min-height: 100svh; }
  .hero-name { white-space: normal; }
  .av { transform: scale(0.72); transform-origin: top center; }
  .av-1 { top: 10% !important; right: 2% !important; }
  .av-2 { top: 8% !important; right: 40% !important; }
  .av-3 { display: none; }
  .about-section { clip-path: polygon(0 30px, 100% 0, 100% 100%, 0 100%); padding: 80px 1.5rem 80px; margin-top: -30px; }
  .about-inner { flex-direction: column; align-items: center; gap: 2.5rem; }
  .about-img-wrap { transform: rotate(-2deg); }
  .about-img { width: 190px; height: 246px; }
  .text-col { transform: rotate(1deg); max-width: 100%; min-width: unset; }
  .about-text { font-size: 16px; }
  .pubs-section { clip-path: polygon(0 0, 100% 30px, 100% 100%, 0 100%); padding-top: 80px; margin-top: -30px; }
  .pub-entry { font-size: 14px; }
  .pub-img-float { display: none; }
  .cv-contact-section { grid-template-columns: 1fr; }
  .cv-divider { display: none; }
  .cv-panel { padding: 5rem 1.5rem 3rem; }
  .contact-panel { padding: 2rem 1.5rem 5rem; }
  .contact-value { font-size: 14px; }
  .cv-watermark { font-size: 130px; }
}

@media (max-width: 900px) and (min-width: 641px) {
  .pub-img-a { width: 200px; height: 144px; right: 14px;  top: 100px; }
  .pub-img-d { width: 175px; height: 161px; top: 290px;   right: 38px; }
  .pub-img-b { width: 162px; height: 206px; top: 100px;   right: 238px; }
  .pub-img-c { width: 175px; height: 237px; top: 350px;   right: 231px; }
}
</style>

<div class="page">

<div class="scroll-bar" id="scrollBar"></div>

<nav class="site-nav">
  <a href="#about">About</a>
  <a href="#publications">Publications</a>
  <a href="#cv">CV</a>
  <a href="#contact">Contact</a>
</nav>

<!-- ═══════ HERO ═══════ -->
<div class="hero" id="hero">
  <div class="floor-grid"></div>
  <div class="floor-glow"></div>
  <div class="hero-blob hero-blob-a"></div>
  <div class="hero-blob hero-blob-b"></div>

  <div class="ui-dots">
    <span style="background:#ff5f57;"></span>
    <span style="background:#febc2e;"></span>
    <span style="background:#28c840;"></span>
  </div>

  <!-- intensity02 — upper right -->
  <div class="av av-1" style="top:15%;right:13%;animation-delay:0.1s;">
    <div style="position:relative;">
      <div class="speech" style="top:-28px;left:30px;">researching 🔍</div>
    </div>
    <div class="av-body" style="width:40px;height:46px;background:rgba(255,200,0,0.18);border:1px solid rgba(255,200,0,0.4);">🌐</div>
    <div class="av-shadow" style="width:28px;background:rgba(255,200,0,0.1);"></div>
    <div class="av-label" style="color:rgba(255,230,150,0.85);">intensity02</div>
  </div>

  <!-- extraction_05 — upper centre -->
  <div class="av av-2" style="top:10%;right:39%;animation-delay:0.28s;">
    <div style="position:relative;">
      <div class="speech" style="top:-26px;right:28px;border-radius:6px 6px 0 6px;">digital media</div>
    </div>
    <div class="av-body" style="width:36px;height:42px;background:rgba(180,80,255,0.2);border:1px solid rgba(180,80,255,0.45);">👾</div>
    <div class="av-shadow" style="width:26px;background:rgba(180,80,255,0.12);"></div>
    <div class="av-label" style="color:rgba(220,160,255,0.85);">extraction_05</div>
  </div>

  <!-- interface_24 — mid right, well separated from others -->
  <div class="av av-3" style="top:44%;right:10%;animation-delay:0.48s;">
    <div style="position:relative;">
      <div class="speech" style="top:-26px;right:28px;border-radius:6px 6px 0 6px;">in the matrix</div>
    </div>
    <div class="av-body" style="width:34px;height:40px;background:rgba(255,120,200,0.18);border:1px solid rgba(255,120,200,0.4);">🧠</div>
    <div class="av-shadow" style="width:24px;background:rgba(255,120,200,0.1);"></div>
    <div class="av-label" style="color:rgba(255,180,230,0.85);">interface_24</div>
  </div>

  <div class="hero-content">
    <h1 class="hero-name">
      <span class="first">Mai</span><span class="rest"> W. <em>Ibrahim</em></span>
    </h1>
    <p class="hero-desc">is a media theorist &amp; researcher of digital cultures.</p>
    <div class="hero-btn"><a href="#about">Enter ↓</a></div>
  </div>
</div>

<!-- ═══════ ABOUT ═══════ -->
<div class="about-section" id="about">
  <p class="section-label">About</p>
  <div class="about-inner">
    <div class="about-img-wrap">
      <img class="about-img" src="/assets/img/prof_pic.jpg" alt="Mai W. Ibrahim" />
    </div>
    <div class="text-col">
      <p class="about-text">My research examines the relationship between digital media, pre-conscious intensities, and political economy. I investigate how digital media act upon the human body prior to conscious awareness, and how platform capitalism transforms that bodily register into a site of extraction.</p>
      <p class="about-text">My work engages a wide range of media, including virtual reality, brain-computer interfaces, social media, and video games.</p>
      <p class="about-text">I am currently a sessional instructor at McMaster University in Hamilton, Canada. I was a Postdoctoral Visitor at York University's Department of Communication and Media Studies in 2024–2025, where I researched toxicity in video games. I completed my PhD in Communication, Rhetoric, and Digital Media at North Carolina State University.</p>
    </div>
  </div>
</div>

<!-- ═══════ PUBLICATIONS ═══════ -->
<div class="pubs-section" id="publications">
  <div class="pub-img-float pub-img-a">
    <img src="/assets/img/vr-headset.jpg" alt="VR headset" />
  </div>
  <div class="pub-img-float pub-img-b">
    <img src="/assets/img/vr-museum.jpg" alt="VR museum" />
  </div>
  <div class="pub-img-float pub-img-c">
    <img src="/assets/img/vr-space.jpg" alt="VR space" />
  </div>
  <div class="pub-img-float pub-img-d">
    <img src="/assets/img/bci-headset.jpg" alt="BCI headset" />
  </div>

  <div class="pub-content">
    <p class="section-label">Research &amp; Publications</p>

    <div class="pub-type-block type-chapters">
      <span class="pub-type-label">Book Chapters</span>
      <p class="pub-entry">Ibrahim, M. (2025). <a href="/assets/pdf/embodiment-social-vr.pdf" target="_blank">Embodiment and Representation in Social VR</a>. In Grant Bollmer, Katherine Guinness, and Yiğit Soncul (Eds.), <em>Handbook of Digital Cultures</em> (pp. 307–314). De Gruyter.</p>
      <p class="pub-entry">Ibrahim, M. (2024). <a href="/assets/pdf/tahrir-square.pdf" target="_blank">Exploring Tahrir Square as an Intra-Active Hybrid Space</a>. In Joanna Godlewicz-Adamiec &amp; Pawel Piszczatowski (Eds.), <em>Re-Thinking Agency: Non-Anthropocentric Approaches</em> (pp. 21–33). Vandenhoeck &amp; Ruprecht.</p>
      <p class="pub-entry">Ibrahim, M. (2023). <a href="/assets/pdf/posthuman-bci-vr.pdf" target="_blank">Posthuman Subjectivity in BCI-VR Entanglement</a>. In Veljko Dubljević &amp; Allen Coin (Eds.), <em>Policy, Identity, and Neurotechnology</em> (pp. 11–25). Springer.</p>
      <p class="pub-entry">Ibrahim, M. &amp; Dubljević, V. (2023). <a href="/assets/pdf/neurofeminism-bci.pdf" target="_blank">Neurofeminism in BCI and BBI Ethics as a Prelude to Political Neuroethics</a>. In Michele Farisco (Ed.), <em>Neuroethics and Cultural Diversity</em> (pp. 77–94). ISTE/Wiley.</p>
      <p class="pub-entry">Ibrahim, M. &amp; Dubljević, V. (2024). Prélude à la neuroéthique politique: neuroféminisme et éthique des ICM et ICC. <em>Neuroéthique et diversité culturelle</em>, p. 95. ISTE Group.</p>
    </div>

    <div class="pub-type-block type-articles">
      <span class="pub-type-label">Journal Articles</span>
      <p class="pub-entry">Ibrahim, M. (Accepted). Virtual Enchantment: Rethinking Engagement in Social VR Through the Better World Museum. <em>Convergence</em>.</p>
    </div>

    <div class="pub-type-block type-reviews">
      <span class="pub-type-label">Reviews</span>
      <p class="pub-entry">Ibrahim, M. (2021). Review of the book <a href="/assets/pdf/nihilism-review.pdf" target="_blank"><em>Nihilism and Technology</em></a>, by N. Gertz. <em>Communication Design Quarterly</em>, 9(1), 32–34.</p>
      <p class="pub-entry">Ibrahim, M. (2020). Review of the chapter <em>A Fast Food Civil Rights</em> in <em>Franchise</em>, by M. Chatelain. HASTAC.</p>
    </div>

    <div class="pub-type-block type-interview">
      <span class="pub-type-label">Interview</span>
      <p class="pub-entry">Ibrahim, M. (2020). Unraveling the World of "Franchise" [Interview with M. Chatelain]. HASTAC.</p>
    </div>
  </div>
</div>

<!-- ═══════ CV + CONTACT ═══════ -->
<div class="cv-contact-section" id="cv">
  <div class="cv-top-stripe"></div>
  <div class="cv-blob cv-blob-a"></div>
  <div class="cv-blob cv-blob-b"></div>

  <div class="cv-panel">
    <p class="section-label">CV</p>
    <a class="cv-download" href="/assets/pdf/cv.pdf" target="_blank">Download CV</a>
    <div class="cv-watermark">CV</div>
  </div>

  <div class="cv-divider"></div>

  <div class="contact-panel" id="contact">
    <p class="section-label">Contact</p>
    <div class="contact-grid">
      <a class="contact-row" href="mailto:mai.w.ibrahim@gmail.com">
        <span class="contact-label">Email</span>
        <span class="contact-value">mai.w.ibrahim@gmail.com</span>
        <span class="contact-arrow">→</span>
      </a>
      <a class="contact-row" href="https://bsky.app/profile/maiibrahim.bsky.social" target="_blank">
        <span class="contact-label">Bluesky</span>
        <span class="contact-value">@maiibrahim.bsky.social</span>
        <span class="contact-arrow">→</span>
      </a>
      <a class="contact-row" href="https://scholar.google.ca/citations?user=e39G1iYAAAAJ" target="_blank">
        <span class="contact-label">Google Scholar</span>
        <span class="contact-value">Mai W. Ibrahim</span>
        <span class="contact-arrow">→</span>
      </a>
    </div>
  </div>
</div>

</div>

<script>
(function() {
  var bar = document.getElementById('scrollBar');
  function onScroll() {
    var scrollTop = window.scrollY || document.documentElement.scrollTop;
    var docHeight = document.documentElement.scrollHeight - window.innerHeight;
    var pct = docHeight > 0 ? (scrollTop / docHeight) * 100 : 0;
    bar.style.width = pct + '%';
  }
  window.addEventListener('scroll', onScroll, { passive: true });
  onScroll();
})();
</script>
