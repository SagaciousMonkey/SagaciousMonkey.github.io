---
layout: page
title: Home
---

<!--
  FONTS: Ensure this is in your _includes/head.html:
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Inconsolata:wght@300;400&display=swap" rel="stylesheet" />
-->
<style>

  /* ══════════════════════════════════════════
     SCOPED RESET
  ══════════════════════════════════════════ */
  .home-page *,
  .home-page *::before,
  .home-page *::after {
    box-sizing: border-box;
  }

  :root {
    --bg:        #0e0d0c;
    --surface:   #161412;
    --surface2:  #1c1916;
    --border:    #2a2520;
    --text:      #c9b99a;
    --muted:     #5e5347;
    --accent:    #b5763a;
    --accent-lt: #d4935a;
    --white:     #f0e8db;
  }

  /* ══════════════════════════════════════════
     OUTER WRAPPER
     Full-bleed from viewport edge to edge,
     sidebar offset handled per-section below.
  ══════════════════════════════════════════ */
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

  /* ══════════════════════════════════════════
     SHARED INNER CONTAINER
     Keeps content clear of Hyde's fixed sidebar.
     Re-used by welcome and grid sections.
  ══════════════════════════════════════════ */
  .home-inner {
    width: 100%;
    padding-left: 2rem;
    padding-right: 2rem;
  }

  @media (min-width: 48em) {
    .home-inner {
      padding-left: 20rem;
      padding-right: 2rem;
    }
  }

  @media (min-width: 64em) {
    .home-inner {
      padding-left: 22rem;
      padding-right: 4rem;
    }
  }


  /* ══════════════════════════════════════════
     1. DECORATIVE DIAGONAL STRIP
  ══════════════════════════════════════════ */

  .home-strip {
    width: 100%;
    height: clamp(160px, 26vh, 260px);
    display: flex;
    flex-direction: row;
    overflow: hidden;
    /* On desktop, indent past the sidebar */
    padding-left: 0;
  }

  @media (min-width: 48em) {
    .home-strip {
      padding-left: 18rem; /* sidebar width — strip starts flush with content */
    }
  }

  /* ── Individual panel ── */
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

  /* Placeholder tile for before real media is added */
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

  /*
   * ── Diagonal cuts via clip-path ──
   * Panel 1: right edge diagonal
   * Panel 2: parallelogram (both edges)
   * Panel 3: left edge diagonal
   * Negative margin-right creates overlap so cuts appear seamless.
   */
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

  /* Simplify diagonal on narrow screens */
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

  /* Stack on mobile — diagonal cuts don't work well at very small widths */
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


  /* ══════════════════════════════════════════
     2. WELCOME TEXT
  ══════════════════════════════════════════ */

  .home-welcome {
    padding: 3rem 0 3.5rem;
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

  /* Thin rule separating welcome from grid */
  .home-divider {
    border: none;
    border-top: 1px solid var(--border);
    margin: 0 0 3.5rem;
  }


  /* ══════════════════════════════════════════
     3. SELECTED WORK SECTION HEADER
  ══════════════════════════════════════════ */

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


  /* ══════════════════════════════════════════
     4. CARD GRID
  ══════════════════════════════════════════ */

  .portfolio-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2px;
    width: 100%;
    align-items: start;
  }

  /* ── Card ── */
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

  /* ── Media ── */
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

  /* ── Card body ── */
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

  /* ── Toggle button ── */
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

  /* ── Accordion drawer ── */
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


  /* ══════════════════════════════════════════
     RESPONSIVE
  ══════════════════════════════════════════ */

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
      padding-left: 1rem;
      padding-right: 1rem;
    }
  }

  /* Bottom padding on the whole page */
  .home-grid-section {
    padding-bottom: 5rem;
  }

</style>

