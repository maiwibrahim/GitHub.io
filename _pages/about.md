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

.page *, .page *::before, .page *::after {
  box-sizing: border-box;
}

.post { padding: 0 !important; margin: 0 !important; }
article { padding: 0 !important; margin: 0 !important; }
.post-header { display: none !important; }
.navbar, nav.navbar { display: none !important; }
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
@keyframes depth { 0%,100%{transform:translate(-50%,-50%) scale(1);} 50%{transform:translate(-50%,-50%) scale(1.04);} }
@keyframes glow { 0%,100%{box-shadow:0 0 60px rgba(239,204,0,0.4), 0 0 120px rgba(180,100,255,0.3);} 50%{box-shadow:0 0 80px rgba(239,204,0,0.6), 0 0 160px rgba(180,100,255,0.5);} }
@keyframes fadeUp { from{opacity:0;transform:translateY(20px);} to{opacity:1;transform:translateY(0);} }
@keyframes flicker { 0%,96%,100%{opacity:1;} 97%{opacity:0.6;} 99%{opacity:0.8;} }
@keyframes particle { 0%{transform:translateY(0) translateX(0);opacity:0.8;} 100%{transform:translateY(-80px) translateX(20px);opacity:0;} }

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

.portal-ring-1 {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 320px;
  height: 320px;
  border-radius: 50%;
  border: 1.5px solid rgba(239,204,0,0.4);
  animation: rotate 25s linear infinite;
}

.portal-ring-2 {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 380px;
  height: 380px;
  border-radius: 50%;
  border: 0.5px dashed rgba(180,100,255,0.3);
  animation: rotateReverse 20s linear infinite;
}

.portal-ring-3 {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 440px;
  height: 440px;
  border-radius: 50%;
  border: 0.5px solid rgba(255,180,80,0.15);
  animation: rotate 35s linear infinite;
}

.portal-dot {
  position: absolute;
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: #efcc00;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
}

.portal-dot-2 {
  position: absolute;
  width: 5px;
  height: 5px;
  border-radius: 50%;
  background: #b464ff;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
}

.hero-name {
  font-family: 'DM Serif Display', Georgia, serif;
  font-size: clamp(48px, 10vw, 100px);
  font-weight: 400;
  font-style: normal;
  line-height: 1.05;
  letter-spacing: 0;
  margin-bottom: 1rem;
  display: block;
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

.hero-btn {
  position: relative;
  z-index: 10;
  margin-top: 2.5rem;
  animation: fadeUp 1s ease 0.6s forwards;
  opacity: 0;
}

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
  gap: 5rem;
  align-items: flex-start;
  justify-content: center;
  flex-wrap: wrap;
}

.about-img {
  width: 250px;
  height: auto;
  border-radius: 50%;
  object-fit: cover;
  box-shadow:0 20px 40px rgba(0,0,0,0.25);
}

.text-col {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  max-width: 500px;
}

.about-text {
  font-size: 19px;
  line-height: 2;
  color: #5a3e2b;
  margin: 0;
}

/* VR/BCI Images */
.pubs-images img {
  border-radius: 3px;
  object-fit: cover;
  box-shadow: 0 10px 30px rgba(0,0,0,0.15);
}

/* PUBLICATIONS */
.pubs-section {
  background: #fff;
  min-height: 100vh;
  width: 100vw;
  color: #3a3228;
  margin-top: -60px;
  clip-path: polygon(0 0, 100% 60px, 100% 100%, 0 100%);
  padding: 120px max(2.5rem, 6vw) 4rem;
}

