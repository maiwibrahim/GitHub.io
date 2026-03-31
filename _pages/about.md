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
@import url('https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=Lora:ital,wght@0,400;0,500;1,400&display=swap');

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
  width: 100vw;
  position: relative;
  left: 50%;
  margin-left: -50vw;
  overflow-x: hidden;
  font-family: 'Lora', Georgia, serif;
}

.navbar, nav.navbar { display: none !important; }
.post { padding: 0 !important; margin: 0 !important; }
article { padding: 0 !important; margin: 0 !important; }
.post-header { display: none !important; }
.p-name, .sidebar-header, .profile-name { display: none !important; }

.hero {
  background: #6b4472;
  min-height: 100vh;
  width: 100vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 4rem 2rem;
}

.hero-name {
  font-family: 'DM Serif Display', Georgia, serif;
  font-size: clamp(72px, 14vw, 130px);
  font-weight: 400;
  line-height: 1.0;
  letter-spacing: 0;
  margin-bottom: 1.1rem;
  transform: scaleX(1.15);
  display: block;
}

.hero-desc {
  font-size: 22px;
  color: #ffffff;
  line-height: 1.7;
  font-style: italic;
}

.site-nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 99999;
  background: #6b4472;
  display: flex;
  gap: 2.5rem;
  align-items: center;
  height: 52px;
  padding: 0 3rem;
}

.site-nav a {
  font-family: 'Lora', serif;
  font-size: 13px;
  color: #f7edfb;
  text-decoration: none;
  letter-spacing: 0.15em;
  text-transform: uppercase;
}

.about-section {
  background: #fdf6ee;
  min-height: 100vh;
  width: 100vw;
  display: flex;
  flex-direction: column;
  justify-content: center;
  p
