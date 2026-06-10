---
layout: nocss
category: "Egyptian Tomb Redux" # Change per page
permalink: /projects/etr
---

<style>

  .deepdive *,
  .deepdive *::before,
  .deepdive *::after {
    box-sizing: border-box;
  }

  :root {
    --bg:        #0e0d0c;
    --surface:   #161412;
    --border:    #2a2520;
    --text:      #c9b99a;
    --muted:     #5e5347;
    --accent:    #b5763a;
    --accent-lt: #d4935a;
    --white:     #f0e8db;
    --navy:      #182430;
  }

  .shadow-text {
    text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.7);
  }

  .deepdive {
    background: var(--bg);
    color: var(--text);
    font-family: 'Inconsolata', monospace;
    font-weight: 300;

    width: 98vw;
    position: relative;
    left: 50%;
    margin-left: -50vw;
  }

  .deepdive-inner {
    width: 100%;
    padding: 0 2rem 6rem;
  }

  @media (min-width: 48em) {
    .deepdive-inner {
      padding-left: 13rem;
      padding-right: 1rem;
    }
  }

  @media (min-width: 64em) {
    .deepdive-inner {
      padding-left: 14rem;
      padding-right: 1rem;
    }
  }

  .dd-hero {
    position: relative;
    width: 100%;
    /*Changed third height variable to shorten length of hero at top of page */
    height: clamp(280px, 50vh, 300px);
    overflow: hidden;
    margin-bottom: 0;
  }

.dd-hero-strip {
  display: flex;
  flex-direction: row;
  width: 100%;
  height: 100%;
}

.dd-hero-panel {
  flex: 1;
  height: 100%;
  background-size: cover;
  background-position: center top;
  filter: brightness(0.55) saturate(0.7);
  border-right: 1px solid var(--border);
}

