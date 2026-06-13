---
layout: page
title: About Me
permalink: /aboutme
---

<style>

  :root {
    --bg:        #0e0d0c;
    --surface:   #161412;
    --surface2: #1c1916;
    --border:    #2a2520;
    --text:      #c9b99a;
    --muted:     #47475e;
    --accent:    #299fce;
    --accent-lt: #4b8faa;
    --white:     #f0e8db;
  }

  .portfolio-grid {
    grid-template-columns: repeat(3, 1fr);
    display: grid;
    width: 100%;
    justify-content: space-evenly;
    align-items: center;
    padding: 10px;
    overflow: hidden;
  }

  .home-photo-cell img {
    display: block;
    width: 100%;
    height: auto;
    max-width: 30vw;
    object-fit: cover;
    object-position: center top;
    transition: transform 0.4s ease;
  }

.home-welcome {
  background: var(--bg);
  color: var(--text);
  font-family: 'Inconsolata', monospace;
  font-weight: 300;
  padding: 1rem 1rem;
}

  .home-buttons {
    display: flex;
    gap: 0.75rem;
    flex-wrap: wrap;
    margin-top: 1.25rem;
  }

  .home-btn {
    display: inline-flex;
    align-items: center;
    padding: 0.6rem 1.4rem;
    font-family: 'Inconsolata', monospace;
    font-size: 0.68rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    text-decoration: none !important;
    border: 1px solid var(--accent);
    background: var(--accent);
    color: var(--bg) !important;
    transition: background 0.2s ease, border-color 0.2s ease;
  }

  .home-btn:hover {
    background: var(--accent-lt);
    border-color: var(--accent-lt);
  }

  .home-btn--ghost {
    background: transparent;
    color: var(--accent-lt) !important;
  }

  .home-btn--ghost:hover {
    background: var(--accent);
    color: var(--bg) !important;
  }


</style>

<div class="portfolio-grid">
  <div class="home-photo-cell">
    <img src="/assets/img/mountainsandme.jpg" alt="">
    </div>
  <div class="home-photo-cell">
    <img src="/assets/img/WithPresh.JPEG" alt="">
   </div>
  <div class="home-photo-cell">
    <img src="/assets/img/vermont.png" alt="">
    </div>
</div>

<div class="home-welcome">
  <span class="home-welcome-eyebrow">Designer &amp; Writer</span>
  <p class="home-welcome-bio">Hey there! I'm a designer and writer. I've renovated and built escape rooms, created characters and storylines to keep players invested, and maintained networks that pass my creativity and passion to my teammates.</p>
  <p class="home-welcome-bio">I'm currently looking for opportunities in games, where I continue to develop game jams and scripts.</p>
  <div class="home-buttons">
    <a class="home-btn" href="/projects">Projects</a>
    <a class="home-btn home-btn--ghost" href="/fiction">Fiction</a>
    <a class="home-btn home-btn--ghost" href="/resume">Resume</a>
  </div>
</div>
