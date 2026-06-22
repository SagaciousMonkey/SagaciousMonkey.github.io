---
layout: page
title: About Me
permalink: /about-me
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
    --white:     #e9eaf7;
  }

  .portfolio-grid {
    grid-template-columns: repeat(3, 1fr);
    display: grid;
    width: 100%;
    justify-content: space-evenly;
    align-items: center;
    padding: 10px;
    overflow: hidden;
    margin-top: 1rem;
    margin-bottom: 3rem;
  }

  .home-photo-cell img {
    display: block;
    width: 100%;
    height: auto;
    margin: 0 auto;
    max-width: 18vw;
    object-fit: cover;
    object-position: center top;
    transition: transform 0.4s ease;
  }

.home-welcome {
  background: var(--bg);
  color: var(--text);
  font-family: 'Playfair Display', !important;
  padding-right: 2rem;
  padding-left: 2rem;
}

  .home-buttons {
    display: flex;
    gap: 0.75rem;
    flex-wrap: wrap;
    margin-top: 2.8rem;
    margin-bottom: 1.25rem;
    justify-content: center;
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
  .home-welcome-bio{
    text-indent: 25px;
    color: var(--white);
    margin: 20px;
    

  }


</style>

<div class="portfolio-grid">
  <div class="home-photo-cell">
    <img src="/assets/img/spookytower.jpg" alt="">
    </div>
  <div class="home-photo-cell">
    <img src="/assets/img/WithPresh.JPEG" alt="">
   </div>
  <div class="home-photo-cell">
    <img src="/assets/img/vermont.png" alt="">
    </div>
</div>

<div class="home-welcome">
  <p class="home-welcome-bio">Hey there! I’m a narrative designer hellbent on rewarding players who ask questions and make decisions. I’ve used environmental storytelling and immersive puzzle design to build interesting escape rooms and video games that offered unique experiences. </p>
	<p class="home-welcome-bio">As an escape room game master and designer, I had the opportunity to study players directly and see how they responded to different things in the room. I could see how groups reacted to puzzles and hints, and what grabbed player attention and what could be improved. I saw how industry conventions like “do not touch” stickers and useless electronic props dissolved the awe and admiration players had when they entered an immersive space. </p>
	<p class="home-welcome-bio">I also saw an opportunity to innovate. My moves were simple, at first- moving props around to key areas, for example. In time, they became far more detailed. I wrote faux Ottoman-Turkish on leather scrolls, charted out keyword-based chatbots and even developed Gameboy games. </p>
	<p class="home-welcome-bio">I began to notice that when you treat a player with reverence, they respond in kind. If you develop systems that account for interesting choices, players will notice your work, and will continue to want to be immersed. I’ve found this to be true in every form of media I’ve worked on- immersive experiences, film, comics and video games. 
	I’ve documented those experiences on this site in my projects page. They showcase the opportunities I took, the problems that arose, and the unique tools I designed to solve them.</p>
  <div class="home-buttons">
    <a class="home-btn" href="/projects">Projects</a>
    <a class="home-btn home-btn--ghost" href="/fiction">Fiction</a>
    <a class="home-btn home-btn--ghost" href="/resume">Resume</a>
  </div>
</div>
