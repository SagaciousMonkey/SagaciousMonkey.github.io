---
layout: page
title: Projects
permalink: /projects
---

<style>

.port-card-title {
  cursor: pointer;
  transition: color 0.2s ease;
}

.port-card-title:hover {
  color: var(--accent-lt) !important;
}

.port-synopsis {
  display: none;
  font-size: 0.82rem;
  line-height: 1.7;
  color: var(--text);
  margin: 0;
}

.port-card.is-flipped .port-media {
  display: none;
}

.port-card.is-flipped .port-synopsis {
  display: block;
}

.port-card.is-flipped .port-desc {
  display: none;
}

.port-hero {
  width: 100%;
  position: relative;
  height: clamp(160px, 15vw, 20vw);
  overflow: hidden;
  background: var(--surface);
}

.port-hero-img {
  width: 100vw;
  height: clamp(160px, 15vw, 20vw);
  background-image: url('/assets/img/trees.png');
  background-repeat: repeat-x;
  background-size: 100%;
  background-position: left center;
  filter: brightness(1.0);
  animation: hero-scroll 80s linear infinite;
  image-rendering: pixelated;
  z-index: 2;
}

@keyframes hero-scroll {
  0%   { background-position: 0px center; }
  100% { background-position: -2552px center; }
}

.port-hero::after {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(
    to bottom,
    rgba(12, 12, 14, 0.25) 20%,
    transparent 50%,
    rgba(12, 12, 14, 0.6) 100%,
    var(--bg) 100%
  );
  pointer-events: none;
}

.port-hero-text {
  position: absolute;
  top: 2
  left: 2rem;
  right: 2rem;
  z-index: 2;
}

@media (min-width: 48em) {
  .port-hero-text {
    left: 13rem;
    right: 1rem;
  }
}

@media (min-width: 64em) {
  .port-hero-text {
    left: 14rem;
    right: 1rem;
  }
}

.port-hero-eyebrow {
  display: block;
  font-size: 0.62rem;
  letter-spacing: 0.28em;
  text-transform: uppercase;
  color: var(--accent-lt);
  margin-bottom: 0.5rem;
}

.port-hero-title {
  font-family: 'Playfair Display', serif !important;
  font-size: clamp(1.6rem, 3.5vw, 2.8rem) !important;
  font-weight: 700 !important;
  color: var(--white) !important;
  margin: 0 !important;
  padding: 0 !important;
  line-height: 1.1;
  text-shadow: 0 2px 16px rgba(0,0,0,0.5);
}

@media (max-width: 30em) {
  .port-hero {
    height: 160px;
    width; 100%;
  }
  .port-hero-text {
    top: 1.25rem;
    left: 1rem;
    right: 1rem;
  }
}

.port-link {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  margin-top: 0.25rem;
  font-size: 0.68rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--accent-lt) !important;
  text-decoration: none !important;
  transition: color 0.2s ease;
  width: fit-content;
}

.port-link::after {
  content: '→';
  display: inline-block;
  transition: transform 0.25s ease;
}

.port-link:hover {
  color: var(--white) !important;
}

