---
layout: page
category: "Flash Fiction, ~15 min read" # Change per page
hero: # Path to your hero image
permalink: /fiction/tsbts
---

<!--
  DEEP-DIVE PAGE TEMPLATE
  ========================
  Usage:
  - Copy this file, rename it (e.g. quest-design.html or quest-design.md)
  - Update the front matter above (title, category, hero image path)
  - Replace placeholder text and media paths throughout
  - Available section types:
      .dd-media-block          — alternating image/video + text
      .dd-media-block.flip     — forces media to the right side
      .dd-pullquote            — large highlighted quote
      .dd-credits              — tools/credits table at the bottom
-->

<style>

  /* ── Scoped reset ── */
  .deepdive *,
  .deepdive *::before,
  .deepdive *::after {
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

  .deepdive {
    background: var(--bg);
    color: var(--text);
    font-family: 'Inconsolata', monospace;
    font-weight: 300;

    width: 100%;
    position: relative;
  }

  .deepdive-inner {
    width: 100%;
    padding: 2rem 2rem 2rem;
  }

  @media (min-width: 48em) {
    .deepdive-inner {
      padding-left: 2rem;
      padding-right: 2rem;
    }
  }

  @media (min-width: 64em) {
    .deepdive-inner {
      padding-left: 2rem;
      padding-right: 2rem;
    }
  }
  /* ════════════════════════════════════════
     HERO
  ════════════════════════════════════════ */

.dd-hero {
    position: relative;
    width: 100%;
    /*Changed third height variable to shorten length of hero at top of page */
    height: clamp(280px, 50vh, 300px);
    overflow: hidden;
    margin-bottom: 0;
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

  /* Gradient fade at the bottom so the title reads cleanly */
  .dd-hero::after {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(
      to bottom,
      transparent 30%,
      rgba(14,13,12,0.7) 70%,
      var(--bg) 100%
    );
    pointer-events: none;
  }

  .dd-hero-text {
    bottom: 5rem;
    left: 2rem;
    right: 2rem;
    z-index: 2;
    text-shadow: 2px 2px 5px black;
    text-align: center;
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
    font-weight: 700 !important;
    color: var(--white) !important;
    line-height: 1.1 !important;
    margin: 0 !important;
    padding: 0 !important;
    text-shadow: 0 2px 20px rgba(0,0,0,0.6);
  }
    .dd-hero-subtitle {
    font-family: 'Inconsolata', serif !important;
    font-weight: 100 !important;
    color: var(--accent) !important;
    margin: 0 !important;
    padding: 0 !important;
    text-shadow: 0 2px 20px rgba(0,0,0,0.6);
  }

  .dd-lede {
    text-indent: 50px;
    max-width: 80vw;
    margin: 3rem 0 4rem;
  }

  .dd-lede p {
    font-size: 1rem;
    line-height: 1.8;
    color: white;
    margin: 0 0 1rem;
  }

  .dd-lede p:last-child {
    margin-bottom: 0;
  }

  /* Thin rule separating lede from body sections */
  .dd-divider {
    border: none;
    border-top: 1px solid var(--border);
    margin: 0 0 4rem;
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

  /* .flip: media right, text left */
  .dd-media-block.flip .dd-media-block-media { order: 2; }
  .dd-media-block.flip .dd-media-block-text  { order: 1; }

  /* Media container */
  .dd-media-block-media {
    position: relative;
    overflow: hidden;
    background: var(--surface);
    border: 1px solid var(--border);
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

  /* Caption sits below the media inside the media container */
  .dd-caption {
    display: block;
    font-size: 0.65rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--muted);
    padding: 0.65rem 0.85rem;
    border-top: 1px solid var(--border);
    background: var(--surface);
  }

  /* Text side */
  .dd-media-block-text h2 {
    font-family: 'Playfair Display', serif !important;
    font-size: clamp(1.2rem, 2vw, 1.6rem) !important;
    font-weight: 700 !important;
    color: var(--white) !important;
    margin: 0 0 1rem !important;
    padding: 0 !important;
    line-height: 1.2;
  }

  .dd-media-block-text p {
    font-size: 0.88rem;
    line-height: 1.85;
    color: var(--text);
    margin: 0 0 0.85rem;
  }

  .dd-media-block-text p:last-child {
    margin-bottom: 0;
  }

  /* Stack vertically on narrow viewports */
  @media {
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

  .dd-pullquote {
    position: relative;
    margin: 2rem 0 5rem;
    padding: 2.5rem 2rem 2.5rem 3rem;
    border-left: 3px solid var(--accent);
    background: var(--surface);
  }

  /* Large decorative quotation mark */
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
    margin-top: 0rem;
    font-size: 0.65rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--muted) !important;
    text-decoration: none !important;
    transition: color 0.2s ease;
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

  /* ── Placeholder style (remove when using real media) ── */
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
    <div class="port-hero-img"></div>
  </div>
  <div class="deepdive-inner">
    <div class="dd-hero-text">
      <span class="dd-hero-category">Flash Fiction, ~15 minute read</span>
      <h1 class="dd-hero-title">The Salt Beneath the Sea</h1>
      <h4 class="dd-hero-subtitle">Fantasy</h4>
    </div>
    <a class="dd-back" href="/fiction">Back to Portfolio</a>
    <!-- ── Lede / intro paragraph ── -->
    <div class="dd-lede">
      <p>
    	Madman Venzo spoke in harsh angles, but he played the cittern well. His songs had the architecture of great stone cities, and each pluck of the strings carved and chiseled buildings and paths. His musical direction helped the days to pass. As we climbed against the southern highlands, walking uphill and against the wind for miles, I would watch him prance from hilltop to hilltop. I had to carry the bags, but the old goat only carried a lurid joy and his stringed gourd that he played until his fingernails bled.</p><p>
      <i>“The single thought! The truth made wrought!<p>
      Beneath the arid sea,</p><p>
      ‘Twas there the wise ones did proclaim,</p><p>
      O Leucidia, to be.”</p></i><p>
      He crooned as he led me through a pair of ridges. The taste of salt grew harsher on my tongue. Mad as he was, he was right-- the sea was close. The wind grew louder over every hill we passed, calling us closer to the eternal coast. Perhaps the madman merely followed the noise of the wind. The two of them seemed close, always speaking back and forth. The wind, however, would calm and subside now and again. Venzo did not.</p><p>
      There was no end to his babbling. In his damp prison cell back home, Venzo had composed no fewer than three dozen blasphemous symphonies. It had driven the guards mad, being religious men, to hear about Leucidia this, and O Leucidia that. Venzo’s symphonies claimed that Leucidia had proven that the gods were dead. And because listening to blasphemy is a high crime in the country of Thun, the guards had to plug their ears to keep from being imprisoned themselves.</p><p>
      Once, Venzo had begun to sing a popular, lusty ballad that had been censored by the church. But when the men took the cotton out of their ears to listen in, it was O Leucidia again.<p>
      <i>“The thin-veiled ice, the whorish gneiss<p>
      That holds our symmetry;</p><p>
      Beneath the salt is carved my name.</p><p>
      O Leucidia, my plea.”</p></i><p>
      The noose barely held around the twig that was Venzo’s neck. He was thin as a snake, riddled with knots like oak. I had dropped him three times, but the rope could not find the man’s neck. As accomplished of a hangman as I was, I could find no way to stop the man from breathing, nor stop his singing.</p><p>
      The entire crowd was agape at this seemingly immortal man. The priests tore the cotton from my ears as I readied my fourth attempt at the noose. If I could not kill him, they whispered, I would have to take him as far away from the city as godly possible and leave him to rot. They aren’t allowed to spill blood in the church of Thun, but they always find a silly way around it.</p><p>
      That was how I was shamed as an executioner, and forced to become the madman’s maid. I had decided to ditch Venzo at my earliest convenience, but after some days with him, I began to enjoy his company. Eventually, I let him lead me; he was just as desperate to stay away from Thun as I was.</p><p>
      And there we were, exactly where the city had wanted the old man. Venzo had lead me to the shores of the farthest west, where no man dared to live. The saltwater was nearly poisonous, and the dunes that made up the coast stretched for miles.</p><p>
      <i>“There I begun, a simple son,<p>
      Who knew no harmony...”</p></i><p>
      The wind died down as I waited to hear the next line. We were only a few yards from the sea, but the old man’s gaze was stuck towards the horizon. His fingers grew still against the strings.</p><p>
      I attempted to continue the poem. “Is this where… I’ll leave you be?”</p><p>
      He laughed. A response! They were few and far between. “Not quite…” He continued.</p><p>
      <i>“There I begun, a simple son,<p>
      Who knew no harmony.</p><p>
      But living now, I can exclaim-!</p><p>
      You, Leucidia, must be!”</p></i><p>
      His fingers, which had been busy at the strings, curled at the end of his song. He held the cittern aside as he turned his mouth towards me, but his eyes were rigid, focused on the far edge of the water.</p><p>
      “...don’t worry, miss. When you see it, you’ll remember the music and the lines. It’ll be so nice to listen for once...I’ve had to play it myself while I was away...”</p><p>
      It struck me, hearing him put a sentence together. It was guilt that made me stay with Venzo, and empathy that forced me to stay. I imagined myself, mad, old, and alone. Won’t I want a guardian, when I reach that age?</p><p>
      But before I could pull him to somewhere greener to waste away, anywhere but the harsh and briny coast, the madman ran to the edge of the water. His body, thin and rigid, floated easily upon the saltwater. I ran to him, but with the bags, I was left tripping over the hills of soft sand. When I had managed to tear them off, Venzo was already far beyond where I could safely swim. Between my calls, begging him to return, I could hear him sing-</p><p>
      <i>“My weary bones, your wind-hewn stones!<p>
      Beneath the arid sea!</p><p>
      For all things made must be the same;</p><p>
      And I…”</p></i><p>
      His voice eventually faded.</p><p>
      It was already evening, and my guilt forbade me to leave. I set up camp on a small ridge of dirt, which rose like an altar above the sand. Venzo, in his rush to swim away, had left his cittern on the beach, and I begun to pluck at the strings.</p><p>
      When the skies turned dark, and the fire dimmed to embers, I looked out to the sea. Clouds had begun to form out beyond the horizon, and from the distance, they looked like an small island, crowned by a single hazy mountain.</p><p>
      The wind howled into my ears, and I picked up the cittern. I knew the final line.</p><p>
      <i>“For all things made must be the same;<p>
      And I, Leucidia, am thee.”</p></i><p>

    <hr class="dd-divider" />
