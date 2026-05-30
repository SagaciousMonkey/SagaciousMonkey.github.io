---
layout: nocss
category: "Outbreak '95" # Change per page
hero: "/assets/video/ET_ArkArt.MP4" # Path to your hero image
permalink: /projects/ob95
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
    --border:    #2a2520;
    --text:      #c9b99a;
    --muted:     #5e5347;
    --accent:    #b5763a;
    --accent-lt: #d4935a;
    --white:     #f0e8db;
    --navy:      #182430;   /* Hyde sidebar colour, used sparingly for cohesion */
  }

  /* ── Full-bleed wrapper (same technique as hub page) ── */
  .deepdive {
    background: var(--bg);
    color: var(--text);
    font-family: 'Inconsolata', monospace;
    font-weight: 300;

    width: 100vw;
    position: relative;
    left: 50%;
    margin-left: -50vw;
  }

  /* ── Inner container — mirrors Hyde sidebar offsets ── */
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

  .dd-hero-img {
    width: 30%;
    height: 100%;
    object-fit: cover;
    object-position: 100px;
    display: block;
    margin: 0;
    border-radius: 0;
    filter: brightness(0.55) saturate(0.7);
    transition: filter 0.6s ease;
  }

  /* Gradient fade at the bottom so the title reads cleanly */
  .dd-hero::after {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(
      to bottom,
      transparent 30%,
      rgba(34, 25, 16, 0.7) 70%,
      var(--bg) 100%
    );
    pointer-events: none;
  }

  .dd-hero-text {
    position: absolute;
    bottom: 2.5rem;
    left: 2rem;
    right: 2rem;
    z-index: 2;
  }

  @media (min-width: 48em) {
    .dd-hero-text {
      left: 22rem;
      right: 3rem;
    }
  }

  @media (min-width: 64em) {
    .dd-hero-text {
      left: 24rem;
      right: 5rem;
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

  /* ════════════════════════════════════════
     INTRO / LEDE
  ════════════════════════════════════════ */

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

  /* ════════════════════════════════════════
     MEDIA BLOCKS  (alternating layout)
  ════════════════════════════════════════ */

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

  /* Stack vertically on narrow viewports */
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

  /* ════════════════════════════════════════
     CREDITS / TOOLS SECTION
  ════════════════════════════════════════ */

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

  /* ════════════════════════════════════════
     BACK LINK
  ════════════════════════════════════════ */

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

<!-- ═══════════════════════════════════════════
     HERO
════════════════════════════════════════════ -->
<div class="deepdive">

  <div class="dd-hero">
    <!-- Replace with your hero image -->
    <!-- For a video hero instead: -->
    <img class="dd-hero-img" src="/assets/img/gobleki.JPEG" autoplay muted playsinline></img>
    <div class="dd-hero-text">
      <a class="dd-back" href="/projects">Back to Projects</a>
      <h1 class="dd-hero-title">Outbreak '95</h1>
    </div>
  </div>

  <!-- ═══════════════════════════════════════════
       BODY CONTENT
  ════════════════════════════════════════════ -->
  <div class="deepdive-inner">
    <!-- ════════════════════════════════════════
         MEDIA BLOCK 1 — image left, text right
    ════════════════════════════════════════ -->
    <div class="dd-media-block">
      <div class="dd-media-block-media">
        <!-- Replace with your image or video -->
        <!-- <img src="/assets/img/.jpg" alt="Description of image" /> -->
        <video src="/assets/video/ET_ArkArt.MP4" autoplay muted playsinline></video>
        <span class="dd-caption">Originally, the inside of the ark said: "The Riddle of the Sphinx," but... had nothing to do with a man walking on three legs.</span>
      </div>
      <div class="dd-media-block-text">
        <h3>Narrative, Environment, Prop, and Puzzle Design</h3>
        <br>
        <p>
        Outbreak was an older room, designed to be a CDC facility that housed a cure for an apocalyptic virus. In its first iteration, it was designed to be a high difficulty game that appealed to experts, but decoration was a low priority. As it looked rather plain, marketing it was difficult, and it consistently underperformed. Since it clearly needed an exciting edge, I pitched a Halloween variant- “Zombie” Outbreak. We would fill the negative space with blood, update the lighting, change the room’s soundtrack and add props that gave the room a survival-horror element. The room consistently sold out, a complete reversal of its previous performance. The owners decided that this was what Outbreak needed- and made the theme permanent.</p>
      </div>
    </div>

    <!-- ════════════════════════════════════════
         MEDIA BLOCK 2 — text left, image right (.flip)
    ════════════════════════════════════════ -->
    <div class="dd-media-block flip">
      <div class="dd-media-block-media">
        <div class="dd-placeholder">Image / Video</div>
        <!-- <img src="/assets/img/quest-02.jpg" alt="Description of image" /> -->
        <span class="dd-caption">Caption describing what the viewer is looking at</span>
      </div>
      <div class="dd-media-block-text">
        <p>Eventually the owners decided that it should be nostalgic, and suggested placing it in the Nineties. My Zombie Outbreak design already had references to Resident Evil and Army of Darkness, so it was a simple transition, though initially superficial. We needed new puzzles that evoked the technological surge of the nineties, and the team developed two new experiences that quickly became exciting new projects of their own- a Gameboy game running on original hardware and a PC that ran a Python variant of the classic Eliza chatbot.</p>
        <p>The chatbot came first. Eliza was developed in the 60s, as a quasi-therapist that would find keywords in a user’s prompts and redirect them back. “I went for a jog today,” would return “A jog? Tell me about that,” as Eliza would find the noun and place it into one of her responses. Turning her into a security system for a CDC research lab required extensive scripting. I would spend any unbooked moment to dive into the Python file and add keywords that players could spot in the room- the script began with terms like “Zombie,” and “Virus,” and ended with exact terms from the puzzles, as well as references to the other characters who worked in the lab.</p>
      </div>
    </div>

    <!-- ════════════════════════════════════════
         PULL QUOTE
    ════════════════════════════════════════ -->
    <div class="dd-pullquote">
      <blockquote>
        <p>
        Outbreak is very intricate and well architected - so much to a point that the custom gameboy component in the room is hands down one of the most unique additions to an escape room I've ever seen.
        </p>
        <cite>— Rich B, Google Review</cite>
      </blockquote>
    </div>

    <!-- ════════════════════════════════════════
         MEDIA BLOCK 3 — image left, text right
    ════════════════════════════════════════ -->
    <div class="dd-media-block">
      <div class="dd-media-block-media">
        <!-- Replace with your image or video -->
        <div class="dd-placeholder">Image / Video</div>
        <!-- <img src="/assets/img/quest-01.jpg" alt="Description of image" /> -->
        <!-- <video src="/assets/video/quest-01.mp4" autoplay muted loop playsinline></video> -->
        <span class="dd-caption">Caption describing what the viewer is looking at</span>
      </div>
      <div class="dd-media-block-text">
        <p>
        Scripting the Gameboy game and the chatbot, I was able to honor the work of my previous manager, who had written a binder of journal entries from a character named Dr. Alan Williams. The journal contained a puzzle that made players read each of the dozen pages. This was removed for better game flow, but with the cut, we also lost a great deal of immersion- the characters in the lab were essentially removed with the binder. I realized that with Eliza, we could do two things- add more references to the characters, and reward players who asked about them with hints about other puzzles. “Eric” would return “Your partner, Dr. Eric Hill? A smart man… but prone to distraction. Why does he insist on taking notes with a video game cartridge? I don’t think a ‘secret code’ is an effective security measure, either…”</p>
        <p>The Gameboy really hammered in the themes of technological overindulgence. It was a strange addition, but it was one that resonated with players. A previous attempt at a Nineties device, a cassette deck, was scrapped after players damaged it within hours- but with the Gameboy, there was an odd reverence. Players would pass it around, keep it on to hear the soundtrack, and read through Dr. Hill’s notes and journal entries. Like Eliza, Dr. Hill had a puzzle attached (the secret code, mentioned before), but he also would comment on other corners of the room. One of our earliest escapes had taken notes from Dr. Hill and Eliza, and had used their hints to help solve the other puzzles and riddles- the game master didn’t need to send a single hint to them.</p>

      </div>
    </div>

    <!-- ════════════════════════════════════════
         MEDIA BLOCK 2 — text left, image right (.flip)
    ════════════════════════════════════════ -->
    <div class="dd-media-block flip">
      <div class="dd-media-block-media">
        <div class="dd-placeholder">Image / Video</div>
        <!-- <img src="/assets/img/quest-02.jpg" alt="Description of image" /> -->
        <span class="dd-caption">Caption describing what the viewer is looking at</span>
      </div>
      <div class="dd-media-block-text">
        <p>This was the most interesting element of the update- the addition of narrative elements that were not mandatory. By adding this, we created an escape room that offered multiple kinds of rewarding play. Players could focus either on the logical answers, or they could dive into the text to understand more about the purpose of the puzzles, often to get hints for future brainteasers. Players would split up, investigate different corners, then re-group with different perspectives. Often we design escape rooms so players have to do this- rarely do we get to engender this thinking across the entire experience.</p>
        <p>I’ll never forget a game I hosted when a teenager asked me more about what happened to the characters. He had read every entry and had been talking to Eliza. Alan was pushed as the hero of the room- his corpse, dressed in a hazmat suit, hands players an important key. But Dr. Hill’s remains were nowhere to be found. Asking players to wonder what is absent in a room, while maintaining immersion, is an incredibly difficult task, one that should often only be used for flavor. In the shadow of the hero my previous manager had written, I decided to write Dr. Hill as a coward- and very few realized that he had abandoned his duties. But the fact that someone had figured it out meant a lot to me. These are the connections I strive to develop.</p>
      </div>
    </div>

    <!-- ════════════════════════════════════════
         PULL QUOTE
    ════════════════════════════════════════ -->
    <div class="dd-pullquote">
      <blockquote>
        <p>
        We did the virus outbreak scenario for a teambuilding event. Everyone raved about how fun this was, it far exceeded expectations even for a bunch of engineer dorks. The game was brilliantly designed, the puzzles were very challenging but not frustrating.
        </p>
        <cite>— Jeremy Smolik, Google Review</cite>
      </blockquote>
    </div>

  </div><!-- /.deepdive-inner -->
</div><!-- /.deepdive -->
