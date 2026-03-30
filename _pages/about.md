---
layout: about
title: About
permalink: /
nav: true
nav_order: 1
news: false
selected_papers: false
social: false
toc:
  sidebar: left
---

<style>
@import url('https://fonts.googleapis.com/css2?family=IM+Fell+English:ital@0;1&family=Lora:ital,wght@0,400;0,500;1,400&display=swap');

.page *,
.page *::before,
.page *::after { box-sizing: border-box; margin: 0; padding: 0; }

.page {
  font-family: 'Lora', Georgia, serif;
  margin: 0 -2rem 0 -2rem;
}

:root { --nav-h: 57px; }

/* HERO */
.hero {
  background: #6b4472;
  padding: 4rem 2.5rem 3.5rem;
  min-height: calc(100vh - var(--nav-h));
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.hero-name {
  font-family: 'IM Fell English', Georgia, serif;
  font-size: clamp(44px, 9.5vw, 70px);
  font-weight: 400;
  font-style: italic;
  line-height: 1.0;
  letter-spacing: -0.02em;
  color: #f7edfb;
  margin-bottom: 1.1rem;
  white-space: nowrap;
}
.hero-desc {
  font-size: 14px;
  color: #d9b8e0;
  line-height: 1.7;
  font-style: italic;
}

/* ABOUT */
.about-section {
  padding: 3rem 2.5rem;
  background: #fdf6ee;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.section-label {
  font-size: 10px;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: #6b4472;
  margin-bottom: 1.25rem;
  font-style: normal;
}
.about-grid {
  display: grid;
  grid-template-columns: 112px 1fr;
  gap: 1.75rem;
  align-items: start;
}
.about-img {
  width: 112px;
  height: 142px;
  object-fit: cover;
  object-position: top;
  border-radius: 2px;
}
.about-text {
  font-size: 13.5px;
  line-height: 1.9;
  color: #5a3e2b;
}

/* PUBLICATIONS */
.pubs-section {
  padding: 3rem 2.5rem;
  background: #fff;
  min-height: 100vh;
}
.pubs-section .section-label {
  color: #3a6b52;
  margin-bottom: 2rem;
}
.pub-type-block {
  margin-bottom: 2.25rem;
}
.pub-type-block:last-child { margin-bottom: 0; }
.pub-type-label {
  font-size: 11.5px;
  font-weight: 500;
  font-style: normal;
  letter-spacing: 0.01em;
  margin-bottom: 0.9rem;
  padding: 4px 10px;
  display: inline-block;
  border-radius: 3px;
}
.type-chapters  .pub-type-label { background: #fde8c8; color: #8a4e10; }
.type-articles  .pub-type-label { background: #d4eadb; color: #2c5c3c; }
.type-reviews   .pub-type-label { background: #dfe0f5; color: #3b3c80; }
.type-interview .pub-type-label { background: #ecd8f0; color: #5a2870; }
.pub-entry {
  font-size: 13px;
  line-height: 1.8;
  color: #3a3228;
  margin-bottom: 0.85rem;
  font-style: normal;
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
  padding: 2.5rem 2.5rem;
  background: #fdf6ee;
  min-height: 100vh;
  display: flex;
  align-items: center;
  gap: 1rem;
  flex-wrap: wrap;
}
.cv-download {
  font-size: 11px;
  letter-spacing: 0.13em;
  text-transform: uppercase;
  color: #3d1f4a;
  background: #c9a0d6;
  text-decoration: none;
  padding: 7px 16px;
  border-radius: 2px;
  font-style: normal;
}
.cv-download:hover { background: #b080c4; color: #fff; }

/* FOOTER */
.footer-section {
  padding: 2.25rem 2.5rem;
  background: #3d1f4a;
  display: flex;
  align-items: center;
  gap: 1.75rem;
  flex-wrap: wrap;
}
.footer-link {
  font-size: 13px;
  color: #c9a0d6;
  text-decoration: none;
  font-style: italic;
}
.footer-link:hover { color: #f0ddf5; }
.footer-sep { color: #6b3d7a; font-size: 12px; }
</style>

<div class="page">

  <!-- HERO -->
  <div class="hero" id="about">
    <h1 class="hero-name">Mai W. Ibrahim</h1>
    <p class="hero-desc">is a media theorist &amp; researcher of digital cultures</p>
  </div>

  <!-- ABOUT -->
  <div class="about-section">
    <p class="section-label">About</p>
    <div class="about-grid">
      <img class="about-img" src="/assets/img/prof_pic.jpg" alt="Mai W. Ibrahim" />
      <p class="about-text">My work sits at the intersection of digital media, media theory, and the philosophy and politics of technology. I investigate how digital media do not simply represent reality but actively constitute it — shaping what exists, what can be known, and whose existence becomes legible. I am currently a sessional instructor at McMaster University in Hamilton, Canada.</p>
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
    <a class="footer-link" href="mailto:mai.w.ibrahim@gmail.com">Email</a>
    <span class="footer-sep">·</span>
    <a class="footer-link" href="https://bsky.app/profile/maiibrahim.bsky.social">Bluesky</a>
    <span class="footer-sep">·</span>
    <a class="footer-link" href="https://scholar.google.ca/citations?user=e39G1iYAAAAJ">Google Scholar</a>
  </div>

</div>
