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
  --hero-bg:      #0b1b2e;
  --navy:         #0f2540;
  --navy-soft:    #1a3a5c;
  --teal:         #0dbfb4;
  --teal-soft:    #35d4ca;
  --teal-muted:   #80e8e3;
  --pink:         #ff3d82;
  --pink-soft:    #ff6fa3;
  --pink-muted:   #ffaac9;
  --yellow:       #f5e27a;
  --yellow-soft:  #f9edaa;
  --yellow-muted: #fdf4d0;
}

body { overflow-x: hidden; }

.container,.container-fluid,.container-md,
main,#main-content,.col,.col-md,
.row,.wrapper,.post,.profile {
  max-width:100%!important;width:100%!important;
  padding:0!important;margin:0!important;float:none!important;
}

.page {
  font-family:'Lora',Georgia,serif;
  width:100vw;position:relative;left:50%;margin-left:-50vw;overflow-x:hidden;
}
.page *,.page *::before,.page *::after { box-sizing:border-box; }

.post  { padding:0!important;margin:0!important; }
article{ padding:0!important;margin:0!important; }
.post-header              { display:none!important; }
.navbar,nav.navbar        { display:none!important; }
.p-name,.sidebar-header,.profile-name { display:none!important; }

.scroll-bar {
  position:fixed;top:0;left:0;height:3px;width:0%;
  background:linear-gradient(90deg,#e8d46a,#f5e89a,#fdf4d0,#f5e27a,#e8d46a);
  z-index:999999;transition:width .05s linear;pointer-events:none;
  box-shadow:0 0 8px rgba(245,226,122,.55);
}

.site-nav {
  position:fixed;top:0;left:0;right:0;z-index:99999;
  background:rgba(11,27,46,.92);backdrop-filter:blur(14px);
  display:flex;gap:2rem;align-items:center;justify-content:flex-end;
  height:60px;padding:0 3rem;
  border-bottom:.5px solid rgba(13,191,180,.18);
}
.site-nav a {
  font-family:'Space Mono',monospace;font-size:12px;
  color:#ffffff;text-decoration:none;
  letter-spacing:.18em;text-transform:uppercase;transition:color .2s;
}
.site-nav a:hover { color:var(--teal-soft); }

.hero {
  background:var(--hero-bg);
  min-height:100vh;width:100vw;
  display:flex;align-items:center;
  padding:60px 6vw 0;
  position:relative;overflow:hidden;
}
.hero-blob { position:absolute;border-radius:50%;filter:blur(90px);pointer-events:none;z-index:1; }
.hero-blob-a { width:500px;height:500px;background:rgba(255,61,130,.14);top:-140px;right:3%; }
.hero-blob-b { width:320px;height:320px;background:rgba(13,191,180,.12);bottom:10%;right:28%; }
.hero-blob-c { width:260px;height:260px;background:rgba(245,226,122,.07);top:20%;left:5%; }

.ui-dots { position:absolute;top:18px;right:20px;display:flex;gap:5px;z-index:10; }
.ui-dots span { width:6px;height:6px;border-radius:50%; }

.av {
  position:absolute;display:flex;flex-direction:column;
  align-items:center;gap:4px;z-index:5;
  opacity:0;animation:avFloat .7s ease forwards;
}
@keyframes avFloat {
  from{opacity:0;transform:translateY(14px);}
  to  {opacity:1;transform:translateY(0);}
}
.av-label {
  font-family:'Space Mono',monospace;font-size:9.5px;letter-spacing:.05em;
  background:rgba(0,0,0,.38);padding:2px 7px;border-radius:2px;white-space:nowrap;
}

.hero-content {
  position:relative;z-index:10;
  display:flex;flex-direction:column;gap:14px;max-width:600px;
}
.hero-name {
  font-family:'DM Serif Display',Georgia,serif;
  font-size:clamp(32px,5.4vw,62px);font-weight:400;
  line-height:.92;white-space:nowrap;letter-spacing:-.01em;margin:0;
}
.hero-name .first { color:var(--yellow-soft); }
.hero-name .rest  { color:#e0f0f8; }
.hero-name em     { font-style:italic;color:rgba(13,191,180,.45); }

.hero-desc { font-size:clamp(14px,2vw,18px);color:#ffffff;font-style:italic;line-height:1.6;margin:0; }
.hero-btn { margin-top:10px; }
.hero-btn a {
  font-family:'Space Mono',monospace;font-size:11px;
  letter-spacing:.15em;text-transform:uppercase;
  color:#0b1b2e;background:var(--teal);
  padding:12px 28px;text-decoration:none;display:inline-block;transition:background .2s;
}
.hero-btn a:hover { background:var(--teal-soft); }

.about-section {
  background:#f0f8fa;width:100vw;
  padding:130px max(2.5rem,6vw) 140px;
  margin-top:-60px;
  clip-path:polygon(0 60px,100% 0,100% 100%,0 100%);
  min-height:100vh;display:flex;flex-direction:column;
  justify-content:center;align-items:center;position:relative;
}
.section-label {
  font-size:17px;letter-spacing:.2em;text-transform:uppercase;
  color:var(--pink);margin-bottom:2.5rem;
  font-style:normal;font-family:'Space Mono',monospace;
  text-align:center;width:100%;
}
.about-inner {
  display:flex;gap:9rem;align-items:center;
  justify-content:center;flex-wrap:wrap;position:relative;
}
.about-img-wrap { flex-shrink:0;transform:rotate(-6deg);position:relative;align-self:center; }
.about-img {
  width:230px;height:298px;object-fit:cover;object-position:top;display:block;border-radius:3px;
  box-shadow:0 0 0 3px #fff,6px 10px 36px rgba(255,61,130,.22),-2px -2px 0 1px rgba(13,191,180,.35);
}
.text-col { display:flex;flex-direction:column;gap:1.4rem;max-width:520px;transform:rotate(2.5deg);min-width:280px;padding-top:24px; }
.about-text { font-size:16px;line-height:1.95;color:#1a2e3a;margin:0; }

@keyframes floatA { 0%,100%{transform:translateY(0) rotate(-3deg);}  50%{transform:translateY(-18px) rotate(-3deg);} }
@keyframes floatB { 0%,100%{transform:translateY(0) rotate(2deg);}   50%{transform:translateY(-14px) rotate(2deg);} }
@keyframes floatC { 0%,100%{transform:translateY(0) rotate(-1.5deg);}50%{transform:translateY(-20px) rotate(-1.5deg);} }
@keyframes floatD { 0%,100%{transform:translateY(0) rotate(4deg);}   50%{transform:translateY(-12px) rotate(4deg);} }

.pubs-section {
  background:#fdfcff;min-height:100vh;width:100vw;color:#1a2e3a;
  margin-top:-60px;clip-path:polygon(0 0,100% 60px,100% 100%,0 100%);
  padding:130px max(2.5rem,6vw) 6rem;position:relative;overflow:hidden;
}
.pubs-section * { color:#1a2e3a; }
.pubs-section a { color:#1a2e3a!important;border-bottom:.5px solid rgba(26,46,58,.28);text-decoration:none; }
.pubs-section a:hover { color:var(--pink)!important;border-bottom-color:var(--pink); }
.pubs-section .section-label { color:var(--pink);margin-bottom:2rem;text-align:left;font-size:17px; }
.pub-img-float { position:absolute;z-index:2;overflow:hidden;border-radius:4px;box-shadow:0 8px 32px rgba(255,61,130,.1);cursor:pointer; }
.pub-img-float img { width:100%;height:100%;object-fit:cover;display:block;opacity:.14;filter:grayscale(10%);transition:opacity .45s ease,transform .45s ease; }
.pub-img-float:hover img { opacity:.88;transform:scale(1.04); }
.pub-img-a { width:320px;height:310px;top:90px;right:22px;animation:floatA 8s ease-in-out infinite; }
.pub-img-a img { object-fit:cover;object-position:top center; }
.pub-img-c { width:280px;height:380px;top:490px;right:370px;animation:floatC 9s ease-in-out infinite;background:transparent; }
.pub-img-c img { object-fit:cover;object-position:center;background:transparent; }
.pub-img-d { width:280px;height:258px;top:430px;right:60px;animation:floatD 7s ease-in-out infinite; }
.pub-img-b { width:260px;height:330px;top:110px;right:380px;animation:floatB 10s ease-in-out infinite; }
.pub-content { position:relative;z-index:10;max-width:660px; }
.pub-type-block { margin-bottom:2.8rem; }
.pub-type-block:last-child { margin-bottom:0; }
.pub-type-label {
  font-size:11px;font-weight:500;letter-spacing:.14em;text-transform:uppercase;
  margin-bottom:1rem;padding:5px 14px;display:inline-block;border-radius:3px;font-family:'Space Mono',monospace;
}
.type-chapters  .pub-type-label { background:#d0eef8;color:#0a5e78; }
.type-articles  .pub-type-label { background:#ffe5ef;color:var(--pink); }
.type-reviews   .pub-type-label { background:#fdf4d0;color:#7a6820; }
.type-interview .pub-type-label { background:#e8faf9;color:#0a7a74; }
.pub-entry { font-size:16px;line-height:1.9;color:#1a2e3a;margin-bottom:.9rem;font-family:'Lora',serif; }
.pub-entry:last-child { margin-bottom:0; }
.pub-entry em { font-style:italic; }
.pub-entry a { color:inherit;text-decoration:none;border-bottom:.5px solid rgba(26,46,58,.28); }
.pub-entry a:hover { border-bottom-color:var(--pink);color:var(--pink)!important; }

.cv-contact-section {
  background:#0b1b2e;min-height:100vh;width:100vw;
  display:grid;grid-template-columns:1fr 1px 1fr;position:relative;overflow:hidden;
}
.cv-blob { position:absolute;border-radius:50%;filter:blur(90px);pointer-events:none;z-index:0; }
.cv-blob-a { width:500px;height:500px;background:rgba(255,61,130,.12);top:-120px;left:-100px; }
.cv-blob-b { width:380px;height:380px;background:rgba(13,191,180,.1);bottom:-80px;right:-80px; }
.cv-blob-c { width:280px;height:280px;background:rgba(245,226,122,.05);top:40%;left:40%; }
.cv-top-stripe {
  position:absolute;top:0;left:0;right:0;height:3px;
  background:linear-gradient(90deg,#e8d46a,#f5e89a,#fdf4d0,#f5e27a,#e8d46a);z-index:10;
}
.cv-divider { background:rgba(13,191,180,.14);align-self:stretch;position:relative;z-index:2; }
.cv-panel { display:flex;flex-direction:column;justify-content:center;padding:6rem max(2rem,5vw) 6rem max(2.5rem,6vw);position:relative;z-index:2; }
.cv-panel .section-label { color:rgba(13,191,180,.62);text-align:left;margin-bottom:2rem;font-size:17px; }
.cv-download {
  font-family:'Space Mono',monospace;font-size:11px;letter-spacing:.18em;text-transform:uppercase;
  color:#0b1b2e;background:var(--teal);text-decoration:none;padding:14px 32px;
  display:inline-flex;align-items:center;gap:10px;transition:background .2s;width:fit-content;
}
.cv-download:hover { background:var(--teal-soft);color:#0b1b2e; }
.cv-download::after { content:'↓';font-size:16px; }
.contact-panel { display:flex;flex-direction:column;justify-content:center;padding:6rem max(2.5rem,6vw) 6rem max(2rem,5vw);position:relative;z-index:2; }
.contact-panel .section-label { color:rgba(13,191,180,.62);text-align:left;margin-bottom:2rem;font-size:17px; }
.contact-grid { display:flex;flex-direction:column;gap:0;max-width:420px; }
.contact-row {
  display:flex;align-items:center;justify-content:space-between;
  padding:1.3rem 0;border-bottom:.5px solid rgba(13,191,180,.15);
  text-decoration:none;transition:padding-left .25s,color .2s;
}
.contact-row:first-child { border-top:.5px solid rgba(13,191,180,.15); }
.contact-row:hover { padding-left:.65rem; }
.contact-label { font-family:'Space Mono',monospace;font-size:9px;letter-spacing:.18em;text-transform:uppercase;color:var(--teal);min-width:100px; }
.contact-value { font-family:'Lora',serif;font-size:16px;font-style:italic;color:#ffffff;flex:1;padding:0 1rem; }
.contact-arrow { font-family:'Space Mono',monospace;font-size:13px;color:rgba(13,191,180,.36);transition:transform .2s,color .2s; }
.contact-row:hover .contact-arrow { transform:translateX(5px);color:var(--teal-soft); }
.contact-row:hover .contact-value { color:var(--teal-muted); }

@media (max-width:640px) {
  .site-nav { justify-content:flex-start;padding:0 1.5rem;gap:1.25rem;height:56px; }
  .site-nav a { font-size:10px; }
  .hero { padding:56px 1.5rem 60px;align-items:center;min-height:100svh; }
  .hero-name { white-space:normal; }
  .hero-content { max-width:55%; }
  .av { transform:scale(.78);transform-origin:top left; }
  .about-section { clip-path:polygon(0 30px,100% 0,100% 100%,0 100%);padding:80px 1.5rem 80px;margin-top:-30px; }
  .about-inner { flex-direction:column;align-items:center;gap:2.5rem; }
  .about-img-wrap { transform:rotate(-3deg); }
  .about-img { width:190px;height:246px; }
  .text-col { transform:rotate(1.5deg);max-width:100%;min-width:unset; }
  .about-text { font-size:15px; }
  .section-label { font-size:15px; }
  .pubs-section { clip-path:polygon(0 0,100% 30px,100% 100%,0 100%);padding-top:80px;margin-top:-30px; }
  .pub-entry { font-size:15px; }
  .pub-img-float { display:none; }
  .cv-contact-section { grid-template-columns:1fr; }
  .cv-divider { display:none; }
  .cv-panel { padding:5rem 1.5rem 3rem; }
  .contact-panel { padding:2rem 1.5rem 5rem; }
  .contact-value { font-size:14px; }
}
@media (max-width:900px) and (min-width:641px) {
  .pub-img-a { width:200px;height:194px;right:14px;top:100px; }
  .pub-img-d { width:175px;height:161px;top:330px;right:38px; }
  .pub-img-b { width:162px;height:206px;top:100px;right:238px; }
  .pub-img-c { width:175px;height:237px;top:350px;right:231px; }
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

<div class="hero" id="hero">
  <div class="hero-blob hero-blob-a"></div>
  <div class="hero-blob hero-blob-b"></div>
  <div class="hero-blob hero-blob-c"></div>
  <div class="ui-dots">
    <span style="background:var(--teal);"></span>
    <span style="background:var(--pink);"></span>
    <span style="background:var(--yellow);"></span>
  </div>

  <!--
    Placement logic:
    - Hero name flexes to ~47% vh. With clamp(32px,5.4vw,62px) it is smaller than before.
    - intensity02 top:38% → its TOP is just barely above the name's first line.
    - extraction05 top:50% → sits at name's vertical midpoint.
    - glitch_24    top:61% → below the name.
    - "digital media" tag at top:44% between the first two avatars.
    - "researching" tag at top:73% below all three.
  -->

  <!-- intensity02 — YELLOW — intense bodily affect, energy radiating from body -->
  <div class="av" style="top:38%;right:10%;animation-delay:.10s;">
    <svg width="58" height="76" viewBox="0 0 58 76" fill="none" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <clipPath id="i2clip">
          <path d="M23 24 Q17 32 15 44 Q19 52 29 54 Q39 52 43 44 Q41 32 35 24 Z"/>
        </clipPath>
      </defs>
      <!-- VR headset -->
      <rect x="19" y="7"  width="20" height="11" rx="3"   fill="rgba(245,226,122,.20)" stroke="rgba(245,226,122,.82)" stroke-width="1.2"/>
      <rect x="21" y="9"  width="6"  height="6"  rx="1.5" fill="rgba(245,226,122,.55)"/>
      <rect x="30" y="9"  width="6"  height="6"  rx="1.5" fill="rgba(245,226,122,.55)"/>
      <line x1="19" y1="12" x2="13" y2="12" stroke="rgba(245,226,122,.48)" stroke-width="1.1"/>
      <line x1="39" y1="12" x2="45" y2="12" stroke="rgba(245,226,122,.48)" stroke-width="1.1"/>
      <!-- Neck -->
      <rect x="26" y="18" width="6"  height="5"  rx="1"   fill="rgba(245,226,122,.18)" stroke="rgba(245,226,122,.42)" stroke-width="1"/>
      <!-- Torso outline -->
      <path d="M23 24 Q17 32 15 44 Q19 52 29 54 Q39 52 43 44 Q41 32 35 24 Z"
            fill="rgba(245,226,122,.10)" stroke="rgba(245,226,122,.68)" stroke-width="1.3"/>
      <!-- Concentric pulse rings inside torso (intensity = pre-conscious bodily affect) -->
      <g clip-path="url(#i2clip)">
        <ellipse cx="29" cy="37" rx="3"  ry="3"   fill="none" stroke="rgba(245,226,122,.85)" stroke-width="1.3"/>
        <ellipse cx="29" cy="37" rx="6"  ry="5.5" fill="none" stroke="rgba(245,226,122,.58)" stroke-width="1.0"/>
        <ellipse cx="29" cy="37" rx="10" ry="9"   fill="none" stroke="rgba(245,226,122,.38)" stroke-width="0.9"/>
        <ellipse cx="29" cy="37" rx="14" ry="12"  fill="none" stroke="rgba(245,226,122,.20)" stroke-width="0.8"/>
      </g>
      <!-- Energy rays escaping outward — affect overflowing the body boundary -->
      <line x1="21" y1="27" x2="11" y2="19" stroke="rgba(245,226,122,.58)" stroke-width="1.1" stroke-linecap="round"/>
      <line x1="17" y1="32" x2="7"  y2="27" stroke="rgba(245,226,122,.44)" stroke-width="0.9" stroke-linecap="round"/>
      <line x1="15" y1="38" x2="4"  y2="37" stroke="rgba(245,226,122,.32)" stroke-width="0.8" stroke-linecap="round"/>
      <line x1="37" y1="27" x2="47" y2="19" stroke="rgba(245,226,122,.58)" stroke-width="1.1" stroke-linecap="round"/>
      <line x1="41" y1="32" x2="51" y2="27" stroke="rgba(245,226,122,.44)" stroke-width="0.9" stroke-linecap="round"/>
      <line x1="43" y1="38" x2="54" y2="37" stroke="rgba(245,226,122,.32)" stroke-width="0.8" stroke-linecap="round"/>
      <line x1="16" y1="45" x2="5"  y2="48" stroke="rgba(245,226,122,.25)" stroke-width="0.8" stroke-linecap="round"/>
      <line x1="42" y1="45" x2="53" y2="48" stroke="rgba(245,226,122,.25)" stroke-width="0.8" stroke-linecap="round"/>
      <!-- Arms raised — body fully activated -->
      <path d="M21 31 Q12 29 8 23"  fill="none" stroke="rgba(245,226,122,.65)" stroke-width="1.4" stroke-linecap="round"/>
      <path d="M37 31 Q46 29 50 23" fill="none" stroke="rgba(245,226,122,.65)" stroke-width="1.4" stroke-linecap="round"/>
      <!-- Legs -->
      <path d="M23 54 Q21 62 20 70" fill="none" stroke="rgba(245,226,122,.52)" stroke-width="1.4" stroke-linecap="round"/>
      <path d="M35 54 Q37 62 38 70" fill="none" stroke="rgba(245,226,122,.52)" stroke-width="1.4" stroke-linecap="round"/>
    </svg>
    <div style="width:38px;height:5px;border-radius:50%;background:rgba(245,226,122,.10);"></div>
    <div class="av-label" style="color:rgba(249,237,170,.9);">intensity02</div>
  </div>

  <!-- extraction05 — PINK — data extracted from the body as silver particles rising up -->
  <div class="av" style="top:50%;right:37%;animation-delay:.28s;">
    <svg width="58" height="76" viewBox="0 0 58 76" fill="none" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <clipPath id="e5clip">
          <path d="M23 24 Q17 32 15 44 Q19 52 29 54 Q39 52 43 44 Q41 32 35 24 Z"/>
        </clipPath>
      </defs>
      <!-- VR headset -->
      <rect x="19" y="7"  width="20" height="11" rx="3"   fill="rgba(255,61,130,.20)" stroke="rgba(255,61,130,.82)" stroke-width="1.2"/>
      <rect x="21" y="9"  width="6"  height="6"  rx="1.5" fill="rgba(255,61,130,.55)"/>
      <rect x="30" y="9"  width="6"  height="6"  rx="1.5" fill="rgba(255,61,130,.55)"/>
      <line x1="19" y1="12" x2="13" y2="12" stroke="rgba(255,61,130,.48)" stroke-width="1.1"/>
      <line x1="39" y1="12" x2="45" y2="12" stroke="rgba(255,61,130,.48)" stroke-width="1.1"/>
      <!-- Neck -->
      <rect x="26" y="18" width="6" height="5" rx="1" fill="rgba(255,61,130,.18)" stroke="rgba(255,61,130,.42)" stroke-width="1"/>
      <!-- Torso outline -->
      <path d="M23 24 Q17 32 15 44 Q19 52 29 54 Q39 52 43 44 Q41 32 35 24 Z"
            fill="rgba(255,61,130,.10)" stroke="rgba(255,61,130,.65)" stroke-width="1.3"/>
      <!-- Data grid inside — structured information held in the body -->
      <g clip-path="url(#e5clip)">
        <line x1="15" y1="30" x2="43" y2="30" stroke="rgba(255,61,130,.28)" stroke-width="0.7"/>
        <line x1="15" y1="35" x2="43" y2="35" stroke="rgba(255,61,130,.28)" stroke-width="0.7"/>
        <line x1="15" y1="40" x2="43" y2="40" stroke="rgba(255,61,130,.28)" stroke-width="0.7"/>
        <line x1="15" y1="45" x2="43" y2="45" stroke="rgba(255,61,130,.28)" stroke-width="0.7"/>
        <line x1="23" y1="24" x2="23" y2="54" stroke="rgba(255,61,130,.20)" stroke-width="0.6"/>
        <line x1="29" y1="24" x2="29" y2="54" stroke="rgba(255,61,130,.20)" stroke-width="0.6"/>
        <line x1="35" y1="24" x2="35" y2="54" stroke="rgba(255,61,130,.20)" stroke-width="0.6"/>
        <!-- Data nodes at intersections — being activated, about to leave -->
        <rect x="22" y="29" width="2.2" height="2.2" rx=".4" fill="rgba(255,61,130,.82)"/>
        <rect x="28" y="34" width="2.2" height="2.2" rx=".4" fill="rgba(255,111,163,.76)"/>
        <rect x="34" y="29" width="2.2" height="2.2" rx=".4" fill="rgba(255,61,130,.70)"/>
        <rect x="22" y="39" width="2.2" height="2.2" rx=".4" fill="rgba(255,111,163,.65)"/>
        <rect x="28" y="44" width="2.2" height="2.2" rx=".4" fill="rgba(255,61,130,.58)"/>
        <rect x="34" y="39" width="2.2" height="2.2" rx=".4" fill="rgba(255,111,163,.52)"/>
      </g>
      <!-- Extraction upward streams — dashed lines from body to collection node -->
      <line x1="22" y1="23" x2="27" y2="5"  stroke="rgba(255,61,130,.42)" stroke-width="0.85" stroke-linecap="round" stroke-dasharray="2.2 2"/>
      <line x1="29" y1="23" x2="29" y2="3"  stroke="rgba(255,61,130,.52)" stroke-width="0.95" stroke-linecap="round" stroke-dasharray="2.2 1.8"/>
      <line x1="36" y1="23" x2="31" y2="5"  stroke="rgba(255,61,130,.42)" stroke-width="0.85" stroke-linecap="round" stroke-dasharray="2.2 2"/>
      <!-- Silver particle data — escaping upward at different stages -->
      <rect x="25.5" y="20" width="2.2" height="2.2" rx=".3" fill="rgba(205,220,232,.92)"/>
      <rect x="31.5" y="18" width="1.9" height="1.9" rx=".3" fill="rgba(215,228,238,.86)"/>
      <rect x="22.5" y="15" width="1.8" height="1.8" rx=".3" fill="rgba(195,212,226,.82)"/>
      <rect x="28"   y="12" width="2.1" height="2.1" rx=".3" fill="rgba(208,222,234,.76)"/>
      <rect x="33"   y="10" width="1.7" height="1.7" rx=".3" fill="rgba(198,214,228,.70)"/>
      <rect x="25"   y="8"  width="1.7" height="1.7" rx=".3" fill="rgba(202,218,230,.64)"/>
      <!-- Collection node at crown — platform harvesting point -->
      <circle cx="29" cy="4"  r="2.4" fill="rgba(255,61,130,.92)" stroke="rgba(255,61,130,1)"   stroke-width="0.8"/>
      <circle cx="29" cy="4"  r="1.1" fill="rgba(255,210,228,1)"/>
      <!-- Arms — open/passive, data flowing away -->
      <path d="M21 33 Q13 35 9 41"  fill="none" stroke="rgba(255,61,130,.60)" stroke-width="1.4" stroke-linecap="round"/>
      <path d="M37 33 Q45 35 49 41" fill="none" stroke="rgba(255,61,130,.60)" stroke-width="1.4" stroke-linecap="round"/>
      <!-- Legs -->
      <path d="M23 54 Q21 62 20 70" fill="none" stroke="rgba(255,61,130,.48)" stroke-width="1.4" stroke-linecap="round"/>
      <path d="M35 54 Q37 62 38 70" fill="none" stroke="rgba(255,61,130,.48)" stroke-width="1.4" stroke-linecap="round"/>
    </svg>
    <div style="width:38px;height:5px;border-radius:50%;background:rgba(255,61,130,.10);"></div>
    <div class="av-label" style="color:rgba(255,111,163,.9);">extraction05</div>
  </div>

  <!-- glitch_24 — TEAL — body sliced into displaced horizontal strips, RGB fringe -->
  <div class="av" style="top:61%;right:20%;animation-delay:.45s;">
    <svg width="58" height="76" viewBox="0 0 58 76" fill="none" xmlns="http://www.w3.org/2000/svg">
      <!-- VR headset — with RGB ghost layers for chromatic aberration -->
      <rect x="21" y="7.6" width="20" height="11" rx="3" fill="none" stroke="rgba(255,61,130,.24)" stroke-width="1"/>
      <rect x="17" y="7.2" width="20" height="11" rx="3" fill="none" stroke="rgba(13,191,180,.18)"  stroke-width="1"/>
      <rect x="19" y="7"   width="20" height="11" rx="3" fill="rgba(13,191,180,.20)" stroke="rgba(13,191,180,.84)" stroke-width="1.2"/>
      <rect x="21" y="9"   width="6"  height="6"  rx="1.5" fill="rgba(13,191,180,.55)"/>
      <rect x="30" y="9"   width="6"  height="6"  rx="1.5" fill="rgba(13,191,180,.55)"/>
      <!-- one lens with pink ghost — corrupted display -->
      <rect x="22" y="9.6" width="5.5" height="4.5" rx="1" fill="rgba(255,61,130,.22)"/>
      <line x1="19" y1="12" x2="13" y2="12" stroke="rgba(13,191,180,.48)" stroke-width="1.1"/>
      <line x1="39" y1="12" x2="45" y2="12" stroke="rgba(13,191,180,.48)" stroke-width="1.1"/>
      <!-- Neck -->
      <rect x="26" y="18" width="6" height="5" rx="1" fill="rgba(13,191,180,.18)" stroke="rgba(13,191,180,.42)" stroke-width="1"/>

      <!-- Body as FOUR displaced horizontal slices — the glitch -->
      <!-- Slice 1 (upper torso) — shifted left -4px -->
      <path d="M23 24 Q18 28 16 31 L43 31 Q41 28 35 24 Z"
            fill="rgba(13,191,180,.14)" stroke="rgba(13,191,180,.65)" stroke-width="1.1"
            transform="translate(-4,0)"/>
      <!-- Slice 2 — no shift, anchor -->
      <path d="M16 31 L43 31 L42 38 L15 38 Z"
            fill="rgba(13,191,180,.12)" stroke="rgba(13,191,180,.58)" stroke-width="1.1"/>
      <!-- Slice 3 — shifted right +5px -->
      <path d="M15 38 L42 38 L40 45 L17 45 Z"
            fill="rgba(13,191,180,.10)" stroke="rgba(13,191,180,.50)" stroke-width="1.1"
            transform="translate(5,0)"/>
      <!-- Slice 4 (lower torso) — shifted left -2px -->
      <path d="M17 45 Q19 51 29 53 Q39 51 40 45 Z"
            fill="rgba(13,191,180,.08)" stroke="rgba(13,191,180,.44)" stroke-width="1.1"
            transform="translate(-2,0)"/>

      <!-- Scan-tear lines at slice boundaries -->
      <line x1="10" y1="31" x2="48" y2="31" stroke="rgba(255,255,255,.16)" stroke-width="1.2"/>
      <line x1="10" y1="38" x2="48" y2="38" stroke="rgba(13,191,180,.20)"  stroke-width="1.0"/>
      <line x1="10" y1="45" x2="48" y2="45" stroke="rgba(255,61,130,.14)"  stroke-width="0.8"/>

      <!-- Pixel-noise artefacts scattered across slices — bright like CRT corruption -->
      <rect x="14" y="25" width="4.5" height="2.2" rx=".2" fill="rgba(245,226,122,.92)"/>
      <rect x="34" y="26" width="3.5" height="2"   rx=".2" fill="rgba(255,61,130,.90)"/>
      <rect x="25" y="31" width="5.5" height="2.2" rx=".2" fill="rgba(13,191,180,1)"  />
      <rect x="37" y="32" width="3.2" height="2"   rx=".2" fill="rgba(245,226,122,.88)"/>
      <rect x="9"  y="34" width="4"   height="2"   rx=".2" fill="rgba(255,61,130,.82)"/>
      <rect x="18" y="39" width="4.5" height="1.8" rx=".2" fill="rgba(13,191,180,.90)"/>
      <rect x="38" y="40" width="5.5" height="2"   rx=".2" fill="rgba(245,226,122,.84)"/>
      <rect x="26" y="45" width="3.5" height="2"   rx=".2" fill="rgba(255,61,130,.78)"/>
      <!-- inverted block — white box over slice 2 -->
      <rect x="27" y="33" width="7"  height="3.5" rx=".2" fill="rgba(255,255,255,.62)"/>
      <rect x="28.5" y="34" width="4" height="2.2" rx=".2" fill="rgba(2,8,18,.92)"/>

      <!-- Arms — right arm doubled/ghosted -->
      <path d="M21 33 Q13 34 9 39"  fill="none" stroke="rgba(13,191,180,.62)" stroke-width="1.4" stroke-linecap="round"/>
      <path d="M23 33 Q15 34 11 39" fill="none" stroke="rgba(255,61,130,.22)" stroke-width="1.1" stroke-linecap="round"/>
      <path d="M37 33 Q45 34 49 39" fill="none" stroke="rgba(13,191,180,.62)" stroke-width="1.4" stroke-linecap="round"/>

      <!-- Legs — left leg displaced, right ghost -->
      <path d="M23 53 Q21 61 20 70" fill="none" stroke="rgba(13,191,180,.55)" stroke-width="1.4" stroke-linecap="round" transform="translate(-3,0)"/>
      <path d="M35 53 Q37 61 38 70" fill="none" stroke="rgba(13,191,180,.55)" stroke-width="1.4" stroke-linecap="round"/>
      <path d="M23 53 Q21 61 20 70" fill="none" stroke="rgba(255,61,130,.18)" stroke-width="1.0" stroke-linecap="round"/>
    </svg>
    <div style="width:38px;height:5px;border-radius:50%;background:rgba(13,191,180,.10);"></div>
    <div class="av-label" style="color:rgba(128,232,227,.9);">glitch_24</div>
  </div>

  <!-- "digital media" tag — between intensity02 and extraction05 -->
  <div style="position:absolute;top:44%;right:26%;z-index:6;opacity:0;animation:avFloat .7s ease .55s forwards;">
    <div style="background:rgba(255,255,255,.09);border:.5px solid rgba(255,255,255,.22);padding:5px 13px;font-size:11px;font-family:'Space Mono',monospace;color:rgba(255,255,255,.75);white-space:nowrap;border-radius:6px;box-shadow:0 2px 12px rgba(255,61,130,.12);">digital media</div>
  </div>

  <!-- "researching" tag — below all avatars -->
  <div style="position:absolute;top:73%;right:9%;z-index:6;opacity:0;animation:avFloat .7s ease .65s forwards;">
    <div style="background:rgba(255,255,255,.09);border:.5px solid rgba(255,255,255,.22);padding:5px 12px 5px 10px;font-size:11px;font-family:'Space Mono',monospace;color:rgba(255,255,255,.75);white-space:nowrap;border-radius:6px;box-shadow:0 2px 12px rgba(255,61,130,.12);display:inline-flex;align-items:center;gap:6px;">
      <svg width="11" height="11" viewBox="0 0 12 12" fill="none" xmlns="http://www.w3.org/2000/svg" style="flex-shrink:0;display:block;">
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
    <div class="hero-btn"><a href="#about">Enter ↓</a></div>
  </div>
</div>

<!-- ABOUT -->
<div class="about-section" id="about">
  <p class="section-label">About</p>
  <div class="about-inner">
    <div class="about-img-wrap">
      <img class="about-img" src="/assets/img/prof_pic.jpg" alt="Mai W. Ibrahim" />
    </div>
    <div class="text-col">
      <p class="about-text">My research examines the relationship between digital media, pre-conscious intensities, and political economy. I investigate how digital media act upon the human body prior to conscious awareness, and how platform capitalism transforms that bodily register into a site of extraction.</p>
      <p class="about-text">My work engages a wide range of media, including virtual reality, brain-computer interfaces, social media, and video games.</p>
      <p class="about-text">I am currently a sessional instructor at McMaster University in Hamilton, Canada. I was a Postdoctoral Visitor at York University's Department of Communication and Media Studies in Toronto, Canada 2024–2025, where I researched toxicity in video games. I completed my PhD in Communication, Rhetoric, and Digital Media at North Carolina State University in Raleigh, U.S.</p>
    </div>
  </div>
</div>

<!-- PUBLICATIONS -->
<div class="pubs-section" id="publications">
  <div class="pub-img-float pub-img-a"><img src="/assets/img/vr-headset.jpg" alt="VR headset"/></div>
  <div class="pub-img-float pub-img-b"><img src="/assets/img/vr-museum.jpg"  alt="VR museum"/></div>
  <div class="pub-img-float pub-img-c"><img src="/assets/img/vr-space.jpg"   alt="VR space"/></div>
  <div class="pub-img-float pub-img-d"><img src="/assets/img/bci-headset.jpg" alt="BCI headset"/></div>
  <div class="pub-content">
    <p class="section-label">Research &amp; Publications</p>
    <div class="pub-type-block type-chapters">
      <span class="pub-type-label">Book Chapters</span>
      <p class="pub-entry">Ibrahim, M. (2025). <a href="/assets/pdf/embodiment-social-vr.pdf" target="_blank">Embodiment and Representation in Social VR</a>. In Grant Bollmer, Katherine Guinness, and Yiğit Soncul (Eds.), <em>Handbook of Digital Cultures</em> (pp. 307–314). De Gruyter.</p>
      <p class="pub-entry">Ibrahim, M. (2024). <a href="/assets/pdf/tahrir-square.pdf" target="_blank">Exploring <em>Tahrir Square</em> as an Intra-Active Hybrid Space</a>. In Joanna Godlewicz-Adamiec &amp; Pawel Piszczatowski (Eds.), <em>Re-Thinking Agency: Non-Anthropocentric Approaches</em> (pp. 21–33). Vandenhoeck &amp; Ruprecht.</p>
      <p class="pub-entry">Ibrahim, M. (2023). <a href="/assets/pdf/posthuman-bci-vr.pdf" target="_blank">Posthuman Subjectivity in BCI-VR Entanglement</a>. In Veljko Dubljević &amp; Allen Coin (Eds.), <em>Policy, Identity, and Neurotechnology</em> (pp. 11–25). Springer.</p>
      <p class="pub-entry">Ibrahim, M. &amp; Dubljević, V. (2023). <a href="/assets/pdf/neurofeminism-bci.pdf" target="_blank">Neurofeminism in BCI and BBI Ethics as a Prelude to Political Neuroethics</a>. In Michele Farisco (Ed.), <em>Neuroethics and Cultural Diversity</em> (pp. 77–94). ISTE/Wiley.</p>
      <p class="pub-entry">Ibrahim, M. &amp; Dubljević, V. (2024). Prélude à la neuroéthique politique: neuroféminisme et éthique des ICM et ICC. <em>Neuroéthique et diversité culturelle</em>, p. 95. ISTE Group.</p>
    </div>
    <div class="pub-type-block type-articles">
      <span class="pub-type-label">Journal Articles</span>
      <p class="pub-entry">Ibrahim, M. (Accepted). Virtual Enchantment: Rethinking Engagement in Social VR through the <em>Better World Museum</em>. <em>Convergence</em>.</p>
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

<!-- CV + CONTACT -->
<div class="cv-contact-section" id="cv">
  <div class="cv-top-stripe"></div>
  <div class="cv-blob cv-blob-a"></div>
  <div class="cv-blob cv-blob-b"></div>
  <div class="cv-blob cv-blob-c"></div>
  <div class="cv-panel">
    <p class="section-label">CV</p>
    <a class="cv-download" href="/assets/pdf/cv.pdf" target="_blank">Download CV</a>
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
    </div>
  </div>
</div>

</div>

<script>
(function(){
  var bar=document.getElementById('scrollBar');
  function onScroll(){
    var s=window.scrollY||document.documentElement.scrollTop;
    var d=document.documentElement.scrollHeight-window.innerHeight;
    bar.style.width=(d>0?(s/d)*100:0)+'%';
  }
  window.addEventListener('scroll',onScroll,{passive:true});
  onScroll();
})();
</script>

