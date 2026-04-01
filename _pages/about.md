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

:root { --nav-h: 52px; }

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

/* NAV */
.site-nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 99999;
  background: rgba(13, 0, 40, 0.85);
  backdrop-filter: blur(10px);
  display: flex;
  gap: 2rem;
  align-items: center;
  justify-content: flex-end;
  height: 52px;
  padding: 0 3rem;
}
.site-nav a {
  font-family: 'Space Mono', monospace;
  font-size: 12px;
  color: rgba(255,255,255,0.6);
  text-decoration: none;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  transition: color 0.2s;
}
.site-nav a:hover { color: #a060ff; }

/* HERO */
.hero {
  background: #0d0028;
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
  height: 220px;
  background-image:
    linear-gradient(rgba(120,60,255,0.14) 1px, transparent 1px),
    linear-gradient(90deg, rgba(120,60,255,0.14) 1px, transparent 1px);
  background-size: 50px 30px;
  transform: perspective(500px) rotateX(55deg);
  transform-origin: bottom;
}
.floor-glow {
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 220px;
  background: linear-gradient(0deg, rgba(80,0,180,0.18), transparent);
  border-top: 1px solid rgba(120,60,255,0.25);
}
.ui-dots {
  position: absolute;
  top: 16px; right: 20px;
  display: flex;
  gap: 5px;
  z-index: 10;
}
.ui-dots span { width: 6px; height: 6px; border-radius: 50%; }
.av {
  position: absolute;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 3px;
  z-index: 5;
}
.av-body {
  border-radius: 50% 50% 40% 40%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 14px;
}
.av-shadow { border-radius: 50%; height: 5px; }
.av-label {
  font-family: 'Space Mono', monospace;
  font-size: 7px;
  letter-spacing: 0.05em;
  background: rgba(0,0,0,0.5);
  padding: 1px 5px;
  border-radius: 2px;
  white-space: nowrap;
}
.speech {
  position: absolute;
  background: rgba(255,255,255,0.07);
  border: 0.5px solid rgba(255,255,255,0.14);
  padding: 3px 7px;
  font-size: 7px;
  font-family: 'Space Mono', monospace;
  color: rgba(255,255,255,0.55);
  white-space: nowrap;
  border-radius: 6px 6px 6px 0;
}
.hero-content {
  position: relative;
  z-index: 10;
  display: flex;
  flex-direction: column;
  gap: 12px;
  max-width: 580px;
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
.hero-name .first { color: #a060ff; }
.hero-name .rest { color: #f0eaff; }
.hero-name em { font-style: italic; color: rgba(240,234,255,0.65); }
.hero-desc {
  font-size: clamp(14px, 2vw, 18px);
  color: rgba(240,234,255,0.45);
  font-style: italic;
  line-height: 1.6;
  margin: 0;
}
.hero-btn { margin-top: 8px; }
.hero-btn a {
  font-family: 'Space Mono', monospace;
  font-size: 11px;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: #0d0028;
  background: #a060ff;
  padding: 12px 28px;
  text-decoration: none;
  display: inline-block;
  transition: background 0.2s;
}
.hero-btn a:hover { background: #b880ff; }

/* ABOUT */
.about-section {
  background: #fdf6ee;
  width: 100vw;
  padding: 110px max(2.5rem, 6vw) 130px;
  margin-top: -60px;
  clip-path: polygon(0 60px, 100% 0, 100% 100%, 0 100%);
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.section-label {
  font-size: 16px;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: #6b4472;
  margin-bottom: 2rem;
  font-style: normal;
  font-family: 'Lora', serif;
  text-align: center;
  width: 100%;
}
.about-inner {
  display: flex;
  gap: 7rem;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
}
.about-img {
  width: 260px;
  height: 335px;
  object-fit: cover;
  object-position: top;
  border-radius: 3px;
  flex-shrink: 0;
  transform: rotate(-3deg);
}
.text-col {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  max-width: 400px;
  transform: rotate(-3deg);
  min-width: 260px;
}
.about-text {
  font-size: 19px;
  line-height: 2;
  color: #5a3e2b;
  margin: 0;
}

/* PUBLICATIONS — floating images */
@keyframes floatA { 0%,100%{transform:translateY(0px) rotate(-4deg);} 50%{transform:translateY(-18px) rotate(-4deg);} }
@keyframes floatB { 0%,100%{transform:translateY(0px) rotate(3deg);} 50%{transform:translateY(-14px) rotate(3deg);} }
@keyframes floatC { 0%,100%{transform:translateY(0px) rotate(-2deg);} 50%{transform:translateY(-20px) rotate(-2deg);} }
@keyframes floatD { 0%,100%{transform:translateY(0px) rotate(5deg);} 50%{transform:translateY(-12px) rotate(5deg);} }

.pubs-section {
  background: #fff;
  min-height: 100vh;
  width: 100vw;
  color: #3a3228;
  margin-top: -60px;
  clip-path: polygon(0 0, 100% 60px, 100% 100%, 0 100%);
  padding: 130px max(2.5rem, 6vw) 5rem;
  position: relative;
  overflow: hidden;
}
.pubs-section * { color: #3a3228; }
.pubs-section a { color: #3a3228 !important; border-bottom: 0.5px solid rgba(58,50,40,0.3); text-decoration: none; }
.pubs-section a:hover { color: #6b4472 !important; border-bottom-color: #6b4472; }
.pubs-section .section-label { color: #3a6b52; margin-bottom: 2rem; text-align: left; }

.pub-img-float {
  position: absolute;
  z-index: 2;
  overflow: hidden;
  border-radius: 4px;
  box-shadow: 0 8px 32px rgba(0,0,0,0.1);
}
.pub-img-float img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  opacity: 0.15;
  filter: grayscale(15%);
  transition: opacity 0.4s;
}
.pub-img-float:hover img { opacity: 0.35; }

.pub-img-a { width: 160px; height: 115px; top: 120px; right: 40px; animation: floatA 8s ease-in-out infinite; }
.pub-img-b { width: 130px; height: 165px; top: 280px; right: 210px; animation: floatB 10s ease-in-out infinite; }
.pub-img-c { width: 150px; height: 110px; bottom: 140px; right: 50px; animation: floatC 9s ease-in-out infinite; }
.pub-img-d { width: 140px; height: 130px; bottom: 280px; right: 215px; animation: floatD 7s ease-in-out infinite; }

.pub-content { position: relative; z-index: 10; max-width: 680px; }

.pub-type-block { margin-bottom: 2.5rem; max-width: 100%; }
.pub-type-block:last-child { margin-bottom: 0; }
.pub-type-label {
  font-size: 13px;
  font-weight: 500;
  letter-spacing: 0.01em;
  margin-bottom: 1rem;
  padding: 5px 14px;
  display: inline-block;
  border-radius: 3px;
}
.type-chapters  .pub-type-label { background: #fde8c8; color: #8a4e10; }
.type-articles  .pub-type-label { background: #d4eadb; color: #2c5c3c; }
.type-reviews   .pub-type-label { background: #dfe0f5; color: #3b3c80; }
.type-interview .pub-type-label { background: #ecd8f0; color: #5a2870; }
.pub-entry {
  font-size: 16px;
  line-height: 1.9;
  color: #3a3228;
  margin-bottom: 0.9rem;
  font-family: 'Lora', serif;
}
.pub-entry:last-child { margin-bottom: 0; }
.pub-entry em { font-style: italic; }
.pub-entry a { color: inherit; text-decoration: none; border-bottom: 0.5px solid rgba(58,50,40,0.3); }
.pub-entry a:hover { border-bottom-color: #6b4472; color: #6b4472 !important; }

/* CV */
.bottom-section {
  background: #0d0028;
  min-height: 100vh;
  width: 100vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  padding: 6rem max(2.5rem, 6vw);
  position: relative;
  overflow: hidden;
}
.bottom-section::before {
  content: 'CV';
  position: absolute;
  right: -20px;
  bottom: -40px;
  font-family: 'DM Serif Display', Georgia, serif;
  font-size: 280px;
  color: rgba(160,96,255,0.04);
  line-height: 1;
  pointer-events: none;
}
.bottom-section .section-label {
  color: rgba(160,96,255,0.7);
  margin-bottom: 1rem;
  text-align: left;
}
.cv-tagline {
  font-family: 'Lora', serif;
  font-size: 18px;
  color: rgba(240,234,255,0.45);
  font-style: italic;
  line-height: 1.7;
  max-width: 420px;
  margin-bottom: 2.5rem;
}
.cv-download {
  font-family: 'Space Mono', monospace;
  font-size: 12px;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: #0d0028;
  background: #a060ff;
  text-decoration: none;
  padding: 14px 32px;
  display: inline-flex;
  align-items: center;
  gap: 10px;
  transition: background 0.2s;
}
.cv-download:hover { background: #b880ff; color: #0d0028; }
.cv-download::after { content: '↓'; font-size: 16px; }

/* CONTACT */
.footer-section {
  background: #fdf6ee;
  min-height: 100vh;
  width: 100vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 6rem max(2.5rem, 6vw);
  position: relative;
  overflow: hidden;
}
.footer-section::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 4px;
  background: linear-gradient(90deg, #a060ff, #00dcb4, #ff3cb4);
}
.footer-section .section-label { color: #6b4472; margin-bottom: 3rem; text-align: left; }
.contact-grid {
  display: flex;
  flex-direction: column;
  gap: 0;
  max-width: 500px;
}
.contact-row {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1.4rem 0;
  border-bottom: 0.5px solid rgba(107,68,114,0.15);
  text-decoration: none;
  color: #3a3228;
  transition: padding-left 0.25s, color 0.2s;
}
.contact-row:first-child { border-top: 0.5px solid rgba(107,68,114,0.15); }
.contact-row:hover { padding-left: 0.75rem; color: #6b4472; }
.contact-label {
  font-family: 'Space Mono', monospace;
  font-size: 10px;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: #c9a0d6;
  min-width: 100px;
}
.contact-value {
  font-family: 'Lora', serif;
  font-size: 17px;
  font-style: italic;
  color: inherit;
  flex: 1;
  padding: 0 1rem;
}
.contact-arrow {
  font-family: 'Space Mono', monospace;
  font-size: 14px;
  color: #c9a0d6;
  transition: transform 0.2s, color 0.2s;
}
.contact-row:hover .contact-arrow { transform: translateX(5px); color: #6b4472; }

/* MOBILE */
@media (max-width: 640px) {
  .site-nav { justify-content: flex-start; padding: 0 1.5rem; gap: 1.25rem; }
  .site-nav a { font-size: 10px; }
  .hero { padding: 0 1.5rem; align-items: flex-end; padding-bottom: 60px; }
  .hero-name { white-space: normal; }
  .about-section { clip-path: polygon(0 30px, 100% 0, 100% 100%, 0 100%); padding: 80px 1.5rem 80px; margin-top: -30px; }
  .about-inner { flex-direction: column; align-items: center; gap: 3rem; }
  .about-img { transform: rotate(-2deg); width: 200px; height: 260px; }
  .text-col { transform: rotate(-2deg); max-width: 100%; min-width: unset; }
  .about-text { font-size: 17px; }
  .pubs-section { clip-path: polygon(0 0, 100% 30px, 100% 100%, 0 100%); padding-top: 80px; margin-top: -30px; }
  .pub-entry { font-size: 14px; }
  .pub-img-float { display: none; }
  .av { display: none; }
  .contact-value { font-size: 15px; }
}
</style>

<div class="page">

<nav class="site-nav">
  <a href="#about">ABOUT</a>
  <a href="#publications">PUBLICATIONS</a>
  <a href="#cv">CV</a>
  <a href="#contact">CONTACT</a>
</nav>

<!-- HERO -->
<div class="hero" id="hero">
  <div class="floor-grid"></div>
  <div class="floor-glow"></div>
  <div class="ui-dots">
    <span style="background:#ff5f57;"></span>
    <span style="background:#febc2e;"></span>
    <span style="background:#28c840;"></span>
  </div>

  <div class="av" style="top:18%;right:18%;">
    <div style="position:relative;">
      <div class="speech" style="top:-28px;left:30px;">hello! 👋</div>
    </div>
    <div class="av-body" style="width:36px;height:42px;background:rgba(255,100,80,0.2);border:1px solid rgba(255,100,80,0.5);">😊</div>
    <div class="av-shadow" style="width:26px;background:rgba(255,100,80,0.15);"></div>
    <div class="av-label" style="color:rgba(255,180,160,0.8);">user_42</div>
  </div>
  <div class="av" style="top:28%;right:32%;">
    <div class="av-body" style="width:30px;height:36px;background:rgba(80,200,255,0.2);border:1px solid rgba(80,200,255,0.45);">🤖</div>
    <div class="av-shadow" style="width:22px;background:rgba(80,200,255,0.12);"></div>
    <div class="av-label" style="color:rgba(160,220,255,0.8);">xr_wanderer</div>
  </div>
  <div class="av" style="top:14%;right:44%;">
    <div style="position:relative;">
      <div class="speech" style="top:-26px;right:28px;border-radius:6px 6px 0 6px;">✨ vr life</div>
    </div>
    <div class="av-body" style="width:32px;height:38px;background:rgba(180,80,255,0.2);border:1px solid rgba(180,80,255,0.45);">👾</div>
    <div class="av-shadow" style="width:24px;background:rgba(180,80,255,0.12);"></div>
    <div class="av-label" style="color:rgba(220,160,255,0.8);">meta_ghost</div>
  </div>
  <div class="av" style="top:32%;right:10%;">
    <div class="av-body" style="width:28px;height:34px;background:rgba(0,220,180,0.2);border:1px solid rgba(0,220,180,0.45);">🧑‍💻</div>
    <div class="av-shadow" style="width:20px;background:rgba(0,220,180,0.12);"></div>
    <div class="av-label" style="color:rgba(160,255,220,0.8);">dev_presence</div>
  </div>
  <div class="av" style="top:22%;right:58%;">
    <div style="position:relative;">
      <div class="speech" style="top:-26px;left:28px;">researching 🔍</div>
    </div>
    <div class="av-body" style="width:28px;height:34px;background:rgba(255,200,0,0.18);border:1px solid rgba(255,200,0,0.4);">🌐</div>
    <div class="av-shadow" style="width:20px;background:rgba(255,200,0,0.1);"></div>
    <div class="av-label" style="color:rgba(255,230,150,0.8);">digital_nomad</div>
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
    <img class="about-img" src="/assets/img/prof_pic.jpg" alt="Mai W. Ibrahim" />
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

<!-- CV -->
<div class="bottom-section" id="cv">
  <p class="section-label">CV</p>
  <p class="cv-tagline">A full record of my academic appointments, research, teaching, and service.</p>
  <a class="cv-download" href="/assets/pdf/cv.pdf" target="_blank">Download CV</a>
</div>

<!-- CONTACT -->
<div class="footer-section" id="contact">
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