.port-link:hover::after {
  transform: translateX(4px);
}

  .portfolio-section *,
  .portfolio-section *::before,
  .portfolio-section *::after {
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

.portfolio-section {
  background: var(--bg);
  color: var(--text);
  font-family: 'Inconsolata', monospace;
  font-weight: 300;
  padding: 1rem 1rem;
}

.portfolio-inner {
  width: 100%;
}

@media (min-width: 48em) {
  .portfolio-inner {
  }
}

@media (min-width: 64em) {
  .portfolio-inner {
  }
}
  .port-label {
    font-size: 0.7rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var;
    margin: 0 0 0.5rem;
    padding: 0;
  }

  .port-title {
    font-size: clamp(1.8rem, 3vw, 2.6rem) !important;
    font-weight: 400 !important;
    color: var(--white) !important;
    margin: 0 0 3.5rem !important;
    padding: 0 0 1.5rem;
    border-bottom: 1px solid var(--border);
  }

  .portfolio-grid {
    display: grid;
    grid-template-columns: auto auto auto;
    gap: 2px;
    width: 100%;
  }

  .port-card {
    background: var(--surface);
    border: 1px solid var(--border);
    display: flex;
    flex-direction: column;
    overflow: hidden;
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
    flex: 1;
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
    font-size: clamp(1rem, 1.4vw, 1.3rem) !important;
    font-weight: 600 !important;
    color: var(--white) !important;
    line-height: 1.25;
    margin: 0;
    padding: 0;
  }

  .port-desc {
    font-size: 0.82rem;
    line-height: 1.7;
    color: var(--text);
    flex: 1;
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

  /* Drawer heading */
  .port-drawer-label {
    font-size: 0.58rem;
    letter-spacing: 0.25em;
    text-transform: uppercase;
    color: var(--muted);
    margin: 0 0 0.75rem;
    padding: 0;
  }

  /* Sub-link list */
  .port-drawer-links {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    gap: 0;
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

/* Wide desktop — 4 cols */
@media (min-width: 72em) {
  .portfolio-grid {
    grid-template-columns: repeat(4, 1fr);
  }
}

/* Mid desktop with sidebar — 3 cols */
@media (min-width: 48em) and (max-width: 71.99em) {
  .portfolio-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* Tablet — 2 cols */
@media (max-width: 47.99em) {
  .portfolio-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

/* Mobile — 1 col */
@media (max-width: 30em) {
  .portfolio-grid {
    grid-template-columns: 1fr;
  }
}

</style>

<div class="port-hero">
  <div class="port-hero-img"></div>
</div>
<div class="portfolio-section">
  <div class="portfolio-inner">
    <div class="portfolio-grid">
      <article class="port-card" id="card-quest">
        <div class="port-media">
            <img src="/assets/img/ETScroll.png"></video>
          <span class="media-badge">World Design</span>
        </div>
        <div class="port-body">
          <span class="port-category">Authenticity and Immersion</span>
          <h2 class="port-card-title"><a href="/projects/etr">Egyptian Tomb Redux</a></h2>
          <p class="port-desc">
            <i>Escape Room.</i> A re-imagining of an industry staple, focusing on game flow and environment design. Players follow the paths of multiple explorers as they journey through a tomb from the Old Kingdom era.
          </p>
        </div>
      </article>
      <article class="port-card" id="card-narrative">
        <div class="port-media">
          <img src="/assets/img/OBVirus.JPEG">
          <span class="media-badge">Narrative Design</span>
        </div>
        <div class="port-body">
          <span class="port-category">The Room That Spoke Back</span>
          <h2 class="port-card-title"><a href="/projects/ob95">Outbreak '95</a></h2>
          <p class="port-desc">
            <i>Escape Room.</i> A survival horror experience with extensive scripted props, such as an original Gameboy and a chatbot PC. This room pushed atmosphere over jumpscare horror.
          </p>
        </div>
      </article>
      <article class="port-card" id="card-third">
        <div class="port-media">
          <img src="/assets/img/CCC.png">
          <span class="media-badge">Collaboration</span>
        </div>
        <div class="port-body">
          <span class="port-category">New Foundations</span>
          <h2 class="port-card-title">Game Jams</h2>
          <p class="port-desc">
            <i>Video Games; Twine, Unity and Godot.</i> Works published on Itch.io and personal projects. Chicken Kaiju, Biscuit-based Dungeon Crawlers, and an adventure through Hell.
          </p>
        </div>
      </article>
      <article class="port-card" id="card-third">
        <div class="port-media">
          <div class="port-placeholder">Image / Video</div>
          <span class="media-badge">Quest Design</span>
        </div>
        <div class="port-body">
          <span class="port-category">Your Memories, Their Arsenal</span>
          <h2 class="port-card-title">Under Alma</h2>
          <p class="port-desc">
            <i>Solo TTRPG.</i> An adventure in the belly of the world's soul. Become a muse to a weary soul, giving them memories that impart knowledge and experience.
          </p>
          </div>
      </article>

    </div>

  </div>
</div>

<script>
  document.querySelectorAll('.port-toggle').forEach(function(btn) {
    btn.addEventListener('click', function() {
      var card   = btn.closest('.port-card');
      var isOpen = card.classList.contains('is-open');

      // Close all cards that have toggle
      document.querySelectorAll('.port-card').forEach(function(c) {
        c.classList.remove('is-open');
        var toggle = c.querySelector('.port-toggle');
        if (toggle) toggle.setAttribute('aria-expanded', 'false');
      });

      // Open this one if closed
      if (!isOpen) {
        card.classList.add('is-open');
        btn.setAttribute('aria-expanded', 'true');
      }
    });
  });
</script>
