---
layout: page
category: "Game Jams" # Change per page
permalink: /projects/gj
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

  .centered {
    text-align: center;
  }

  .shadow-text {
    text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.7);
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
      left: 3rem;
      right: 1rem;
    }
  }

  @media (min-width: 64em) {
    .dd-hero-text {
      left: 3rem;
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
    margin-bottom: 2rem;
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

  .dd-intro {
    line-height: 1.85;
    align-items:center;
    text-align:center;
    justify-items:center;
  }

  .dd-intro p{
    width:80%;
    align-items:center;
    text-align:center;
    justify-items:center;
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
    <div class="dd-hero-panel" style="background-image: url('/assets/img/gj1.png')"></div>
    <div class="dd-hero-panel" style="background-image: url('/assets/img/gj2.png')"></div>
    <div class="dd-hero-panel" style="background-image: url('/assets/img/soggymeter.png')"></div>
    <div class="dd-hero-panel" style="background-image: url('/assets/img/gj5.png')"></div>
    <div class="dd-hero-panel" style="background-image: url('/assets/img/gj4.png')"></div>
  </div>
  <div class="dd-hero-text">
    <a class="dd-back" href="/projects">Back to Projects</a>
    <h1 class="dd-hero-title">Game Jams</h1>
      <div class="shadow-text" style="font-size: 1rem; text-indent: 5px; font-family: 'Playfair Display', serif !important; color: var(white); !important;">Three minute read</div>  
  </div></div>

<div class="deepdive-inner">
    <div class="dd-media-block-text">
      <p>I love entering game jams! Designing new rooms at EscapeWorks meant we would plan for new experiences for weeks, and go into intense detail so constructing new rooms would take as little time as possible. I still retain those detail-oriented skills, but game jams push the envelope so I don’t get the luxury of weeks, only days!</p>
      <p>So far, each of the jams I’ve done have pushed me to make better and better content, and with each one I’ve found new elements to develop for future games. </p>
      <br>
      </div>
    <div class="dd-media-block">
      <div class="dd-media-block-media">
        <img src="/assets/img/CCC2.png" alt="A big chicken monster destroying a city">
        <span class="dd-caption">American Kaiju was designed to be a mix of Rampage and Donkey Kong Country- juggling physics-based movement and city destruction</span>
      </div>
    <div class="dd-media-block-text">
        <h3 class="centered">American Kaiju: <i>HARDBOILED</i></h3>
        <p>American Kaiju was a fun week-long jam I tackled with three friends. The jam had a very open-ended theme, so a buddy in the Discord suggested a sub-theme for us.</p>
        <p>“Chicken,” he said. </p>
        <p>"Chicken?"</p>
        <p>Our other immediate drafts and ideas were thrown out. We had been given a strange new challenge. One we couldn’t back down from! To do so would be chi-</p>
        <p>Excuse me. …To do so would be a <i>sign of extreme cowardice.</i></p>
      </div>
    </div>
    <div class="dd-media-block flip">
      <div class="dd-media-block-media">
        <img src="/assets/img/shellshook.png" alt="A chicken stares ahead, now truly understanding the depths of loss.">
        <span class="dd-caption">Had I ever truly lived before I studied how a chicken walks for three hours? Clearly my life was missing this essential experience</span>
      </div>
      <div class="dd-media-block-text">
        <p>American Kaiju, like most game jams, tested our teamwork, our ability to maintain consistency, and our confidence to commit to release. On the team, I was the jack-of-all-trades manager, and I oversaw programming, art, and the story. Giving our rooster kaiju protagonist a voice was a challenge, but I storyboarded intro and outro sequences that gave the experience flavor.</p>
        <p>It also tested the design skills I sharpened in my escape room days. Simply put, we had many ideas, but a very limited window for completion. Scope is a gigantic challenge in its own right, but my experiences planning how I could reformat an escape room in two days helped give me the vision to keep things simple here, too. We kept our priorities and released on time.</p>
      </div>
    </div>
      <div class="dd-media-block">
      <div class="dd-media-block-media">
        <img src="/assets/img/ladyfingers.png" alt="A blue demon admits their love of collecting sweet biscuits.">
        <span class="dd-caption">Retro game assets help keep the project focused. As always, I make all my own art.</span>
      </div>
    <div class="dd-media-block-text">
        <h3 class="centered">Hungry for a Biscuit</h3>
        <p>After learning the skills I needed to publish a finished Godot game, I was eager to try again, so I pushed myself to do a solo game jam. I submitted Hungry for a Biscuit to the Brackeys Game Jam 2025.2, making the step from 2D to 3D. Hungry took the jam’s theme, “Risk it for the Biscuit,” to a far too literal level, but I had a blast making it. The game gave me the skills I wanted for other projects, like 3D environment work, and it also made me learn how to incorporate a “Soggy Meter.”</p>
      </div>
    </div>
    <div class="dd-media-block flip">
      <div class="dd-media-block-media"> 
        <img src="/assets/img/museo.png" alt="A blue collar worker standing in a strange museum.">
        <span class="dd-caption">Future project... I love the aesthetic of sprites and 3D models, especially if they can blend together to evoke retro-futurism.</span>
      </div>
      <div class="dd-media-block-text">
        <p>While the game was simple, I was happy to see that environmental elements I added like spatial audio and grid-based movement get praise from the judges. I worked with new software, Trenchbroom and Blender, adding to my Aseprite work from American Kaiju. This was a large step up for me. With Hungry, I made a small environment I could relax in, a vibe I carry to my future projects. </p>
      </div>
    </div>
  </div>
</div>
