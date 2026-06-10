---
layout: page
title: About Me
---

<style>

  .home-page *,
  .home-page *::before,
  .home-page *::after {
    box-sizing: border-box;
  }

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

  .home-page {
    background: var(--bg);
    color: var(--text);
    font-family: 'Inconsolata', monospace;
    font-weight: 300;
    width: 100vw;
    position: relative;
    left: 50%;
    margin-left: -50vw;
  }

  .home-inner {
    width: 100%;
    padding-left: 4rem;
    padding-right: 2rem;
  }

  @media (min-width: 48em) {
    .home-inner {
      padding-left: 13rem;
      padding-right: 2rem;
    }
  }

  @media (min-width: 64em) {
    .home-inner {
      padding-left: 13rem;
      padding-right: 1rem;
    }
  }

  .home-strip {
    width: 100%;
    height: clamp(260px, 45vh, 480px);
    display: flex;
    flex-direction: row;
    overflow: hidden;
  }

  @media (min-width: 48em) {
    .home-strip {
      padding-left: 12rem;
    }
  }

  .strip-panel {
    position: relative;
    flex: 1;
    overflow: hidden;
    background: var(--surface);
  }

  .strip-panel-media {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
  }

  .strip-panel-media img,
  .strip-panel-media video {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center top;
    display: block;
    margin: 0;
    border-radius: 0;
    filter: brightness(0.5) saturate(0.5);
    transition: filter 0.5s ease, transform 0.5s ease;
    transform: scale(1.03);
  }

  .strip-panel:hover .strip-panel-media img,
  .strip-panel:hover .strip-panel-media video {
    filter: brightness(0.75) saturate(0.8);
    transform: scale(1.0);
  }

  .strip-placeholder {
    width: 100%;
    height: 100%;
    background: repeating-linear-gradient(
      135deg,
      #161412,
      #161412 20px,
      #1b1915 20px,
      #1b1915 40px
    );
  }

  .strip-panel:nth-child(1) {
    clip-path: polygon(0% 0%, 108% 0%, 100% 100%, 0% 100%);
    margin-right: -4%;
    z-index: 1;
  }

  .strip-panel:nth-child(2) {
    clip-path: polygon(8% 0%, 108% 0%, 100% 100%, 0% 100%);
    margin-right: -4%;
    z-index: 2;
  }

  .strip-panel:nth-child(3) {
    clip-path: polygon(8% 0%, 100% 0%, 100% 100%, 0% 100%);
    z-index: 3;
  }

  .strip-panel:hover {
    z-index: 10;
  }

  @media (max-width: 47.99em) {
    .home-strip {
      padding-left: 0;
    }

    .strip-panel:nth-child(1),
    .strip-panel:nth-child(2),
    .strip-panel:nth-child(3) {
      clip-path: polygon(3% 0%, 100% 0%, 97% 100%, 0% 100%);
      margin-right: -2%;
    }

    .strip-panel:nth-child(3) {
      clip-path: polygon(3% 0%, 100% 0%, 100% 100%, 0% 100%);
      margin-right: 0;
    }
  }

  @media (max-width: 30em) {
    .home-strip {
      flex-direction: column;
      height: auto;
    }

    .strip-panel,
    .strip-panel:nth-child(1),
    .strip-panel:nth-child(2),
    .strip-panel:nth-child(3) {
      flex: none;
      height: 100px;
      clip-path: none !important;
      margin-right: 0 !important;
      border-bottom: 1px solid var(--border);
    }
  }

  .home-welcome {
    padding: 1.5rem 1rem;
  }

  .home-welcome-eyebrow {
    display: block;
    font-size: 0.65rem;
    letter-spacing: 0.28em;
    text-transform: uppercase;
    color: var(--muted);
    margin: 0 0 0.75rem;
  }

  .home-welcome-name {
    font-family: 'Playfair Display', serif !important;
    font-size: clamp(1.8rem, 3.5vw, 3rem) !important;
    font-weight: 700 !important;
    color: var(--white) !important;
    margin: 0 0 1.25rem !important;
    padding: 0 !important;
    line-height: 1.1;
  }

  .home-welcome-bio {
    max-width: 58ch;
    font-size: 0.9rem;
    line-height: 1.85;
    color: var(--text);
    margin: 0;
    padding: 0;
  }

  .home-divider {
    border: none;
    border-top: 1px solid var(--border);
    margin: 0 0 3.5rem;
  }

  .home-buttons {
  display: flex;
  gap: 1rem;
  margin-top: 1.75rem;
  flex-wrap: wrap;
  padding-left: 1rem;
  }

  .home-btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.6rem 1.4rem;
  font-family: 'Inconsolata', monospace;
  font-size: 0.68rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  text-decoration: none !important;
  transition: background 0.2s ease, color 0.2s ease, border-color 0.2s ease;
  border: 1px solid var(--accent);
  background: var(--accent);
  color: var(--bg) !important;
  }

  .home-btn:hover {
  background: var(--accent-lt);
  border-color: var(--accent-lt);
  color: var(--bg) !important;
  text-decoration: none !important;
  }

  .home-btn--ghost {
  background: transparent;
  color: var(--accent-lt) !important;
  }

  .home-btn--ghost:hover {
  background: var(--accent);
  color: var(--bg) !important;
  }

  .port-label {
    font-size: 0.7rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--muted);
    margin: 0 0 0.5rem;
    padding: 0;
  }

  .port-title {
    font-family: 'Playfair Display', serif !important;
    font-size: clamp(1.4rem, 2.5vw, 2rem) !important;
    font-weight: 400 !important;
    color: var(--white) !important;
    margin: 0 0 2.5rem !important;
    padding: 0 0 1.25rem;
    border-bottom: 1px solid var(--border);
  }

  .portfolio-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2px;
    width: 100%;
    align-items: start;
  }

  .port-card {
    background: var(--surface);
    border: 1px solid var(--border);
    display: flex;
    flex-direction: column;
    transition: border-color 0.3s ease;
  }

  .port-card.is-open {
    border-color: var(--accent);
  }

  .port-media {
    position: relative;
    width: 100%;
    aspect-ratio: 4 / 3;
    overflow: hidden;
    background: #1a1713;
  }

  .port-media img,
  .port-media video,
  .port-media iframe {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
    transition: transform 0.6s ease, filter 0.4s ease;
    filter: brightness(0.75) saturate(0.6);
    margin: 0;
    border-radius: 0;
  }

  .port-card.is-open .port-media img,
  .port-card.is-open .port-media video {
    filter: brightness(0.9) saturate(0.8);
  }

  .media-badge {
    position: absolute;
    top: 0.75rem;
    right: 0.75rem;
    font-size: 0.6rem;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    color: var(--accent-lt);
    background: rgba(14,13,12,0.75);
    border: 1px solid var(--accent);
    padding: 0.2rem 0.55rem;
    backdrop-filter: blur(4px);
  }

  .port-placeholder {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.65rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--muted);
    background: repeating-linear-gradient(
      135deg,
      #161412,
      #161412 20px,
      #1b1915 20px,
      #1b1915 40px
    );
  }

  .port-body {
    padding: 1.5rem;
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
    border-top: 1px solid var(--border);
  }

  .port-category {
    font-size: 0.62rem;
    letter-spacing: 0.22em;
    text-transform: uppercase;
    color: var(--accent);
    margin: 0;
    padding: 0;
  }

  .port-card-title {
    font-family: 'Playfair Display', serif !important;
    font-size: clamp(1rem, 1.4vw, 1.3rem) !important;
    font-weight: 700 !important;
    color: var(--white) !important;
    line-height: 1.25;
    margin: 0;
    padding: 0;
  }

  .port-desc {
    font-size: 0.82rem;
    line-height: 1.7;
    color: var(--text);
    margin: 0;
  }

  .port-toggle {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    margin-top: 0.25rem;
    padding: 0;
    background: none;
    border: none;
    cursor: pointer;
    font-family: 'Inconsolata', monospace;
    font-size: 0.68rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--accent-lt);
    transition: color 0.2s ease;
    width: fit-content;
  }

  .port-toggle:hover {
    color: var(--white);
  }

  .port-toggle-icon {
    display: inline-block;
    font-style: normal;
    transition: transform 0.3s ease;
    line-height: 1;
  }

  .port-card.is-open .port-toggle-icon {
    transform: rotate(180deg);
  }

  .port-drawer {
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.4s ease;
    background: var(--surface2);
    border-top: 0px solid var(--border);
  }

  .port-card.is-open .port-drawer {
    max-height: 600px;
    border-top-width: 1px;
  }

  .port-drawer-inner {
    padding: 1rem 1.5rem 1.25rem;
  }

  .port-drawer-label {
    font-size: 0.58rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--muted);
    margin: 0 0 0.75rem;
    padding: 0;
  }

  .port-drawer-links {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
  }

  .port-drawer-links li {
    border-bottom: 1px solid var(--border);
  }

  .port-drawer-links li:last-child {
    border-bottom: none;
  }

  .port-drawer-links a {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0.6rem 0;
    font-size: 0.78rem;
    color: var(--text) !important;
    text-decoration: none !important;
    transition: color 0.2s ease, padding-left 0.2s ease;
    line-height: 1.3;
  }

  .port-drawer-links a:hover {
    color: var(--white) !important;
    padding-left: 0.4rem;
    text-decoration: none !important;
  }

  .port-drawer-links a::after {
    content: '→';
    font-size: 0.7rem;
    color: var(--muted);
    flex-shrink: 0;
    margin-left: 0.5rem;
    transition: color 0.2s ease, transform 0.2s ease;
  }

  .port-drawer-links a:hover::after {
    color: var(--accent-lt);
    transform: translateX(3px);
  }

  /* Tablet: 2-col grid */
  @media (max-width: 47.99em) {
    .portfolio-grid {
      grid-template-columns: repeat(2, 1fr);
    }
  }

  /* Mid-desktop with sidebar: 2-col grid */
  @media (min-width: 48em) and (max-width: 63.99em) {
    .portfolio-grid {
      grid-template-columns: repeat(2, 1fr);
    }
  }

  /* Wide desktop: 3-col grid */
  @media (min-width: 64em) {
    .portfolio-grid {
      grid-template-columns: repeat(3, 1fr);
    }
  }

  /* Mobile: single column, tighter spacing */
  @media (max-width: 30em) {
    .home-welcome {
      padding: 2rem 0 2.5rem;
    }

    .portfolio-grid {
      grid-template-columns: 1fr;
      gap: 1px;
    }

    .port-media {
      aspect-ratio: 16 / 9;
    }

    .home-inner {
    width: 100%;
    height: clamp(260px, 60vh, 480px);
    display: flex;
    flex-direction: row;
    overflow: hidden;
    }
  }

  .home-grid-section {
    padding-bottom: 5rem;
  }

