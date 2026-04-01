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

.post, article { padding: 0 !important; margin: 0 !important; }
.post-header, .navbar, nav.navbar, .p-name, .sidebar-header, .profile-name { display: none !important; }

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
@keyframes floatSlow { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-15px); } }

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

.portal-ring-1, .portal-ring-2, .portal-ring-3 {
  position: absolute;
  top: 50%;
  left: 50%;
  border-radius: 50%;
  pointer-events: none;
}

.portal-ring-1 { width: 320px; height: 320px; border: 1.5px solid rgba(239,204,0,0.4); animation: rotate 60s linear infinite; }
.portal-ring-2 { width: 380px; height: 380px; border: 0.5px dashed rgba(180,100,255,0.3); animation: rotateReverse 90s linear infinite; }
.portal-ring-3 { width: 440px; height: 440px; border: 0.5px solid rgba(255,180,80,0.15); animation: rotate 120s linear infinite; }

.portal-dot, .portal-dot-2 {
  position: absolute;
  border-radius: 50%;
}

.portal-dot { width: 6px; height: 6px; background: #efcc00; top: 0; left: 50%; transform: translateX(-50%); }
.portal-dot-2 { width: 5px; height: 5px; background: #b464ff; bottom: 0; left: 50%; transform: translateX(-50%); }

.hero-name {
  font-family: 'DM Serif Display', Georgia, serif;
  font-size: clamp(48px, 10vw, 100px);
  font-weight: 400;
  line-height: 1.05;
  margin-bottom: 1rem;
  color: #fff;
  animation: fadeUp 1s ease forwards;
  z-index: 10;
  position: relative;
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
.hero-btn a { font-family: 'Space Mono', monospace; color: #0d0018; background: #efcc00; font-size: 11px; padding: 14px 36px; text-decoration: none; letter-spacing: 0.15em; }

/* ABOUT */
.about-section {
  background: #fdf6ee;
  width: 100vw;
  padding: 100px max(2.5rem, 6vw) 120px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.section-label { font-size: 16px; letter-spacing: 0.2em; text-transform: uppercase; color: #6b4472; margin-bottom: 2rem; font-style: normal; font-family: 'Lora', serif; text-align: center; width: 100%; }

.about-inner { display: flex; flex-wrap: wrap; justify-content: center; align-items: flex-start; gap: 3rem; }

.about-img, .vr-img { border-radius: 5px; object-fit: cover; }

.about-img { width: 300px; height: 400px; animation: fadeUp 1.5s ease forwards; }

.vr-img { width: 280px; height: 340px; animation: fadeUp 2s ease forwards; animation-delay: 0.2s; transition: transform 0.5s; animation-name: fadeUp, floatSlow; animation-duration: 2s, 6s; animation-iteration-count: 1, infinite; animation-timing-function: ease, ease-in-out; }

.vr-img:nth-child(3) { animation-delay: 0.4s; }
.vr-img:nth-child(4) { animation-delay: 0.6s; }

.text-col { max-width: 480px; display: flex; flex-direction: column; gap: 1.5rem; }

.about-text { font-size: 19px; line-height: 2; color: #5a3e2b; margin: 0; }

/* PUBLICATIONS */
.pubs-section {
  background: #fff;
  min-height: 100vh;
  width: 100vw;
  color: #3a3228;
  padding: 120px max(2.5rem, 6vw) 4rem;
}

/* CV */
.bottom-section { padding: 6rem max(2.5rem, 6vw); background: #fdf6ee; min-height: 100vh; display: flex; flex-direction: column; justify-content: center; gap: 1rem; }
.cv-download { font-size: 14px; letter-spacing: 0.13em; text-transform: uppercase; color: #3d1f4a; background: #c9a0d6; text-decoration: none; padding: 10px 20px; border-radius: 2px; display: inline-block; }
.cv-download:hover { background: #b080c4; color: #fff; }

/* CONTACT */
.footer-section { padding: 6rem max(2.5rem, 6vw); background: #3d1f4a; min-height: 100vh; width: 100vw; display: flex; flex-direction: column; justify-content: center; gap: 1.75rem; }
.footer-link { font-size: 18px; color: #c9a0d6; text-decoration: none; font-style: italic; }
.footer-link:hover { color: #f0ddf5; }

/* MOBILE */
@media (max-width: 768px) {
  .about-inner { flex-direction: column; align-items: center; gap: 2.5rem; }
  .about-img, .vr-img { width: 200px; height: 240px; }
  .text-col { max-width: 100%; }
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
  <p class="hero-desc">is a media theorist & researcher of digital cultures</p>
  <div class="hero-btn">
    <a href="#about">VIEW PROFILE ↓</a>
  </div>
</div>

<!-- ABOUT -->
<div class="about-section" id="about">
  <p class="section-label">About</p>
  <div class="about-inner">
    <!-- Your photo -->
    <img class="about-img" src="prof_pic.jpg" alt="Mai W. Ibrahim"/>

    <!-- VR & BCI images -->
    <img class="vr-img" src="vr-headset.jpg" alt="VR Headset"/>
    <img class="vr-img" src="vr-space.jpg" alt="VR Space"/>
    <img class="vr-img" src="bci-headset.jpg" alt="BCI Headset"/>
    <img class="vr-img" src="vr-museum.jpg" alt="VR Museum"/>

    <div class="text-col">
      <p class="about-text">My research examines the relationship between digital media, pre-conscious intensities, and political economy. I investigate how digital media act upon the human body prior to conscious awareness, and in how platform capitalism transforms that bodily register into a site of extraction.</p>
      <p class="about-text">My work engages a wide range of media, including virtual reality, brain-computer interfaces, social media, video games, among others.</p>
      <p class="about-text">I am currently a sessional instructor at McMaster University in Hamilton, Canada. I was a Postdoctoral Visitor at York University’s Department of Communication and Media Studies in 2024–2025, where I researched toxicity in video games. I completed my PhD in Communication, Rhetoric, and Digital Media at North Carolina State University.</p>
    </div>
  </div>
</div>

<!-- PUBLICATIONS -->
<div class="pubs-section" id="publications">
  <p class="section-label">Research & Publications</p>
  <!-- Publication entries go here -->
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
  <a class="footer-link" href="https://bsky.app/profile/maiibrahim.bsky.social">Bluesky</a>
  <a class="footer-link" href="https://scholar.google.ca/citations?user=e39G1iYAAAAJ">Google Scholar</a>
</div>

</div>
