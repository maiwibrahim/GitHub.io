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
@import url('https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=Space+Mono:wght@400;700&family=Lora:ital,wght@0,400;0,500;1,400&display=swap');

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

.post, article { padding: 0 !important; margin: 0 !important; }
.post-header, .navbar, nav.navbar,
.p-name, .sidebar-header, .profile-name { display: none !important; }

/* NAV */
.site-nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 99999;
  background: rgba(20, 0, 35, 0.85);
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
  color: rgba(255,255,255,0.7);
  text-decoration: none;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  transition: color 0.2s;
}
.site-nav a:hover { color: #efcc00; }

/* HERO */
.hero {
  background: #0d0018;
  min-height: 100vh;
  width: 100vw;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 4rem 2rem;
  position: relative;
  overflow: hidden;
}
@keyframes rotate { from{transform:translate(-50%,-50%) rotate(0deg);} to{transform:translate(-50%,-50%) rotate(360deg);} }
@keyframes rotateReverse { from{transform:translate(-50%,-50%) rotate(0deg);} to{transform:translate(-50%,-50%) rotate(-360deg);} }
@keyframes fadeUp { from{opacity:0;transform:translateY(20px);} to{opacity:1;transform:translateY(0);} }
@keyframes flicker { 0%,96%,100%{opacity:1;} 97%{opacity:0.6;} 99%{opacity:0.8;} }

.hero-bg-glow {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 600px;
  height: 600px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(180,100,255,0.12) 0%, rgba(239,204,0,0.06) 40%, transparent 70%);
  transform: translate(-50%, -50%);
  pointer-events: none;
}

