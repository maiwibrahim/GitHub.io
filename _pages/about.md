---
layout: about
title: ""
permalink: /
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
  margin: -3rem -2rem 0 -2rem;
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
.pub-type-block:last-child
