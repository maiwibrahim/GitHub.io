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

/* SCROLL BAR */
.scroll-bar {
  position:fixed;top:0;left:0;height:3px;width:0%;
  background:linear-gradient(90deg,#e8d46a,#f5e89a,#fdf4d0,#f5e27a,#e8d46a);
  z-index:999999;transition:width .05s linear;pointer-events:none;
  box-shadow:0 0 8px rgba(245,226,122,.55);
}

/* NAV */
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

/* ===================== HERO ===================== */
.hero {
  background:var(--hero-bg);
  min-height:100vh;width:100vw;
  display:flex;align-items:center;
  padding:60px 6vw 0;
  position:relative;overflow:hidden;
}

.hero-blob {
  position:absolute;border-radius:50%;filter:blur(90px);pointer-events:none;z-index:1;
}
.hero-blob-a { width:500px;height:500px;background:rgba(255,61,130,.14);top:-140px;right:3%; }
.hero-blob-b { width:320px;height:320px;background:rgba(13,191,180,.12);bottom:10%;right:28%; }
.hero-blob-c { width:260px;height:260px;background:rgba(245,226,122,.07);top:20%;left:5%; }

/* ===================== AVATAR SYSTEM ===================== */
.av-wrap {
  position:absolute;
  display:flex;flex-direction:column;
  align-items:center;gap:7px;
  z-index:5;
  opacity:0;
  animation:avFloat .7s ease forwards;
}
@keyframes avFloat {
  from{opacity:0;transform:translateY(14px);}
  to  {opacity:1;transform:translateY(0);}
}

/* Oval container — slightly taller than wide */
.av-oval {
  position:relative;
  width:160px;
  height:190px;
  border-radius:50%;
  overflow:hidden;
  flex-shrink:0;
}

/* Border ring rendered via outline trick so it sits outside the overflow:hidden */
.av-oval::after {
  content:'';
  position:absolute;inset:0;
  border-radius:50%;
  pointer-events:none;
  z-index:3;
}

.av-oval--gold::after  { box-shadow:inset 0 0 0 2px rgba(245,226,122,.75), inset 0 0 18px rgba(0,0,0,.35); }
.av-oval--pink::after  { box-shadow:inset 0 0 0 2px rgba(255,61,130,.80),  inset 0 0 18px rgba(0,0,0,.35); }
.av-oval--teal::after  { box-shadow:inset 0 0 0 2px rgba(13,191,180,.80),  inset 0 0 18px rgba(0,0,0,.35); }

.av-oval canvas {
  display:block;
  width:160px;
  height:190px;
}

.av-label {
  font-family:'Space Mono',monospace;font-size:9.5px;letter-spacing:.07em;
  background:rgba(0,0,0,.42);padding:3px 9px;border-radius:3px;white-space:nowrap;
}

/* Floating tag pill */
.hero-tag {
  position:absolute;z-index:6;
  opacity:0;animation:avFloat .7s ease forwards;
  background:rgba(255,255,255,.09);
  border:.5px solid rgba(255,255,255,.22);
  padding:5px 13px;font-size:11px;
  font-family:'Space Mono',monospace;
  color:rgba(255,255,255,.75);
  white-space:nowrap;border-radius:6px;
  box-shadow:0 2px 12px rgba(255,61,130,.12);
}

/* ---- HERO CONTENT ---- */
.hero-content {
  position:relative;z-index:10;
  display:flex;flex-direction:column;gap:14px;max-width:600px;
}
.hero-name {
  font-family:'DM Serif Display',Georgia,serif;
  font-size:clamp(43px,7.9vw,89px);font-weight:400;
  line-height:.92;white-space:nowrap;letter-spacing:-.01em;margin:0;
}
.hero-name .first { color:var(--yellow-soft); }
.hero-name .rest  { color:#e0f0f8; }
.hero-name em     { font-style:italic;color:rgba(13,191,180,.45); }

.hero-desc {
  font-size:clamp(14px,2vw,18px);color:#ffffff;
  font-style:italic;line-height:1.6;margin:0;
}
.hero-btn { margin-top:10px; }
.hero-btn a {
  font-family:'Space Mono',monospace;font-size:11px;
  letter-spacing:.15em;text-transform:uppercase;
  color:#0b1b2e;background:var(--teal);
  padding:12px 28px;text-decoration:none;display:inline-block;transition:background .2s;
}
.hero-btn a:hover { background:var(--teal-soft); }

/* ===================== ABOUT ===================== */
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

.about-img-wrap {
  flex-shrink:0;
  transform:rotate(-6deg);
  position:relative;
  align-self:center;
}

.about-img {
  width:230px;height:298px;
  object-fit:cover;object-position:top;display:block;
  border-radius:3px;
  box-shadow:
    0 0 0 3px #fff,
    6px 10px 36px rgba(255,61,130,.22),
    -2px -2px 0 1px rgba(13,191,180,.35);
}

.text-col {
  display:flex;flex-direction:column;gap:1.4rem;
  max-width:520px;transform:rotate(2.5deg);
  min-width:280px;padding-top:24px;
}
.about-text { font-size:16px;line-height:1.95;color:#1a2e3a;margin:0; }

/* ===================== PUBLICATIONS ===================== */
@keyframes floatA { 0%,100%{transform:translateY(0) rotate(-3deg);}  50%{transform:translateY(-18px) rotate(-3deg);} }
@keyframes floatB { 0%,100%{transform:translateY(0) rotate(2deg);}   50%{transform:translateY(-14px) rotate(2deg);} }
@keyframes floatC { 0%,100%{transform:translateY(0) rotate(-1.5deg);}50%{transform:translateY(-20px) rotate(-1.5deg);} }
@keyframes floatD { 0%,100%{transform:translateY(0) rotate(4deg);}   50%{transform:translateY(-12px) rotate(4deg);} }

.pubs-section {
  background:#fdfcff;min-height:100vh;width:100vw;color:#1a2e3a;
  margin-top:-60px;
  clip-path:polygon(0 0,100% 60px,100% 100%,0 100%);
  padding:130px max(2.5rem,6vw) 6rem;
  position:relative;overflow:hidden;
}
.pubs-section * { color:#1a2e3a; }
.pubs-section a { color:#1a2e3a!important;border-bottom:.5px solid rgba(26,46,58,.28);text-decoration:none; }
.pubs-section a:hover { color:var(--pink)!important;border-bottom-color:var(--pink); }
.pubs-section .section-label { color:var(--pink);margin-bottom:2rem;text-align:left;font-size:17px; }

.pub-img-float {
  position:absolute;z-index:2;overflow:hidden;
  border-radius:4px;box-shadow:0 8px 32px rgba(255,61,130,.1);cursor:pointer;
}
.pub-img-float img {
  width:100%;height:100%;object-fit:cover;display:block;
  opacity:.14;filter:grayscale(10%);
  transition:opacity .45s ease,transform .45s ease;
}
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
  margin-bottom:1rem;padding:5px 14px;display:inline-block;border-radius:3px;
  font-family:'Space Mono',monospace;
}
.type-chapters  .pub-type-label { background:#d0eef8;color:#0a5e78; }
.type-articles  .pub-type-label { background:#ffe5ef;color:var(--pink); }
.type-reviews   .pub-type-label { background:#fdf4d0;color:#7a6820; }
.type-interview .pub-type-label { background:#e8faf9;color:#0a7a74; }

.pub-entry {
  font-size:16px;line-height:1.9;color:#1a2e3a;
  margin-bottom:.9rem;font-family:'Lora',serif;
}
.pub-entry:last-child { margin-bottom:0; }
.pub-entry em { font-style:italic; }
.pub-entry a { color:inherit;text-decoration:none;border-bottom:.5px solid rgba(26,46,58,.28); }
.pub-entry a:hover { border-bottom-color:var(--pink);color:var(--pink)!important; }

/* ===================== CV + CONTACT ===================== */
.cv-contact-section {
  background:#0b1b2e;min-height:100vh;width:100vw;
  display:grid;grid-template-columns:1fr 1px 1fr;
  position:relative;overflow:hidden;
}
.cv-blob {
  position:absolute;border-radius:50%;filter:blur(90px);pointer-events:none;z-index:0;
}
.cv-blob-a { width:500px;height:500px;background:rgba(255,61,130,.12);top:-120px;left:-100px; }
.cv-blob-b { width:380px;height:380px;background:rgba(13,191,180,.1);bottom:-80px;right:-80px; }
.cv-blob-c { width:280px;height:280px;background:rgba(245,226,122,.05);top:40%;left:40%; }

.cv-top-stripe {
  position:absolute;top:0;left:0;right:0;height:3px;
  background:linear-gradient(90deg,#e8d46a,#f5e89a,#fdf4d0,#f5e27a,#e8d46a);
  z-index:10;
}
.cv-divider { background:rgba(13,191,180,.14);align-self:stretch;position:relative;z-index:2; }

.cv-panel {
  display:flex;flex-direction:column;justify-content:center;
  padding:6rem max(2rem,5vw) 6rem max(2.5rem,6vw);
  position:relative;z-index:2;
}
.cv-panel .section-label { color:rgba(13,191,180,.62);text-align:left;margin-bottom:2rem;font-size:17px; }

.cv-download {
  font-family:'Space Mono',monospace;font-size:11px;letter-spacing:.18em;
  text-transform:uppercase;color:#0b1b2e;background:var(--teal);
  text-decoration:none;padding:14px 32px;
  display:inline-flex;align-items:center;gap:10px;transition:background .2s;width:fit-content;
}
.cv-download:hover { background:var(--teal-soft);color:#0b1b2e; }
.cv-download::after { content:'↓';font-size:16px; }

.contact-panel {
  display:flex;flex-direction:column;justify-content:center;
  padding:6rem max(2.5rem,6vw) 6rem max(2rem,5vw);
  position:relative;z-index:2;
}
.contact-panel .section-label { color:rgba(13,191,180,.62);text-align:left;margin-bottom:2rem;font-size:17px; }

.contact-grid { display:flex;flex-direction:column;gap:0;max-width:420px; }
.contact-row {
  display:flex;align-items:center;justify-content:space-between;
  padding:1.3rem 0;border-bottom:.5px solid rgba(13,191,180,.15);
  text-decoration:none;
  transition:padding-left .25s,color .2s;
}
.contact-row:first-child { border-top:.5px solid rgba(13,191,180,.15); }
.contact-row:hover { padding-left:.65rem; }

.contact-label {
  font-family:'Space Mono',monospace;font-size:9px;
  letter-spacing:.18em;text-transform:uppercase;
  color:var(--teal);min-width:100px;
}
.contact-value {
  font-family:'Lora',serif;font-size:16px;font-style:italic;
  color:#ffffff;flex:1;padding:0 1rem;
}
.contact-arrow {
  font-family:'Space Mono',monospace;font-size:13px;
  color:rgba(13,191,180,.36);transition:transform .2s,color .2s;
}
.contact-row:hover .contact-arrow { transform:translateX(5px);color:var(--teal-soft); }
.contact-row:hover .contact-value { color:var(--teal-muted); }

/* ===================== MOBILE ===================== */
@media (max-width:640px) {
  .site-nav { justify-content:flex-start;padding:0 1.5rem;gap:1.25rem;height:56px; }
  .site-nav a { font-size:10px; }

  .hero { padding:56px 1.5rem 60px;align-items:center;min-height:100svh; }
  .hero-name { white-space:normal; }
  .hero-content { max-width:55%; }

  .av-wrap { transform:scale(.75);transform-origin:top left; }

  .about-section {
    clip-path:polygon(0 30px,100% 0,100% 100%,0 100%);
    padding:80px 1.5rem 80px;margin-top:-30px;
  }
  .about-inner { flex-direction:column;align-items:center;gap:2.5rem; }
  .about-img-wrap { transform:rotate(-3deg); }
  .about-img { width:190px;height:246px; }
  .text-col { transform:rotate(1.5deg);max-width:100%;min-width:unset; }
  .about-text { font-size:15px; }
  .section-label { font-size:15px; }

  .pubs-section {
    clip-path:polygon(0 0,100% 30px,100% 100%,0 100%);
    padding-top:80px;margin-top:-30px;
  }
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

<!-- HERO -->
<div class="hero" id="hero">
  <div class="hero-blob hero-blob-a"></div>
  <div class="hero-blob hero-blob-b"></div>
  <div class="hero-blob hero-blob-c"></div>

  <!-- intensity02 — upper right, gold oval -->
  <div class="av-wrap" style="top:38%;right:11%;animation-delay:.10s;">
    <div class="av-oval av-oval--gold">
      <canvas id="cv-intensity" width="320" height="380"></canvas>
    </div>
    <div class="av-label" style="color:rgba(249,237,170,.9);">intensity02</div>
  </div>

  <!-- extraction05 — mid right, pink oval -->
  <div class="av-wrap" style="top:46%;right:32%;animation-delay:.28s;">
    <div class="av-oval av-oval--pink">
      <canvas id="cv-extraction" width="320" height="380"></canvas>
    </div>
    <div class="av-label" style="color:rgba(255,111,163,.9);">extraction05</div>
  </div>

  <!-- glitch_24 — lower right, teal oval -->
  <div class="av-wrap" style="top:58%;right:11%;animation-delay:.45s;">
    <div class="av-oval av-oval--teal">
      <canvas id="cv-glitch" width="320" height="380"></canvas>
    </div>
    <div class="av-label" style="color:rgba(128,232,227,.9);">glitch_24</div>
  </div>

  <!-- floating tags -->
  <div class="hero-tag" style="top:30%;right:24%;animation-delay:.55s;">digital media</div>
  <div class="hero-tag" style="top:54%;right:9%;animation-delay:.65s;display:inline-flex;align-items:center;gap:6px;">
    <svg width="11" height="11" viewBox="0 0 12 12" fill="none" xmlns="http://www.w3.org/2000/svg" style="flex-shrink:0;">
      <circle cx="5" cy="5" r="3.4" stroke="rgba(255,255,255,0.65)" stroke-width="1.3"/>
      <line x1="7.4" y1="7.4" x2="11" y2="11" stroke="rgba(255,255,255,0.65)" stroke-width="1.4" stroke-linecap="round"/>
    </svg>
    researching
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
/* =========================================================
   SCROLL BAR
   ========================================================= */
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

/* =========================================================
   WEBGL SHADER UTILITY
   ========================================================= */
function initShader(canvas, fsSource) {
  var gl = canvas.getContext('webgl', {antialias:true, alpha:true});
  if (!gl) return null;

  var vsSource = [
    'attribute vec2 a_pos;',
    'void main(){gl_Position=vec4(a_pos,0.0,1.0);}'
  ].join('\n');

  function compile(type, src) {
    var s = gl.createShader(type);
    gl.shaderSource(s, src);
    gl.compileShader(s);
    return s;
  }

  var prog = gl.createProgram();
  gl.attachShader(prog, compile(gl.VERTEX_SHADER, vsSource));
  gl.attachShader(prog, compile(gl.FRAGMENT_SHADER, fsSource));
  gl.linkProgram(prog);
  gl.useProgram(prog);

  var buf = gl.createBuffer();
  gl.bindBuffer(gl.ARRAY_BUFFER, buf);
  gl.bufferData(gl.ARRAY_BUFFER, new Float32Array([-1,-1, 1,-1, -1,1, 1,1]), gl.STATIC_DRAW);
  var loc = gl.getAttribLocation(prog, 'a_pos');
  gl.enableVertexAttribArray(loc);
  gl.vertexAttribPointer(loc, 2, gl.FLOAT, false, 0, 0);

  gl.enable(gl.BLEND);
  gl.blendFunc(gl.SRC_ALPHA, gl.ONE_MINUS_SRC_ALPHA);

  return {
    gl: gl,
    prog: prog,
    u: function(name){ return gl.getUniformLocation(prog, name); }
  };
}

function animate(ctx, draw) {
  function frame(t) {
    draw(t * 0.001);
    requestAnimationFrame(frame);
  }
  requestAnimationFrame(frame);
}

/* =========================================================
   SHADER 1 — intensity02
   Domain-warped fractal Brownian motion, golden warmth
   ========================================================= */
(function(){
  var cv = document.getElementById('cv-intensity');
  if (!cv) return;
  var ctx = initShader(cv, [
    'precision highp float;',
    'uniform float u_time;',
    'uniform vec2  u_res;',

    'float hash(vec2 p){',
    '  return fract(sin(dot(p,vec2(127.1,311.7)))*43758.5453);',
    '}',

    'float noise(vec2 p){',
    '  vec2 i=floor(p), f=fract(p);',
    '  vec2 u=f*f*(3.0-2.0*f);',
    '  return mix(mix(hash(i),hash(i+vec2(1,0)),u.x),',
    '             mix(hash(i+vec2(0,1)),hash(i+vec2(1,1)),u.x),u.y);',
    '}',

    'float fbm(vec2 p){',
    '  float v=0.0, a=0.5;',
    '  mat2 r=mat2(cos(0.5),sin(0.5),-sin(0.5),cos(0.5));',
    '  for(int i=0;i<6;i++){v+=a*noise(p);p=r*p*2.1;a*=0.5;}',
    '  return v;',
    '}',

    'void main(){',
    '  vec2 uv=(gl_FragCoord.xy/u_res)*2.0-1.0;',
    '  uv.x*=u_res.x/u_res.y;',
    '  float t=u_time*0.18;',
    /* domain warp — two layers */
    '  vec2 q=vec2(fbm(uv+vec2(0.0,0.0)),',
    '              fbm(uv+vec2(5.2,1.3)));',
    '  vec2 r=vec2(fbm(uv+4.0*q+vec2(1.7+t,9.2)),',
    '              fbm(uv+4.0*q+vec2(8.3,2.8+t*0.7)));',
    '  float f=fbm(uv+4.0*r);',
    /* colour — golden warmth pools */
    '  vec3 col=mix(vec3(0.12,0.06,0.01), vec3(0.70,0.52,0.08), clamp(f*f*4.0,0.0,1.0));',
    '  col=mix(col, vec3(0.96,0.86,0.38), clamp(length(q),0.0,1.0));',
    '  col=mix(col, vec3(1.00,0.97,0.72), f*f*f*f);',
    /* vignette */
    '  float vig=1.0-dot(uv*0.55,uv*0.55);',
    '  col*=vig*vig;',
    '  gl_FragColor=vec4(col,0.82*vig*vig);',
    '}'
  ].join('\n'));
  if (!ctx) return;
  var uTime = ctx.u('u_time'), uRes = ctx.u('u_res');
  ctx.gl.uniform2f(uRes, cv.width, cv.height);
  animate(ctx, function(t){
    ctx.gl.uniform1f(uTime, t);
    ctx.gl.viewport(0,0,cv.width,cv.height);
    ctx.gl.clear(ctx.gl.COLOR_BUFFER_BIT);
    ctx.gl.drawArrays(ctx.gl.TRIANGLE_STRIP,0,4);
  });
})();

/* =========================================================
   SHADER 2 — extraction05
   Spinning vortex field + silver particle rain into void
   ========================================================= */
(function(){
  var cv = document.getElementById('cv-extraction');
  if (!cv) return;
  var ctx = initShader(cv, [
    'precision highp float;',
    'uniform float u_time;',
    'uniform vec2  u_res;',

    'float hash(vec2 p){return fract(sin(dot(p,vec2(127.1,311.7)))*43758.5453);}',
    'float hash1(float n){return fract(sin(n)*753.5453);}',

    'void main(){',
    '  vec2 uv=(gl_FragCoord.xy/u_res)*2.0-1.0;',
    '  uv.x*=u_res.x/u_res.y;',
    '  float t=u_time;',

    /* --- vortex field --- */
    '  float r=length(uv);',
    '  float a=atan(uv.y,uv.x);',
    '  float spin=a - t*1.4 - 3.0/(r+0.18);',
    '  float swirl=sin(spin*5.0)*0.5+0.5;',
    '  float arms=smoothstep(0.38,0.0,mod(spin*0.5+t*0.3,1.0)-0.5)*0.6;',

    /* void pull — darkening towards centre */
    '  float vd=1.0-smoothstep(0.0,0.55,r);',

    /* base pink/magenta vortex colour */
    '  vec3 vortex=mix(vec3(0.05,0.01,0.04), vec3(0.80,0.10,0.36), swirl*(1.0-vd));',
    '  vortex+=arms*vec3(1.0,0.24,0.51)*0.5;',

    /* --- silver particle rain --- */
    /* tile UV into columns, each column has particles falling */
    '  vec2 pUV=vec2((uv.x*0.5+0.5)*16.0, (uv.y*0.5+0.5));',
    '  float col_id=floor(pUV.x);',
    '  float col_frac=fract(pUV.x);',

    /* each column: 4 staggered particles */
    '  float sparkle=0.0;',
    '  for(int k=0;k<4;k++){',
    '    float ki=float(k);',
    '    float speed=0.28+hash1(col_id*7.0+ki)*0.44;',
    '    float phase=hash1(col_id*3.1+ki*5.7);',
    '    float py=fract(phase - t*speed);',   /* falls top→0 */
    '    float dy=abs(pUV.y-py);',
    '    float dot_r=0.025+hash1(col_id+ki)*0.015;',
    '    sparkle+=smoothstep(dot_r,0.0,dy)*smoothstep(0.4,0.0,abs(col_frac-0.5));',
    '  }',

    /* silver colour with slight blue tint, fade as they approach the vortex centre */
    '  float fadeIn=smoothstep(0.0,0.08,r);',  /* don't show particles inside void */
    '  vec3 silver=vec3(0.82,0.88,0.92)*sparkle*fadeIn;',

    /* combine */
    '  vec3 col=vortex+silver;',
    /* vignette */
    '  float vig=1.0-dot(uv*0.55,uv*0.55);',
    '  col*=clamp(vig,0.0,1.0);',
    '  float alpha=0.82*clamp(vig,0.0,1.0);',
    '  gl_FragColor=vec4(col,alpha);',
    '}'
  ].join('\n'));
  if (!ctx) return;
  var uTime = ctx.u('u_time'), uRes = ctx.u('u_res');
  ctx.gl.uniform2f(uRes, cv.width, cv.height);
  animate(ctx, function(t){
    ctx.gl.uniform1f(uTime, t);
    ctx.gl.viewport(0,0,cv.width,cv.height);
    ctx.gl.clear(ctx.gl.COLOR_BUFFER_BIT);
    ctx.gl.drawArrays(ctx.gl.TRIANGLE_STRIP,0,4);
  });
})();

/* =========================================================
   SHADER 3 — glitch_24
   CRT corruption: scanlines, RGB split, noise blocks,
   chromatic aberration, all regenerating each frame
   ========================================================= */
(function(){
  var cv = document.getElementById('cv-glitch');
  if (!cv) return;
  var ctx = initShader(cv, [
    'precision highp float;',
    'uniform float u_time;',
    'uniform vec2  u_res;',

    'float hash(float n){return fract(sin(n)*43758.5453);}',
    'float hash2(vec2 p){return fract(sin(dot(p,vec2(127.1,311.7)))*43758.5);}',

    'void main(){',
    '  vec2 uv=gl_FragCoord.xy/u_res;',
    '  float t=u_time;',

    /* --- scanline baseline --- */
    '  float scan=sin(uv.y*u_res.y*0.9)*0.04;',

    /* --- per-scanline horizontal displacement (tear) --- */
    '  float lineIdx=floor(uv.y*u_res.y);',
    '  float tearT=floor(t*8.0);',   /* 8 tears/sec */
    '  float tearR=hash(lineIdx*0.001+tearT);',
    '  float tearStrength=step(0.88,tearR)*hash(lineIdx+tearT*3.7);',
    '  float xShift=tearStrength*(hash(lineIdx*2.0+tearT)*2.0-1.0)*0.14;',

    /* displaced uv for main channel */
    '  vec2 uvD=vec2(uv.x+xShift, uv.y)+scan;',

    /* --- RGB channel split (chromatic aberration) --- */
    '  float caAmt=0.012+0.018*hash(floor(t*4.0));',
    '  vec2 uvR=uvD+vec2( caAmt,  0.0);',
    '  vec2 uvG=uvD+vec2( 0.0,    0.0);',
    '  vec2 uvB=uvD+vec2(-caAmt,  0.0);',

    /* --- base CRT screen colour (dark teal phosphor) --- */
    '  float screenR=0.02+0.13*hash2(uvR*vec2(7.3,2.1)+t*0.5);',
    '  float screenG=0.06+0.22*hash2(uvG*vec2(5.1,8.7)+t*0.4);',
    '  float screenB=0.04+0.10*hash2(uvB*vec2(9.2,3.3)+t*0.6);',

    /* teal phosphor tint base */
    '  vec3 phosphor=vec3(screenR, screenG*1.6, screenB*1.4);',
    '  phosphor+=vec3(0.0,0.28,0.25)*0.6;',

    /* --- glitch colour bands --- */
    /* Band: full-width teal horizontal slice, scrolling */
    '  float b1y=fract(uv.y*3.0 - t*0.42);',
    '  float band1=step(0.96,b1y)*0.9;',
    '  vec3 bCol1=vec3(0.05,0.75,0.71)*band1;',

    /* Band: pink slice going opposite */
    '  float b2y=fract(uv.y*5.0 + t*0.31);',
    '  float band2=step(0.975,b2y)*0.75;',
    '  vec3 bCol2=vec3(1.0,0.24,0.51)*band2;',

    /* Band: yellow thin stripe */
    '  float b3y=fract(uv.y*9.0 - t*0.2+0.5);',
    '  float band3=step(0.988,b3y)*0.6;',
    '  vec3 bCol3=vec3(0.96,0.89,0.27)*band3;',

    /* --- noise blocks (random coloured rectangles) --- */
    /* divide screen into coarse cells, flicker */
    '  vec2 cell8=floor(uv*8.0);',
    '  float blockT=floor(t*12.0);',
    '  float blockR=hash2(cell8+blockT);',
    '  float isBlock=step(0.93,blockR);',
    '  vec3 blockCol=vec3(hash(blockR*7.1),hash(blockR*13.3),hash(blockR*5.9))*isBlock;',
    '  float blockAlpha=isBlock*0.65;',

    /* --- scanline dark lines every 2 px --- */
    '  float sline=0.65+0.35*step(0.5,fract(uv.y*u_res.y*0.5));',

    /* --- compose --- */
    '  vec3 col=phosphor;',
    '  col+=bCol1+bCol2+bCol3;',
    '  col=mix(col,blockCol,blockAlpha);',
    '  col*=sline;',

    /* vignette */
    '  vec2 vUV=uv*2.0-1.0;',
    '  float vig=1.0-dot(vUV*0.55,vUV*0.55);',
    '  col*=vig;',

    /* clamp */
    '  col=clamp(col,0.0,1.0);',
    '  gl_FragColor=vec4(col,0.82*vig);',
    '}'
  ].join('\n'));
  if (!ctx) return;
  var uTime = ctx.u('u_time'), uRes = ctx.u('u_res');
  ctx.gl.uniform2f(uRes, cv.width, cv.height);
  animate(ctx, function(t){
    ctx.gl.uniform1f(uTime, t);
    ctx.gl.viewport(0,0,cv.width,cv.height);
    ctx.gl.clear(ctx.gl.COLOR_BUFFER_BIT);
    ctx.gl.drawArrays(ctx.gl.TRIANGLE_STRIP,0,4);
  });
})();
</script>
