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
  min-height: calc(100vh - var(--nav-h));
  width: 100vw;
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
  padding: 4rem max(2.5rem, 6vw);
  background: #fdf6ee;
  min-height: 100vh;
  width: 100vw;
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
  font-fam