</style>

<div class="home-page">
  <div class="home-strip" aria-hidden="true">
    <div class="strip-panel">
      <div class="strip-panel-media">
        <img src="/assets/img/skink.jpg" alt="">
      </div>
    </div>
    <div class="strip-panel">
      <div class="strip-panel-media">
        <img src="/assets/img/MissingTheBoys.JPEG" alt="">
      </div>
    </div>
    <div class="strip-panel">
      <div class="strip-panel-media">
        <img src="/assets/img/mountainsandme.jpg" alt="">
      </div>
    </div>
  </div>
  <div class="home-inner">
    <div class="home-welcome">
      <p class="home-welcome-bio">
        Hey there! I'm a designer and writer. I've renovated and built escape rooms, created characters and storylines to keep players invested, and maintained networks that pass my creativity and passion to my teammates.</p>
        <br>
      <p class="home-welcome-bio">I'm currently looking for opportunities in games, where I continue to develop game jams and scripts.
      </p>
      <div class="home-buttons">
        <a class="home-btn" href="/projects">Projects</a>
        <a class="home-btn home-btn--ghost" href="/about">Fiction</a>
        <a class="home-btn home-btn--ghost" href="/about">Resume</a>
    </div>
  </div>
</div>

<script>
  document.querySelectorAll('.port-toggle').forEach(function(btn) {
    btn.addEventListener('click', function() {
      var card   = btn.closest('.port-card');
      var isOpen = card.classList.contains('is-open');

      // Close all first
      document.querySelectorAll('.port-card').forEach(function(c) {
        c.classList.remove('is-open');
        c.querySelector('.port-toggle').setAttribute('aria-expanded', 'false');
      });

      // Open this one if closed
      if (!isOpen) {
        card.classList.add('is-open');
        btn.setAttribute('aria-expanded', 'true');
      }
    });
  });
</script>