.portal-ring-1, .portal-ring-2, .portal-ring-3 { position: absolute; top: 50%; left: 50%; border-radius: 50%; }
.portal-ring-1 { width: 320px; height: 320px; border: 1.5px solid rgba(239,204,0,0.4); animation: rotate 25s linear infinite; }
.portal-ring-2 { width: 380px; height: 380px; border: 0.5px dashed rgba(180,100,255,0.3); animation: rotateReverse 20s linear infinite; }
.portal-ring-3 { width: 440px; height: 440px; border: 0.5px solid rgba(255,180,80,0.15); animation: rotate 35s linear infinite; }
.portal-dot, .portal-dot-2 { position: absolute; left: 50%; transform: translateX(-50%); border-radius: 50%; }
.portal-dot { width: 6px; height: 6px; background: #efcc00; top: 0; }
.portal-dot-2 { width: 5px; height: 5px; background: #b464ff; bottom: 0; }

.hero-name {
  font-family: 'DM Serif Display', Georgia, serif;
  font-size: clamp(48px, 10vw, 100px);
  font-weight: 400;
  margin-bottom: 1rem;
  position: relative;
  z-index: 10;
  animation: fadeUp 1s ease forwards, flicker 12s infinite;
}
.hero-desc {
  font-size: clamp(16px, 2.5vw, 22px);
  color: rgba(255,255,255,0.75);
  line-height: 1.7;
  font-style: italic;
  max-width: 600px;
  position: relative;
  z-index: 10;
  animation: fadeUp 1s ease 0.3s forwards;
  opacity: 0;
}
.hero-btn { position: relative; z-index: 10; margin-top: 2.5rem; animation: fadeUp 1s ease 0.6s forwards; opacity: 0; }
.hero-btn a {
  font-family: 'Space Mono', monospace;
  color: #0d0018;
  background: #efcc00;
  font-size: 11px;
  padding: 14px 36px;
  text-decoration: none;
  letter-spacing: 0.15em;
  display: inline-block;
}

/* ABOUT */
.about-section {
  background: #fdf6ee;
  width: 100vw;
  padding: 100px max(2.5rem, 6vw) 120px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 3rem;
}
.section-label { font-size: 16px; letter-spacing: 0.2em; text-transform: uppercase; color: #6b4472; margin-bottom: 2rem; font-family: 'Lora', serif; text-align: center; width: 100%; }
.about-inner { display: flex; gap: 6rem; flex-wrap: wrap; justify-content: center; align-items: flex-start; }

/* IMAGE STYLING */
.pubs-images { position: relative; display: flex; gap: -40px; flex-wrap: wrap; justify-content: center; }
.pubs-images img {
  border-radius: 8px;
  object-fit: cover;
  box-shadow: 0 20px 40px rgba(0,0,0,0.2);
  transition: transform 0.3s, z-index 0.3s;
  cursor: pointer;
}
.pubs-images img:hover { transform: scale(1.05) rotate(0deg); z-index: 10; }

/* TEXT COLUMN */
.text-col { max-width: 400px; display: flex; flex-direction: column; gap: 1.5rem; }
.about-text { font-size: 19px; line-height: 2; color: #5a3e2b; }

/* PUBLICATIONS */
.pubs-section {
  background: #fff;
  width: 100vw;
  padding: 120px max(2.5rem, 6vw) 4rem;
  margin-top: -60px;
  clip-path: polygon(0 0, 100% 60px, 100% 100%, 0 100%);
  color: #3a3228;
}
.pubs-section * { color: #3a3228; }
.pubs-section a { color: #3a3228; text-decoration: none; border-bottom: 0.5px solid rgba(58,50,40,0.3); }
.pubs-section a:hover { color: #6b4472; border-bottom-color: #6b4472; }
.pub-type-block { margin-bottom: 2.25rem; max-width: 100%; }
.pub-type-label { font-size: 15px; font-weight: 500; letter-spacing: 0.01em; margin-bottom: 0.9rem; padding: 6px 14px; display: inline-block; border-radius: 3px; }
.type-chapters  .pub-type-label { background: #fde8c8; color: #8a4e10; }
.type-articles  .pub-type-label { background: #d4eadb; color: #2c5c3c; }
.type-reviews   .pub-type-label { background: #dfe0f5; color: #3b3c80; }
.type-interview .pub-type-label { background: #ecd8f0; color: #5a2870; }
.pub-entry { font-size: 18px; line-height: 2; margin-bottom: 1rem; font-style: normal; font-family: 'Lora', serif; }
.pub-entry:last-child { margin-bottom: 0; }

/* CV */
.bottom-section { padding: 6rem max(2.5rem, 6vw); background: #fdf6ee; min-height: 100vh; width: 100vw; display: flex; flex-direction: column; justify-content: center; gap: 1rem; }
.cv-download { font-size: 14px; letter-spacing: 0.13em; text-transform: uppercase; color: #3d1f4a; background: #c9a0d6; text-decoration: none; padding: 10px 20px; border-radius: 2px; display: inline-block; }
.cv-download:hover { background: #b080c4; color: #fff; }

/* CONTACT */
.footer-section { padding: 6rem max(2.5rem, 6vw); background: #3d1f4a; min-height: 100vh; width: 100vw; display: flex; flex-direction: column; justify-content: center; gap: 1.75rem; }
.footer-link { font-size: 18px; color: #c9a0d6; text-decoration: none; font-style: italic; }
.footer-link:hover { color: #f0ddf5; }

/* MOBILE */
@media (max-width: 640px) {
  .about-inner { flex-direction: column; align-items: center; gap: 2rem; }
  .text-col { max-width: 100%; }
  .pubs-images img { width: 180px !important; height: auto !important; transform: rotate(0) !important; }
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
  <div class="hero-bg-glow"></div>
  <div class="portal-ring-3"><div class="portal-dot-2"></div></div>
  <div class="portal-ring-2"></div>
  <div class="portal-ring-1"><div class="portal-dot"></div></div>

  <h1 class="hero-name">
    <span style="color:#efcc00;">Mai</span>
    <span style="color:#c8a0ff;"> W.</span>
    <span style="color:#ffffff;"> Ibrahim</span>
  </h1>
  <p class="hero-desc">is a media theorist &amp; researcher of digital cultures</p>
  <div class="hero-btn"><a href="#about">VIEW PROFILE ↓</a></div>
</div>

<!-- ABOUT -->
<div class="about-section" id="about">
  <p class="section-label">About</p>
  <div class="about-inner">
    <!-- Images -->
    <div class="pubs-images">
      <img src="/assets/images/vr-headset.jpg" />
      <img src="/assets/images/vr-space.jpg" />
      <img src="/assets/images/bci-headset.jpg" />
      <img src="/assets/images/vr-museum.JPG" />
    </div>

    <!-- Text -->
    <div class="text-col">
      <p class="about-text">
        My research examines the relationship between digital media, pre-conscious intensities, and political economy. I investigate how digital media act upon the human body prior to conscious awareness, and in how platform capitalism transforms that bodily register into a site of extraction.
      </p>
      <p class="about-text">
        My work engages a wide range of media, including virtual reality, brain-computer interfaces, social media, video games, among others.
      </p>
      <p class="about-text">
        I am currently a sessional instructor at McMaster University in Hamilton, Canada. I was a Postdoctoral Visitor at York University’s Department of Communication and Media Studies in 2024–2025, where I researched toxicity in video games. I completed my PhD in Communication, Rhetoric, and Digital Media at North Carolina State University.
      </p>
    </div>
  </div>
</div>

<!-- PUBLICATIONS -->
<div class="pubs-section" id="publications">
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

<!-- CV -->
<div class="bottom-section" id="cv">
  <p class="section-label" style="margin-bottom:0;">CV</p>
  <a class="cv-download" href="/assets/pdf/cv.pdf" target="_blank">Download ↓</a>
</div>

<!-- CONTACT -->
<div class="footer-section" id="contact">
  <p class="section-label" style="color:#c9a0d6;">Contact</p>
  <a class="footer-link" href="mailto:mai.w.ibrahim@gmail.com">Email</a>
  <a class="footer-link" href="https://bsky.app/profile/mai