.pubs-section * { color: #3a3228; }
.pubs-section a { color: #3a3228 !important; border-bottom: 0.5px solid rgba(58,50,40,0.3); text-decoration: none; }
.pubs-section a:hover { color: #6b4472 !important; border-bottom-color: #6b4472; }
.pubs-section .section-label { color: #3a6b52; margin-bottom: 2rem; text-align: left; }

.pub-type-block { margin-bottom: 2.25rem; max-width: 100%; }
.pub-type-block:last-child { margin-bottom: 0; }

.pub-type-label {
  font-size: 15px;
  font-weight: 500;
  font-style: normal;
  letter-spacing: 0.01em;
  margin-bottom: 0.9rem;
  padding: 6px 14px;
  display: inline-block;
  border-radius: 3px;
}

.type-chapters  .pub-type-label { background: #fde8c8; color: #8a4e10; }
.type-articles  .pub-type-label { background: #d4eadb; color: #2c5c3c; }
.type-reviews   .pub-type-label { background: #dfe0f5; color: #3b3c80; }
.type-interview .pub-type-label { background: #ecd8f0; color: #5a2870; }

.pub-entry {
  font-size: 18px;
  line-height: 2;
  color: #3a3228;
  margin-bottom: 1rem;
  font-style: normal;
  font-family: 'Lora', serif;
}

.pub-entry:last-child { margin-bottom: 0; }
.pub-entry em { font-style: italic; }
.pub-entry a { color: inherit; text-decoration: none; border-bottom: 0.5px solid rgba(58,50,40,0.3); }
.pub-entry a:hover { border-bottom-color: #6b4472; color: #6b4472 !important; }

/* CV */
.bottom-section {
  padding: 6rem max(2.5rem, 6vw);
  background: #fdf6ee;
  min-height: 100vh;
  width: 100vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 1rem;
}

.cv-download {
  font-size: 14px;
  letter-spacing: 0.13em;
  text-transform: uppercase;
  color: #3d1f4a;
  background: #c9a0d6;
  text-decoration: none;
  padding: 10px 20px;
  border-radius: 2px;
  font-style: normal;
  display: inline-block;
  width: fit-content;
}

.cv-download:hover { background: #b080c4; color: #fff; }

/* CONTACT */
.footer-section {
  padding: 6rem max(2.5rem, 6vw);
  background: #3d1f4a;
  min-height: 100vh;
  width: 100vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 1.75rem;
}

.footer-link {
  font-size: 18px;
  color: #c9a0d6;
  text-decoration: none;
  font-style: italic;
}

.footer-link:hover { color: #f0ddf5; }

/* MOBILE */
@media (max-width: 640px) {
  .about-inner { gap: 2rem; flex-direction: column; align-items: center; }
  .about-img { width:180px; height:auto; }
  .text-col { max-width:100%; }
  .about-text { font-size: 17px; }
  .pubs-section { padding-top: 80px; }
  .pub-entry { font-size: 15px; }
}

/* CUSTOM CURSOR */
* {
  cursor: url("data:image/svg+xml,%3Csvg width='32' height='44' viewBox='0 0 52 72' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M20 48 Q18 58 19 65 Q21 69 26 69 Q31 69 33 65 Q34 58 32 48 Z' fill='white'/%3E%3Cpath d='M18 42 Q26 46 34 42 L32 48 Q26 51 20 48 Z' fill='%23ececec'/%3E%3Ccircle cx='26' cy='22' r='20' fill='none' stroke='white' stroke-width='5'/%3E%3Cellipse cx='26' cy='10' rx='9' ry='7' fill='white'/%3E%3Ccircle cx='29' cy='9' r='2.5' fill='%23e0e0e0'/%3E%3Ccircle cx='23' cy='9' r='2.5' fill='%23e0e0e0'/%3E%3Cellipse cx='26' cy='32' rx='8' ry='6' fill='white'/%3E%3Ccircle cx='26' cy='32' r='4' fill='%23e0e0e0'/%3E%3Ccircle cx='26' cy='32' r='2.5' fill='%23c8c8c8'/%3E%3C/svg%3E") 16 14, auto !important;
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

  <div class="portal-ring-3">
    <div class="portal-dot-2"></div>
  </div>
  <div class="portal-ring-2"></div>
  <div class="portal-ring-1">
    <div class="portal-dot"></div>
  </div>

  <h1 class="hero-name">
    <span style="color:#efcc00;">Mai</span>
    <span style="color:#c8a0ff;"> W.</span>
    <span style="color:#ffffff;"> Ibrahim</span>
  </h1>
  <p class="hero-desc">is a media theorist &amp; researcher of digital cultures</p>
  <div class="hero-btn">
    <a href="#about">VIEW PROFILE ↓</a>
  </div>
</div>

<!-- ABOUT -->
<div class="about-section" id="about">
  <p class="section-label">About</p>
  <div class="about-inner">

    <!-- Left: Profile picture -->
    <div style="flex-shrink:0;">
      <img class="about-img" src="/assets/images/your-pic.jpg" alt="Mai W. Ibrahim"/>
    </div>

    <!-- Right: Text + VR/BCI images -->
    <div style="display:flex; flex-direction:column; gap:2rem;">

      <!-- Text Column -->
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

      <!-- Floating Images -->
      <div class="pubs-images" style="position:relative; height:400px; width:100%; display:flex; justify-content:center; align-items:center; gap:1.5rem;">
        <img src="/assets/images/vr-headset.jpg" style="width:180px; transform:rotate(-8deg);"/>
        <img src="/assets/images/vr-space.jpg" style="width:220px; transform:rotate(6deg);"/>
        <img src="/assets/images/bci-headset.jpg" style="width:200px; transform:rotate(-3deg);"/>
        <img src="/assets/images/vr-museum.JPG" style="width:170px; transform:rotate(5deg);"/>
      </div>

    </div>
  </div>
</div>

<!-- PUBLICATIONS -->
<div class="pubs-section" id="publications">
  <p class="section-label">Selected Publications</p>
  <!-- Example: Repeat this block for each publication type -->
  <div class="pub-type-block type-articles">
    <span class="pub-type-label">Articles</span>
    <p class="pub-entry">Ibrahim, M. (2025). <em>Example article title</em>. <a href="#">Journal Name</a></p>
    <p class="pub-entry">Ibrahim, M. (2024). <em>Another article</em>. <a href="#">Journal Name</a></p>
  </div>
</div>

<!-- CV -->
<div class="bottom-section" id="cv">
  <p class="section-label">CV</p>
  <a href="/assets/files/Mai-Ibrahim-CV.pdf" class="cv-download" target="_blank">Download CV</a>
</div>

<!-- CONTACT -->
<div class="footer-section" id="contact">
  <p class="section-label">Contact</p>
  <a href="mailto:mai.ibrahim@email.com" class="footer-link">mai.ibrahim@email.com</a>
  <a href="https://www.linkedin.com/in/mai-ibrahim" target="_blank" class="footer-link">LinkedIn</a>
  <a href="https://twitter.com/maiibrahim" target="_blank" class="footer-link">Twitter</a>
</div>

</div>
