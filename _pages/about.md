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
  --hero-bg:      #1a0f2e;
  --plum:         #6b3f72;
  --plum-soft:    #9b6aa4;
  --plum-muted:   #c4a0cc;
  --teal:         #2a8c84;
  --teal-soft:    #4db8b0;
  --teal-muted:   #8fd8d2;
  --yellow:       #e8d48a;
  --yellow-soft:  #f0e0a0;
  --yellow-muted: #f5ecc0;
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
  background:linear-gradient(90deg,var(--plum),var(--teal),var(--yellow));
  z-index:999999;transition:width .05s linear;pointer-events:none;
  box-shadow:0 0 8px rgba(155,106,164,.5);
}

/* NAV */
.site-nav {
  position:fixed;top:0;left:0;right:0;z-index:99999;
  background:rgba(26,15,46,.88);backdrop-filter:blur(14px);
  display:flex;gap:2rem;align-items:center;justify-content:flex-end;
  height:52px;padding:0 3rem;
  border-bottom:.5px solid rgba(155,106,164,.18);
}
.site-nav a {
  font-family:'Space Mono',monospace;font-size:11px;
  color:rgba(196,160,204,.55);text-decoration:none;
  letter-spacing:.18em;text-transform:uppercase;transition:color .2s;
}
.site-nav a:hover { color:var(--plum-muted); }

/* HERO */
.hero {
  background:var(--hero-bg);
  min-height:100vh;width:100vw;
  display:flex;align-items:flex-end;
  padding:0 6vw 80px;
  position:relative;overflow:hidden;
}

.hero-blob {
  position:absolute;border-radius:50%;filter:blur(90px);pointer-events:none;z-index:1;
}
.hero-blob-a { width:500px;height:500px;background:rgba(107,63,114,.22);top:-140px;right:3%; }
.hero-blob-b { width:320px;height:320px;background:rgba(42,140,132,.14);bottom:10%;right:28%; }
.hero-blob-c { width:260px;height:260px;background:rgba(232,212,138,.08);top:20%;left:5%; }

.ui-dots {
  position:absolute;top:16px;right:20px;
  display:flex;gap:5px;z-index:10;
}
.ui-dots span { width:6px;height:6px;border-radius:50%; }

/* AVATARS */
.av {
  position:absolute;display:flex;flex-direction:column;
  align-items:center;gap:3px;z-index:5;
  opacity:0;animation:avFloat .7s ease forwards;
}
@keyframes avFloat {
  from{opacity:0;transform:translateY(14px);}
  to  {opacity:1;transform:translateY(0);}
}
.av-body {
  border-radius:50% 50% 40% 40%;
  display:flex;align-items:center;justify-content:center;font-size:16px;
}
.av-shadow { border-radius:50%;height:5px; }
.av-label {
  font-family:'Space Mono',monospace;font-size:8px;letter-spacing:.05em;
  background:rgba(0,0,0,.38);padding:1px 5px;border-radius:2px;white-space:nowrap;
}
.speech {
  position:absolute;
  background:rgba(255,255,255,.07);
  border:.5px solid rgba(255,255,255,.14);
  padding:3px 8px;font-size:8px;
  font-family:'Space Mono',monospace;
  color:rgba(255,255,255,.55);
  white-space:nowrap;border-radius:6px 6px 6px 0;
}

