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
@import url('https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=IM+Fell+English:ital@0;1&family=Lora:ital,wght@0,400;0,500;1,400&display=swap');

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

/* HERO */
.hero {
  background: #6b4472;
  padding: 4rem max(2.5rem, 6vw) 3.5rem;
  min-height: 100vh;
  width: 100vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.hero-name {
  font-family: 'DM Serif Display', Georgia, serif;
  font-size: clamp(48px, 12vw, 130px);
  font-weight: 400;
  font-style: normal;
  line-height: 1.05;
  letter-spacing: 0;
  margin-bottom: 1.1rem;
  width: 100%;
  text-align: center;
  display: block;
  white-space: normal;
}
.hero-desc {
  font-size: clamp(16px, 3vw, 22px);
  color: #ffffff;
  line-height: 1.7;
  font-style: italic;
  max-width: 600px;
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
  gap: 10rem;
  align-items: flex-start;
  justify-content: center;
  flex-wrap: wrap;
}
.about-img {
  width: 280px;
  height: 360px;
  object-fit: cover;
  object-position: top;
  border-radius: 3px;
  flex-shrink: 0;
  transform: rotate(-8deg);
  margin-top: 10px;
}
.text-col {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  max-width: 380px;
  transform: rotate(6deg);
  margin-top: 10px;
  min-width: 260px;
  margin-left: 2rem;
}
.about-text {
  font-size: 19px;
  line-height: 2;
  color: #5a3e2b;
  margin: 0;
}

/* RESEARCH */
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
.pubs-section a {
  color: #3a3228 !important;
  border-bottom: 0.5px solid rgba(58,50,40,0.3);
}
.pubs-section a:hover { color: #6b4472 !important; }
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
.pub-entry a {
  color: inherit;
  text-decoration: none;
  border-bottom: 0.5px solid rgba(58,50,40,0.3);
}
.pub-entry a:hover { border-bottom-color: #6b4472; color: #6b4472; }

/* CV */
.bottom-section {
  padding: 4rem max(2.5rem, 6vw);
  background: #fdf6ee;
  min-height: 100vh;
  width: 100vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 1rem;
}
.cv-download {
  font-size: 13px;
  letter-spacing: 0.13em;
  text-transform: uppercase;
  color: #3d1f4a;
  background: #c9a0d6;
  text-decoration: none;
  padding: 7px 16px;
  border-radius: 2px;
  font-style: normal;
  display: inline-block;
  width: fit-content;
}
.cv-download:hover { background: #b080c4; color: #fff; }

/* CONTACT */
.footer-section {
  padding: 4rem max(2.5rem, 6vw);
  background: #3d1f4a;
  min-height: 100vh;
  width: 100vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 1.75rem;
}
.footer-link {
  font-size: 16px;
  color: #c9a0d6;
  text-decoration: none;
  font-style: italic;
}
.footer-link:hover { color: #f0ddf5; }
.footer-sep { color: #6b3d7a; font-size: 12px; }

.post { padding: 0 !important; margin: 0 !important; }
article { padding: 0 !important; margin: 0 !important; }
.post-header { display: none !important; }
.navbar, nav.navbar { display: none !important; }

/* MOBILE */
@media (max-width: 640px) {
  .about-section {
    clip-path: polygon(0 30px, 100% 0, 100% 100%, 0 100%);
    padding: 80px 1.5rem 80px;
    margin-top: -30px;
  }
  .about-inner {
    gap: 2rem;
  }
  .about-img {
    transform: rotate(-2deg);
    width: 180px;
    height: 230px;
  }
  .text-col {
    transform: rotate(-2deg);
    max-width: 100%;
    min-width: unset;
  }
  .about-text { font-size: 17px; }
  .pubs-section {
    clip-path: polygon(0 0, 100% 30px, 100% 100%, 0 100%);
    padding-top: 80px;
    margin-top: -30px;
  }
  .pub-entry { font-size: 14px; }
}
</style>

<div class="page">

<nav style="position:fixed;top:0;left:0;right:0;z-index:99999;background:#6b4472;padding:0 max(1.5rem,4vw);display:flex;gap:2rem;align-items:center;justify-content:flex-end;height:52px;">
  <a href="#about" style="font-family:'Lora',serif;font-size:15px;color:#f7edfb;text-decoration:none;letter-spacing:0.12em;">ABOUT</a>
  <a href="#publications" style="font-family:'Lora',serif;font-size:15px;color:#f7edfb;text-decoration:none;letter-spacing:0.12em;">PUBLICATIONS</a>
  <a href="#cv" style="font-family:'Lora',serif;font-size:15px;color:#f7edfb;text-decoration:none;letter-spacing:0.12em;">CV</a>
  <a href="#contact" style="font-family:'Lora',serif;font-size:15px;color:#f7edfb;text-decoration:none;letter-spacing:0.12em;">CONTACT</a>
</nav>

<!-- HERO -->
<div class="hero" id="hero">
  <h1 class="hero-name">
    <span style="color:#efcc00;">Mai</span>
    <span style="color:#d9b8e0;"> W.</span>
    <span style="color:#efcc00;"> Ibrahim</span>
  </h1>
  <p class="hero-desc">is a media theorist &amp; researcher of digital cultures</p>
</div>

<!-- ABOUT -->
<div class="about-section" id="about">
  <p class="section-label">About</p>
  <div class="about-inner">
    <img class="about-img" src="/assets/img/prof_pic.jpg" alt="Mai W. Ibrahim" />
    <div class="text-col">
      <p class="about-text">My research examines the relationship between digital media, pre-conscious intensities, and political economy. I investigate how digital media act upon the human body prior to conscious awareness, and in how platform capitalism transforms that bodily register into a site of extraction.</p>
      <p class="about-text">My work engages a wide range of media, including virtual reality, brain-computer interfaces, social media, video games, among others.</p>
      <p class="about-text">I am currently a sessional instructor at McMaster University in Hamilton, Canada.</p>
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
    <p class="pub-entry">Ibrahim, M. (2021). <a href="/assets/pdf/nihilism-review.pdf" target="_blank">Review of the book <em>Nihilism and Technology</em>, by N. Gertz</a>. <em>Communication Design Quarterly</em>, 9(1), 32–34.</p>
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
  <a class="footer-link" href="https://bsky.app/profile/maiibrahim.bsky.social">Bluesky</a>
  <a class="footer-link" href="https://scholar.google.ca/citations?user=e39G1iYAAAAJ">Google Scholar</a>
</div>

</div>