<div class="home-page">

  <!-- ════════════════════════════════════════
       1. DECORATIVE DIAGONAL STRIP
       No text, no links — purely atmospheric.
       Replace .strip-placeholder divs with your
       images or videos when ready.
  ════════════════════════════════════════ -->
  <div class="home-strip" aria-hidden="true">

    <div class="strip-panel">
      <div class="strip-panel-media">
        <div class="strip-placeholder"></div>
        <!-- <img src="/assets/img/strip-01.jpg" alt="" /> -->
        <!-- <video src="/assets/video/strip-01.mp4" autoplay muted loop playsinline></video> -->
      </div>
    </div>

    <div class="strip-panel">
      <div class="strip-panel-media">
        <div class="strip-placeholder"></div>
        <!-- <img src="/assets/img/strip-02.jpg" alt="" /> -->
      </div>
    </div>

    <div class="strip-panel">
      <div class="strip-panel-media">
        <div class="strip-placeholder"></div>
        <!-- <img src="/assets/img/strip-03.jpg" alt="" /> -->
      </div>
    </div>

  </div><!-- /.home-strip -->

  <!-- ════════════════════════════════════════
       2. WELCOME TEXT
  ════════════════════════════════════════ -->
  <div class="home-inner">
    <div class="home-welcome">
      <p class="home-welcome-bio">
        I'm a narrative designer and writer.
        I've worked on escape rooms and video games, and I've written short stories and comic scripts.
      </p>
    </div>
    <hr class="home-divider" />
  </div>

  <!-- ════════════════════════════════════════
       3. SELECTED WORK GRID
  ════════════════════════════════════════ -->
  <div class="home-inner home-grid-section">
    <div class="portfolio-grid">

      <!-- Card 1: Quest Design -->
      <article class="port-card" id="card-quest">
        <div class="port-media">
          <div class="port-placeholder">Image / Video</div>
          <!-- <img src="/assets/img/quest-design.jpg" alt="Quest Design" /> -->
          <span class="media-badge">Image</span>
        </div>
        <div class="port-body">
          <span class="port-category">Game Writing</span>
          <h3 class="port-card-title">Quest Design</h3>
          <p class="port-desc">
            Crafting player-driven narratives through branching objectives,
            meaningful choices, and world-coherent storytelling.
          </p>
          <button class="port-toggle" aria-expanded="false" aria-controls="drawer-quest">
            View Projects
            <i class="port-toggle-icon" aria-hidden="true">&#8964;</i>
          </button>
        </div>
        <div class="port-drawer" id="drawer-quest" role="region">
          <div class="port-drawer-inner">
            <p class="port-drawer-label">Projects</p>
            <ul class="port-drawer-links">
              <li><a href="/quest-design/main-quest">Main Quest — Project Title</a></li>
              <li><a href="/quest-design/side-quest-system">Side Quest System</a></li>
              <li><a href="/quest-design/faction-quests">Faction Quest Design</a></li>
            </ul>
          </div>
        </div>
      </article>

      <!-- Card 2: Narrative Design -->
      <article class="port-card" id="card-narrative">
        <div class="port-media">
          <div class="port-placeholder">Image / Video</div>
          <!-- <video src="/assets/video/narrative.mp4" autoplay muted loop playsinline></video> -->
          <span class="media-badge">Video</span>
        </div>
        <div class="port-body">
          <span class="port-category">Game Writing</span>
          <h3 class="port-card-title">Narrative Design</h3>
          <p class="port-desc">
            Building the architecture of story — lore systems, character voice,
            and the invisible scaffolding players feel but never see.
          </p>
          <button class="port-toggle" aria-expanded="false" aria-controls="drawer-narrative">
            View Projects
            <i class="port-toggle-icon" aria-hidden="true">&#8964;</i>
          </button>
        </div>
        <div class="port-drawer" id="drawer-narrative" role="region">
          <div class="port-drawer-inner">
            <p class="port-drawer-label">Projects</p>
            <ul class="port-drawer-links">
              <li><a href="/narrative-design/lore-system">World Lore System</a></li>
              <li><a href="/narrative-design/character-voice">Character Voice Guide</a></li>
              <li><a href="/narrative-design/environmental-storytelling">Environmental Storytelling</a></li>
            </ul>
          </div>
        </div>
      </article>

      <!-- Card 3: Third Discipline -->
      <article class="port-card" id="card-third">
        <div class="port-media">
          <div class="port-placeholder">Image / Video</div>
          <!-- <img src="/assets/img/third.jpg" alt="Third Discipline" /> -->
          <span class="media-badge">Image</span>
        </div>
        <div class="port-body">
          <span class="port-category">Category</span>
          <h3 class="port-card-title">Third Discipline</h3>
          <p class="port-desc">
            A short description of this area of your work and what
            makes it worth exploring further.
          </p>
          <button class="port-toggle" aria-expanded="false" aria-controls="drawer-third">
            View Projects
            <i class="port-toggle-icon" aria-hidden="true">&#8964;</i>
          </button>
        </div>
        <div class="port-drawer" id="drawer-third" role="region">
          <div class="port-drawer-inner">
            <p class="port-drawer-label">Projects</p>
            <ul class="port-drawer-links">
              <li><a href="/third/project-one">Project One</a></li>
              <li><a href="/third/project-two">Project Two</a></li>
              <li><a href="/third/project-three">Project Three</a></li>
            </ul>
          </div>
        </div>
      </article>

    </div><!-- /.portfolio-grid -->

  </div><!-- /.home-inner -->

</div><!-- /.home-page -->

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

      // Open this one if it was closed
      if (!isOpen) {
        card.classList.add('is-open');
        btn.setAttribute('aria-expanded', 'true');
      }
    });
  });
</script>