/* HERO CONTENT */
.hero-content {
  position:relative;z-index:10;
  display:flex;flex-direction:column;gap:14px;max-width:600px;
}
.hero-name {
  font-family:'DM Serif Display',Georgia,serif;
  font-size:clamp(44px,8vw,90px);font-weight:400;
  line-height:.92;white-space:nowrap;letter-spacing:-.01em;margin:0;
}
.hero-name .first { color:var(--yellow-soft); }
.hero-name .rest  { color:#ede4f5; }
.hero-name em     { font-style:italic;color:rgba(196,160,204,.45); }
.hero-desc {
  font-size:clamp(14px,2vw,18px);color:rgba(196,160,204,.42);
  font-style:italic;line-height:1.6;margin:0;
}
.hero-btn { margin-top:10px; }
.hero-btn a {
  font-family:'Space Mono',monospace;font-size:11px;
  letter-spacing:.15em;text-transform:uppercase;
  color:var(--hero-bg);background:var(--teal-soft);
  padding:12px 28px;text-decoration:none;display:inline-block;transition:background .2s;
}
.hero-btn a:hover { background:var(--teal-muted); }

/* ABOUT */
.about-section {
  background:#f5f0fa;width:100vw;
  padding:130px max(2.5rem,6vw) 140px;
  margin-top:-60px;
  clip-path:polygon(0 60px,100% 0,100% 100%,0 100%);
  min-height:100vh;display:flex;flex-direction:column;
  justify-content:center;align-items:center;position:relative;
}

.section-label {
  font-size:15px;letter-spacing:.24em;text-transform:uppercase;
  color:var(--plum);margin-bottom:2.5rem;
  font-style:normal;font-family:'Space Mono',monospace;
  text-align:center;width:100%;
}

.about-inner {
  display:flex;gap:7rem;align-items:center;
  justify-content:center;flex-wrap:wrap;position:relative;
}

.about-img-wrap {
  flex-shrink:0;
  transform:rotate(-4deg);
  position:relative;top:80px;
}
.about-img {
  width:230px;height:298px;
  object-fit:cover;object-position:top;display:block;
  border-radius:3px;
  box-shadow:4px 8px 28px rgba(107,63,114,.18);
}

.text-col {
  display:flex;flex-direction:column;gap:1.4rem;
  max-width:520px;transform:rotate(1.5deg);
  min-width:280px;padding-top:24px;
}
.about-text { font-size:17px;line-height:1.95;color:#3a2e42;margin:0; }

/* PUBLICATIONS */
@keyframes floatA { 0%,100%{transform:translateY(0) rotate(-3deg);}  50%{transform:translateY(-18px) rotate(-3deg);} }
@keyframes floatB { 0%,100%{transform:translateY(0) rotate(2deg);}   50%{transform:translateY(-14px) rotate(2deg);} }
@keyframes floatC { 0%,100%{transform:translateY(0) rotate(-1.5deg);}50%{transform:translateY(-20px) rotate(-1.5deg);} }
@keyframes floatD { 0%,100%{transform:translateY(0) rotate(4deg);}   50%{transform:translateY(-12px) rotate(4deg);} }

.pubs-section {
  background:#fefcff;min-height:100vh;width:100vw;color:#38342a;
  margin-top:-60px;
  clip-path:polygon(0 0,100% 60px,100% 100%,0 100%);
  padding:130px max(2.5rem,6vw) 6rem;
  position:relative;overflow:hidden;
}
.pubs-section * { color:#38342a; }
.pubs-section a { color:#38342a!important;border-bottom:.5px solid rgba(56,52,42,.28);text-decoration:none; }
.pubs-section a:hover { color:var(--plum)!important;border-bottom-color:var(--plum); }
.pubs-section .section-label { color:var(--plum);margin-bottom:2rem;text-align:left;font-size:15px; }

.pub-img-float {
  position:absolute;z-index:2;overflow:hidden;
  border-radius:4px;box-shadow:0 8px 32px rgba(107,63,114,.12);cursor:pointer;
}
.pub-img-float img {
  width:100%;height:100%;object-fit:cover;display:block;
  opacity:.14;filter:grayscale(10%);
  transition:opacity .45s ease,transform .45s ease;
}
.pub-img-float:hover img { opacity:.88;transform:scale(1.04); }

.pub-img-a { width:320px;height:230px;top:110px; right:22px;  animation:floatA 8s  ease-in-out infinite; }
.pub-img-d { width:280px;height:258px;top:400px; right:60px;  animation:floatD 7s  ease-in-out infinite; }
.pub-img-b { width:260px;height:330px;top:110px; right:380px; animation:floatB 10s ease-in-out infinite; }
.pub-img-c { width:280px;height:380px;top:490px; right:370px; animation:floatC 9s  ease-in-out infinite; }
.pub-img-c img { object-fit:contain;object-position:center; }

.pub-content { position:relative;z-index:10;max-width:660px; }

.pub-type-block { margin-bottom:2.8rem; }
.pub-type-block:last-child { margin-bottom:0; }
.pub-type-label {
  font-size:11px;font-weight:500;letter-spacing:.14em;text-transform:uppercase;
  margin-bottom:1rem;padding:5px 14px;display:inline-block;border-radius:3px;
  font-family:'Space Mono',monospace;
}
.type-chapters  .pub-type-label { background:#e8ddf5;color:var(--plum); }
.type-articles  .pub-type-label { background:#d0eeec;color:var(--teal); }
.type-reviews   .pub-type-label { background:#f5f0d0;color:#7a6820; }
.type-interview .pub-type-label { background:#eeddf5;color:var(--plum-soft); }

.pub-entry {
  font-size:16px;line-height:1.9;color:#38342a;
  margin-bottom:.9rem;font-family:'Lora',serif;
}
.pub-entry:last-child { margin-bottom:0; }
.pub-entry em { font-style:italic; }
.pub-entry a { color:inherit;text-decoration:none;border-bottom:.5px solid rgba(56,52,42,.28); }
.pub-entry a:hover { border-bottom-color:var(--plum);color:var(--plum)!important; }

/* CV + CONTACT */
.cv-contact-section {
  background:#1a0f2e;min-height:100vh;width:100vw;
  display:grid;grid-template-columns:1fr 1px 1fr;
  position:relative;overflow:hidden;
}
.cv-blob {
  position:absolute;border-radius:50%;filter:blur(90px);pointer-events:none;z-index:0;
}
.cv-blob-a { width:500px;height:500px;background:rgba(107,63,114,.18);top:-120px;left:-100px; }
.cv-blob-b { width:380px;height:380px;background:rgba(42,140,132,.12);bottom:-80px;right:-80px; }
.cv-blob-c { width:280px;height:280px;background:rgba(232,212,138,.06);top:40%;left:40%; }

.cv-top-stripe {
  position:absolute;top:0;left:0;right:0;height:3px;
  background:linear-gradient(90deg,var(--plum),var(--teal),var(--yellow));
  z-index:10;
}
.cv-divider { background:rgba(155,106,164,.16);align-self:stretch;position:relative;z-index:2; }

.cv-panel {
  display:flex;flex-direction:column;justify-content:center;
  padding:6rem max(2rem,5vw) 6rem max(2.5rem,6vw);
  position:relative;z-index:2;
}
.cv-panel .section-label { color:rgba(196,160,204,.62);text-align:left;margin-bottom:2rem; }

.cv-download {
  font-family:'Space Mono',monospace;font-size:11px;letter-spacing:.18em;
  text-transform:uppercase;color:var(--hero-bg);background:var(--teal-soft);
  text-decoration:none;padding:14px 32px;
  display:inline-flex;align-items:center;gap:10px;transition:background .2s;width:fit-content;
}
.cv-download:hover { background:var(--teal-muted);color:var(--hero-bg); }
.cv-download::after { content:'↓';font-size:16px; }

.cv-watermark {
  position:absolute;right:-10px;bottom:-30px;
  font-family:'DM Serif Display',Georgia,serif;
  font-size:220px;color:rgba(155,106,164,.05);
  line-height:1;pointer-events:none;user-select:none;z-index:1;
}

.contact-panel {
  display:flex;flex-direction:column;justify-content:center;
  padding:6rem max(2.5rem,6vw) 6rem max(2rem,5vw);
  position:relative;z-index:2;
}
.contact-panel .section-label { color:rgba(196,160,204,.62);text-align:left;margin-bottom:2rem; }

.contact-grid { display:flex;flex-direction:column;gap:0;max-width:420px; }
.contact-row {
  display:flex;align-items:center;justify-content:space-between;
  padding:1.3rem 0;border-bottom:.5px solid rgba(155,106,164,.15);
  text-decoration:none;color:rgba(215,200,228,.8);
  transition:padding-left .25s,color .2s;
}
.contact-row:first-child { border-top:.5px solid rgba(155,106,164,.15); }
.contact-row:hover { padding-left:.65rem;color:var(--plum-muted); }
.contact-label {
  font-family:'Space Mono',monospace;font-size:9px;
  letter-spacing:.18em;text-transform:uppercase;
  color:rgba(155,106,164,.4);min-width:100px;
}
.contact-value {
  font-family:'Lora',serif;font-size:16px;font-style:italic;
  color:inherit;flex:1;padding:0 1rem;
}
.contact-arrow {
  font-family:'Space Mono',monospace;font-size:13px;
  color:rgba(155,106,164,.36);transition:transform .2s,color .2s;
}
.contact-row:hover .contact-arrow { transform:translateX(5px);color:var(--plum-muted); }

/* MOBILE */
@media (max-width:640px) {
  .site-nav { justify-content:flex-start;padding:0 1.5rem;gap:1.25rem; }
  .site-nav a { font-size:9px; }

  .hero { padding:52px 1.5rem 60px;align-items:flex-end;min-height:100svh; }
  .hero-name { white-space:normal; }
  .hero-content { max-width:55%; }

  .av { transform:scale(.68);transform-origin:top left; }
  .av-1 { top:16%!important;right:1%!important;animation-delay:.1s; }
  .av-2 { top:28%!important;right:1%!important;animation-delay:.25s; }
  .av-3 { top:40%!important;right:1%!important;animation-delay:.4s; }
  .av-4 { top:52%!important;right:1%!important;animation-delay:.55s; }
  .av-5 { top:64%!important;right:1%!important;animation-delay:.7s; }

  .about-section {
    clip-path:polygon(0 30px,100% 0,100% 100%,0 100%);
    padding:80px 1.5rem 80px;margin-top:-30px;
  }
  .about-inner { flex-direction:column;align-items:center;gap:2.5rem; }
  .about-img-wrap { transform:rotate(-2deg);top:0; }
  .about-img { width:190px;height:246px; }
  .text-col { transform:rotate(1deg);max-width:100%;min-width:unset; }
  .about-text { font-size:16px; }

  .pubs-section {
    clip-path:polygon(0 0,100% 30px,100% 100%,0 100%);
    padding-top:80px;margin-top:-30px;
  }
  .pub-entry { font-size:14px; }
  .pub-img-float { display:none; }

  .cv-contact-section { grid-template-columns:1fr; }
  .cv-divider { display:none; }
  .cv-panel { padding:5rem 1.5rem 3rem; }
  .contact-panel { padding:2rem 1.5rem 5rem; }
  .contact-value { font-size:14px; }
  .cv-watermark { font-size:130px; }
}

@media (max-width:900px) and (min-width:641px) {
  .pub-img-a { width:200px;height:144px;right:14px;top:100px; }
  .pub-img-d { width:175px;height:161px;top:290px;right:38px; }
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

  <div class="ui-dots">
    <span style="background:#c084d4;"></span>
    <span style="background:#4db8b0;"></span>
    <span style="background:#e8d48a;"></span>
  </div>

  <!-- av-1: intensity02 — upper far right -->
  <div class="av av-1" style="top:12%;right:12%;animation-delay:.1s;">
    <div style="position:relative;">
      <div class="speech" style="top:-28px;left:30px;">researching 🔍</div>
    </div>
    <div class="av-body" style="width:40px;height:46px;background:rgba(232,212,138,.18);border:1px solid rgba(232,212,138,.4);">🌐</div>
    <div class="av-shadow" style="width:28px;background:rgba(232,212,138,.1);"></div>
    <div class="av-label" style="color:rgba(240,224,160,.85);">intensity02</div>
  </div>

  <!-- av-2: extraction_05 — upper centre-right -->
  <div class="av av-2" style="top:10%;right:40%;animation-delay:.28s;">
    <div style="position:relative;">
      <div class="speech" style="top:-26px;right:28px;border-radius:6px 6px 0 6px;">digital media</div>
    </div>
    <div class="av-body" style="width:36px;height:42px;background:rgba(155,106,164,.22);border:1px solid rgba(155,106,164,.45);">👾</div>
    <div class="av-shadow" style="width:26px;background:rgba(155,106,164,.12);"></div>
    <div class="av-label" style="color:rgba(196,160,204,.85);">extraction_05</div>
  </div>

  <!-- av-3: surplus — mid right -->
  <div class="av av-3" style="top:38%;right:10%;animation-delay:.45s;">
    <div style="position:relative;">
      <div class="speech" style="top:-26px;left:28px;border-radius:6px 6px 6px 0;">surplus value</div>
    </div>
    <div class="av-body" style="width:38px;height:44px;background:rgba(77,184,176,.2);border:1px solid rgba(77,184,176,.45);">💰</div>
    <div class="av-shadow" style="width:27px;background:rgba(77,184,176,.1);"></div>
    <div class="av-label" style="color:rgba(143,216,210,.85);">surplus</div>
  </div>

  <!-- av-4: capture — mid centre-right -->
  <div class="av av-4" style="top:42%;right:38%;animation-delay:.62s;">
    <div style="position:relative;">
      <div class="speech" style="top:-26px;right:28px;border-radius:6px 6px 0 6px;">capturing data</div>
    </div>
    <div class="av-body" style="width:36px;height:42px;background:rgba(232,212,138,.18);border:1px solid rgba(232,212,138,.4);">🧲</div>
    <div class="av-shadow" style="width:26px;background:rgba(232,212,138,.1);"></div>
    <div class="av-label" style="color:rgba(240,224,160,.85);">capture</div>
  </div>

  <!-- av-5: interface_24 — lower right -->
  <div class="av av-5" style="top:65%;right:14%;animation-delay:.78s;">
    <div style="position:relative;">
      <div class="speech" style="top:-26px;left:28px;border-radius:6px 6px 6px 0;">BCI online</div>
    </div>
    <div class="av-body" style="width:34px;height:40px;background:rgba(155,106,164,.2);border:1px solid rgba(155,106,164,.4);">🧠</div>
    <div class="av-shadow" style="width:24px;background:rgba(155,106,164,.1);"></div>
    <div class="av-label" style="color:rgba(196,160,204,.85);">interface_24</div>
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
      <p class="about-text">I am currently a sessional instructor at McMaster University in Hamilton, Canada. I was a Postdoctoral Visitor at York University's Department of Communication and Media Studies in 2024–2025, where I researched toxicity in video games. I completed my PhD in Communication, Rhetoric, and Digital Media at North Carolina State University.</p>
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

<!-- CV + CONTACT -->
<div class="cv-contact-section" id="cv">
  <div class="cv-top-stripe"></div>
  <div class="cv-blob cv-blob-a"></div>
  <div class="cv-blob cv-blob-b"></div>
  <div class="cv-blob cv-blob-c"></div>

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