.dd-hero-panel:last-child {
  border-right: none;
}

  .dd-hero::after {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(
    to bottom,
    rgba(0, 0, 0, 0.25) 40%,
    transparent 50%,
    rgba(0, 0, 0, 0.6) 80%,
    var(--bg) 100%
    );
    pointer-events: none;
  }

  .dd-hero-text {
    position: absolute;
    bottom: 5rem;
    left: 2rem;
    right: 2rem;
    z-index: 2;
    text-shadow: 2px 2px 5px black;
  }

  @media (min-width: 48em) {
    .dd-hero-text {
      left: 13rem;
      right: 1rem;
    }
  }

  @media (min-width: 64em) {
    .dd-hero-text {
      left: 14rem;
      right: 1rem;
    }
  }

  .dd-hero-category {
    display: block;
    font-size: 0.65rem;
    letter-spacing: 0.28em;
    text-transform: uppercase;
    color: var(--accent-lt);
    margin-bottom: 0.6rem;
  }

  .dd-hero-title {
    font-family: 'Playfair Display', serif !important;
    font-size: clamp(2rem, 5vw, 3.8rem) !important;
    font-weight: 500 !important;
    color: var(--white) !important;
    line-height: 1.1 !important;
    margin: 0 !important;
    padding: 0 !important;
    text-shadow: 0 2px 20px rgba(0,0,0,0.6);
  }

  .dd-lede {
    max-width: 68ch;
    margin: 3.5rem 0 4rem;
  }

  .dd-lede p {
    font-size: 1rem;
    line-height: 1.8;
    color: var(--text);
    margin: 0 0 1rem;
  }

  .dd-lede p:last-child {
    margin-bottom: 0;
  }

  /* Thin rule separating lede from body sections */
  .dd-divider {
    border: none;
    border-top: 1px solid var(--border);
    margin: 0 0 0rem;
  }

  .dd-media-block {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 3rem;
    align-items: center;
    margin-bottom: 5rem;
  }

  /* Default: media left, text right */
  .dd-media-block .dd-media-block-media { order: 1; }
  .dd-media-block .dd-media-block-text  { order: 2; }
  .dd-media-block.flip .dd-media-block-media { order: 2; }
  .dd-media-block.flip .dd-media-block-text  { order: 1; }

  .dd-media-block-media {
    position: relative;
    overflow: hidden;
    background: var(--surface);
    border: 1px solid var(--border);
    justify-items: center;
  }

  .dd-media-block-media img,
  .dd-media-block-media video,
  .dd-media-block-media iframe {
    width: 100%;
    display: block;
    margin: 0;
    border-radius: 0;
    filter: brightness(0.85) saturate(0.75);
    transition: filter 0.4s ease, transform 0.5s ease;
  }

  .dd-media-block-media:hover img,
  .dd-media-block-media:hover video {
    filter: brightness(1) saturate(1);
    transform: scale(1.02);
  }

  .dd-caption {
    display: block;
    font-size: 0.65rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--accent);
    padding: 0.65rem 0.85rem;
    border-top: 1px solid var(--border);
    background: var(--surface);
  }

  .dd-media-block-text h2 {
    font-family: 'Playfair Display', serif !important;
    font-size: clamp(1.2rem, 2vw, 1.6rem) !important;
    font-weight: 700 !important;
    color: var(--white) !important;
    margin: 0 0 1rem !important;
    padding: 0 !important;
    line-height: 1.2;
  }

  .dd-media-block-text h3 {
    font-family: 'Playfair Display', serif !important;
    font-size: clamp(1rem, .8vw, 1.5rem) !important;
    font-weight: 500 !important;
    color: var(--accent-lt); !important;
  }

  .dd-media-block-text h4 {
    font-family: 'Playfair Display', serif !important;
    font-size: clamp(1rem, .8vw, 1.5rem) !important;
    font-weight: 300 !important;
    color: var(--white); !important;
  }

  .dd-media-block-text p {
    text-indent: 50px;
    font-size: 0.88rem;
    line-height: 1.85;
    color: var(--text);
    margin: 0 0 0.85rem;
  }

  .dd-media-block-text p:last-child {
    margin-bottom: 0;
  }

  @media (max-width: 47.99em) {
    .dd-media-block,
    .dd-media-block.flip {
      grid-template-columns: 1fr;
      gap: 1.5rem;
    }

    .dd-media-block .dd-media-block-media,
    .dd-media-block.flip .dd-media-block-media { order: 1; }

    .dd-media-block .dd-media-block-text,
    .dd-media-block.flip .dd-media-block-text  { order: 2; }
  }

  /* ════════════════════════════════════════
     PULL QUOTE
  ════════════════════════════════════════ */

  .dd-pullquote {
    position: relative;
    margin: 2rem 0 5rem;
    padding: 2.5rem 2rem 2.5rem 3rem;
    border-left: 3px solid var(--accent);
    background: var(--surface);
  }

  .dd-pullquote::before {
    content: '\201C';
    position: absolute;
    top: -0.5rem;
    left: 1rem;
    font-family: 'Playfair Display', serif;
    font-size: 5rem;
    color: var(--accent);
    opacity: 0.3;
    line-height: 1;
    pointer-events: none;
  }

  .dd-pullquote blockquote {
    margin: 0;
    padding: 0;
    border: none;
    color: var(--white);
  }

  .dd-pullquote blockquote p {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.1rem, 2vw, 1.5rem);
    font-style: italic;
    line-height: 1.5;
    margin: 0 0 1rem;
    color: var(--white);
  }

  .dd-pullquote cite {
    font-size: 0.65rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--accent-lt);
    font-style: normal;
  }

  .dd-credits {
    margin-top: 6rem;
    padding-top: 2rem;
    border-top: 1px solid var(--border);
  }

  .dd-credits-title {
    font-size: 0.65rem;
    letter-spacing: 0.28em;
    text-transform: uppercase;
    color: var(--muted);
    margin: 0 0 1.5rem;
  }

  .dd-credits-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    gap: 1px;
    background: var(--border);
    border: 1px solid var(--border);
  }

  .dd-credit-item {
    background: var(--surface);
    padding: 1rem 1.25rem;
  }

  .dd-credit-label {
    display: block;
    font-size: 0.6rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 0.35rem;
  }

  .dd-credit-value {
    display: block;
    font-size: 0.82rem;
    color: var(--white);
    line-height: 1.4;
  }

  .dd-back {
    display: inline-flex;
    align-items: center;
    gap: 0.5rem;
    margin-top: 4rem;
    font-size: 0.65rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--accent) !important;
    text-decoration: none !important;
    transition: color 0.2s ease;
    text-shadow: 2px 2px 5px black;
  }

  .dd-back::before {
    content: '←';
    display: inline-block;
    transition: transform 0.25s ease;
  }

  .dd-back:hover {
    color: var(--accent-lt) !important;
    text-decoration: none !important;
  }

  .dd-back:hover::before {
    transform: translateX(-4px);
  }

  .dd-placeholder {
    width: 100%;
    aspect-ratio: 16 / 9;
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

</style>

<div class="deepdive">
<div class="dd-hero">
  <div class="dd-hero-strip">
    <div class="dd-hero-panel" style="background-image: url('/assets/img/ETPanel1.png')"></div>
    <div class="dd-hero-panel" style="background-image: url('/assets/img/ETPanel2.JPEG')"></div>
    <div class="dd-hero-panel" style="background-image: url('/assets/img/gobleki.JPEG')"></div>
    <div class="dd-hero-panel" style="background-image: url('/assets/img/ETSun.JPEG')"></div>
    <div class="dd-hero-panel" style="background-image: url('/assets/img/ETPanel5.jpg')"></div>
  </div>
  <div class="dd-hero-text">
    <a class="dd-back" href="/projects">Back to Projects</a>
    <h1 class="dd-hero-title">Egyptian Tomb Redesigned</h1>
      <div class="shadow-text" style="font-size: 1rem; text-indent: 5px; font-family: 'Playfair Display', serif !important; color: var(white); !important;">Three minute read</div>  
  </div>
</div>
  <div class="deepdive-inner">
    <div class="dd-media-block">
      <div class="dd-media-block-media">
        <video src="/assets/video/ET_ArkArt.MP4" autoplay muted playsinline></video>
        <span class="dd-caption">Originally, the inside of the ark said "The Riddle of the Sphinx," but... had nothing to do with a man walking on three legs.</span>
      </div>
      <div class="dd-media-block-text">
        <h3>Historical Research, Environment, Prop, and Puzzle Design</h3>
        <br>
        <p>
        When Egyptian Tomb was first constructed, it was designed to excite players immediately as they entered. Atmospheric lighting with flickering electric torches, large altars with ornate hieroglyphic carvings, and three inches of sand along the floor all worked to hook players into an immersive experience.</p>
        <br>
        <p>In time, however, game masters began to realize a strange recurring pattern that players took in the room. When players reached the third room, they often would lose track and go back to the first and second rooms, where most of the budget had gone. Even though the third area required no backtracking, game masters would give many hints to keep players’ attention focused. It became clear that the third room lacked something to keep players engaged.</p>
      </div>
    </div>
    <div class="dd-media-block flip">
      <div class="dd-media-block-media">
        <img src="/assets/img/ETDesignBoard.JPEG" alt="Photo of design notes on whiteboard">
        <span class="dd-caption">My design process was collaborative; I would openly display my notes and thoughts and take input from our game masters</span>
      </div>
      <div class="dd-media-block-text">
        <p>In the original design, the third area contained a rotating pillar and a prop resembling Hollywood’s Ark of the Covenant. The Ark was meant to hold gravitas on its own merit, so very little else was installed in the third room. This, however, meant the room was barren- sparse wall decoration, less sand on the ground, and a lack of puzzles meant players would often return to the previous two areas.</p>
        <br>
        <p>The Egyptian Tomb Redesign focused almost entirely on the third room. We edited the puzzles to be clearer, and we installed new tactile props with new puzzles. We repainted the walls a brilliant gold, and we coated them in ancient art, using icons from Sumerian cities, Göbekli Tepe, and other ancient locations. I took this opportunity to develop why the Ark of the Covenant would be found in an Egyptian Tomb- deciding that the Pharaoh who built the tomb was obsessed with collecting exotic art and materials.</p>
      </div>
    </div>
    <div class="dd-pullquote">
      <blockquote>
        <p>
        We did the Egyptian Tomb room, and it was so detailed. We have done many other escape rooms and none have been this immersive as far as decor and even the puzzles. (They) were so unique and unlike any escape room we've done in the past.
        </p>
        <cite>— Kayla Steele, Google Review</cite>
      </blockquote>
    </div>
    <div class="dd-media-block">
      <div class="dd-media-block-media">
        <img src="/assets/img/ETScroll.JPEG" alt="A scroll, translated into English after a short puzzle.">
        <span class="dd-caption">The names are all that is needed, but the text below push the theme of the puzzle... the voyage of the soul.</span>
      </div>
      <div class="dd-media-block-text">
        <p>
        To further the themes of exotic cultures in the Tomb, I developed a scroll that carried that necessary information for the game’s final puzzle. It was written in a script resembling Ottoman-Turkish, suggesting how other explorers from the 1800s (perhaps from the Egyptian-Ottoman War) attempted and failed to solve the puzzle they were about to attempt. Players found scraps of an English translation another explorer left behind.</p>
        <p>Immediately, we noticed the results. Game masters did not need to give as many hints, and we had an increase in the room’s victory rate- even after adding more complex puzzles to the room. For the first time, we had players requesting their victory photo be taken in the final area instead of the entrance. I cherish my time designing escape rooms because I got to immediately see the results of my work through the enjoyment of our customers. </p>
      </div>
    </div>
    <div class="dd-pullquote">
      <blockquote>
        <p>
        The puzzles were challenging and satisfying to solve. If you love translating hieroglyphic messages, answering poetic riddles, and solving physical puzzles, this is definitely the room for you!
        </p>
        <cite>— William Isenberg, Google Review</cite>
      </blockquote>
    </div>
  </div>
</div>
