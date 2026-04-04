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

/* Avatars — Design 3 style */
.av {
  position:absolute;
  display:flex;
  flex-direction:column;
  align-items:center;
  gap:3px;
  z-index:5;
  opacity:0;animation:avFloat .7s ease forwards;
}
@keyframes avFloat {
  from{opacity:0;transform:translateY(14px);}
  to  {opacity:1;transform:translateY(0);}
}
.av-body {
  border-radius:50% 50% 40% 40%;
  display:flex;
  align-items:center;
  justify-content:center;
  font-size:14px;
}
.av-shadow {
  border-radius:50%;
  height:5px;
}
.av-label {
  font-family:'Space Mono',monospace;font-size:8px;
  letter-spacing:.05em;
  background:rgba(0,0,0,.42);padding:2px 6px;border-radius:2px;white-space:nowrap;
}
.speech {
  position:absolute;
  background:rgba(255,255,255,.07);
  border:.5px solid rgba(255,255,255,.18);
  padding:3px 9px;
  font-size:9px;
  font-family:'Space Mono',monospace;
  color:rgba(255,255,255,.65);
  white-space:nowrap;
  border-radius:6px 6px 6px 0;
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
  .av { display:none; }
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

  <!-- Avatar 1: glitch_24 — top-right, no speech bubble -->
  <div class="av" style="top:17%;right:8%;animation-delay:.10s;">
    <div class="av-body" style="width:36px;height:42px;background:rgba(13,191,180,.2);border:1px solid rgba(13,191,180,.5);">👾</div>
    <div class="av-shadow" style="width:26px;background:rgba(13,191,180,.15);"></div>
    <div class="av-label" style="color:rgba(128,232,227,.85);">glitch_24</div>
  </div>

  <!-- Avatar 2: intensity02 — mid-right, no speech bubble -->
  <div class="av" style="top:30%;right:22%;animation-delay:.22s;">
    <div class="av-body" style="width:32px;height:38px;background:rgba(245,226,122,.18);border:1px solid rgba(245,226,122,.48);">🤖</div>
    <div class="av-shadow" style="width:23px;background:rgba(245,226,122,.12);"></div>
    <div class="av-label" style="color:rgba(249,237,170,.85);">intensity02</div>
  </div>

  <!-- Avatar 3: extraction05 — with "digital media" speech bubble -->
  <div class="av" style="top:22%;right:38%;animation-delay:.34s;">
    <div style="position:relative;">
      <div class="speech" style="top:-28px;right:26px;border-radius:6px 6px 0 6px;">digital media</div>
    </div>
    <div class="av-body" style="width:30px;height:36px;background:rgba(255,61,130,.2);border:1px solid rgba(255,61,130,.48);">😊</div>
    <div class="av-shadow" style="width:22px;background:rgba(255,61,130,.13);"></div>
    <div class="av-label" style="color:rgba(255,111,163,.85);">extraction05</div>
  </div>

  <!-- Avatar 4: ambient — lower right, with "researching" speech bubble -->
  <div class="av" style="top:50%;right:12%;animation-delay:.46s;">
    <div style="position:relative;">
      <div class="speech" style="top:-28px;left:28px;display:inline-flex;align-items:center;gap:5px;">
        <svg width="10" height="10" viewBox="0 0 12 12" fill="none" xmlns="http://www.w3.org/2000/svg" style="flex-shrink:0;">
          <circle cx="5" cy="5" r="3.4" stroke="rgba(255,255,255,0.65)" stroke-width="1.3"/>
          <line x1="7.4" y1="7.4" x2="11" y2="11" stroke="rgba(255,255,255,0.65)" stroke-width="1.4" stroke-linecap="round"/>
        </svg>
        researching
      </div>
    </div>
    <div class="av-body" style="width:28px;height:34px;background:rgba(0,220,180,.2);border:1px solid rgba(0,220,180,.45);">🌐</div>
    <div class="av-shadow" style="width:20px;background:rgba(0,220,180,.12);"></div>
    <div class="av-label" style="color:rgba(160,255,220,.85);">ambient</div>
  </div>

  <!-- Avatar 5: infrastructure — lower-mid right, no speech bubble -->
  <div class="av" style="top:62%;right:33%;animation-delay:.58s;">
    <div class="av-body" style="width:28px;height:34px;background:rgba(180,80,255,.2);border:1px solid rgba(180,80,255,.45);">🧑‍💻</div>
    <div class="av-shadow" style="width:20px;background:rgba(180,80,255,.12);"></div>
    <div class="av-label" style="color:rgba(220,160,255,.85);">infrastructure</div>
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
