---
layout: nocss
category: "Short Story, ~20 min read" # Change per page
hero: # Path to your hero image
permalink: /fiction/short-story
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

  p {
    text-indent: 50px;
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

  /* ── Full-bleed wrapper (same technique as hub page) ── */
  .deepdive {
    background: var(--bg);
    color: var(--text);
    font-family: 'Inconsolata', monospace;
    font-weight: 300;

    width: 100vw;
    position: relative;
    left: 75%;
    margin-left: -50vw;
  }

  /* ── Inner container — SPECIAL FOR SHORT STORY */
  .deepdive-inner {
    width: 100%;
    text-align:left
  }

  @media (min-width: 48em) {
    .deepdive-inner {
      padding-left: 22rem;
      padding-right: 3rem;
    }
  }

  @media (min-width: 64em) {
    .deepdive-inner {
      padding-left: 24rem;
      padding-right: 5rem;
    }
  }

  /* ════════════════════════════════════════
     HERO
  ════════════════════════════════════════ */

  .dd-hero {
    position: relative;
    width: 100%;
    height: clamp(280px, 50vh, 520px);
    overflow: hidden;
    margin-bottom: 0;
  }

  .port-hero {
  width: 100vw;
  position: relative;
  left: 50%;
  margin-left: -50vw;
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

  /* ════════════════════════════════════════
     INTRO / LEDE
  ════════════════════════════════════════ */

  .dd-lede {
    max-width: 80ch;
    margin: 3rem 0 4rem;
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
    margin: 0 0 4rem;
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
    <div class="dd-hero-text">
      <span class="dd-hero-category">Short Story, ~20 minute read</span>
      <h1 class="dd-hero-title">Thieves of the Orchard</h1>
      <h4 class="dd-hero-subtitle">Winner of the El Portal Space Western Award</h4>
    </div>
  </div>
  <div class="deepdive-inner">
    <a class="dd-back" href="/fiction">Back to Portfolio</a>
    <div class="dd-lede">
      <p>
        The little one's tears were getting close to my drink, and the big one's hand was grasping my shoulder too tightly. I grit my teeth and growled at neither one in particular.
      </p><p>
        "Make my night any more uncomfortable, and you'll be begging for more than your land." They withdrew half a step. Enough for me to take a swig, at least. My drink tasted like a cranberry bog back on Earth, complete with shrubs and rubber boots. A Purple Jupiter, they called it. With each sip I felt like I was going back to the Milky Way, back home.
      </p><p>
        Once it was down my throat, though, I was back there in that dim bar with the two fools. I was part of a mercenary clan then, and my bosses had told me that they'd give me a few days off as long as I scouted around the area and let my ship draw some rough maps. It gave me a chance to settle down and enjoy the sights as my ship cruised by nebulae and planets. Ended each day with a Purple Jupiter and a few memories. That night, though, those two were tripping up my reminiscences, and I didn't appreciate it.
      </p><p>
        "Sir, we've been on the orchard for more than a decade now. It's our home. No other place in the galaxies could give us the contentment we have there." The little one, his face contorted from the incessant sobbing, squeaked out. 
      </p><p>
        "It wouldn't take long for a man like yourself, an easy grand..." The big one grumbled. Again, that hand on my shoulder tightened.
      </p><p>
        I don't enjoy getting manhandled by anyone pushing their weight around. I stood, one foot on the bench, and grabbed his arm, bringing my eyes close to his. "I told you my reasons, been a gentleman until now. But you grab my shoulder again, and I won't mind getting rough." We stood there for a good three seconds before he backed off. I rolled my shoulder, and reached for my drink, but before I could sit down an odd voice froze us in place.
      </p><p>
        "No need to bother him anymore, fellas! I'll gladly take that grand off your hands." The three of us turned, and I saw some girl standing on a chair behind me. Her eyes were on my level, though only with the added height of the chair. Big grin on her face, she looks right past me, toward the two simpletons. 
      </p><p>
        "You wanna take the job, miss?" Shorty asks. No tears on his face anymore, or even any sign that he had been sobbing. Just curiosity with a drop of discrimination.
      </p><p>
      	"Sure. What is it?" Tufts of black hair bob as she speaks. The big one steps away from me and turns to her.
      </p><p> 
      	"You a mercenary, girl? What colors do you fly?" We all glanced at her jacket. She had no symbols on her shoulders like I did, but there was a small indent in the fabric that made it look like something used to be there. She glanced at my coalition's colors before replying.
      </p><p>
      	"I don't work in a squadron. Name’s Cersa Scath, lonesome freelancer." At this point, the farmers were finally a comfortable distance from me, focused on their new target. I sat down and pulled out my palmtop, hoping that this dim bar had some way for me to connect online. Lucky for me, it did.
      </p><p>
        "We aren't asking for a simple job, miss. You're gonna need a trigger finger to help us out." The big one says, crossing his arms. It would be beneath him to let a woman do a man's job, I guessed.
      </p><p>
        She whipped out a revolver. Red finish, loaded. "Got one."
      </p><p>
        They spoke a bit more, but I wasn't really listening. I was tapping away at my phone, loading up a search engine for my mercenary union's database. After a few attempts to spell her name correctly, the palmtop eventually ended on “CERSA SCATH.” As the loading bar crept across the screen, I tuned back in.
      </p><p>
        "Of course I have Faster-Than-Light! I can make it to your orchard in minutes." Her mouth pursed a little. While she didn't flaunt it like the big one, she had some pride. FTL engines were pricey, but any mercenary ship had a few, and any well-doing traveler would be sure to install one. My phone beeped. CERSA SCATH, it read. Female, 26. Wanted for traitorous acts by the Falcons of Mars. Bounty: High. Possessing mercenary property. And then, to the side of all this, was the emblem that was on my shoulder, a red eagle in a sea of gold.
      </p><p>
        I twitched for my coat holster, but I stopped myself. I hadn't had a day off in a month, and taking her in would mean a lot of payless overtime. I put my hand back on the table and turned back at the girl. She was talking to the farmers, her revolver still in her hands. Her eyes wandered my way, and her revolver gestured an inch in my direction. I couldn't help but chuckle... She was smart. If I had decided that the money was worth it, she'd have shot me in the back before I could turn. I made a mental note not to underestimate shorter women and brought the drink to my lips.
      </p><p>
        "I'll be blunt, miss. Our orchard's covered in robots. They'll tear you to pieces." The little one spoke up.
      </p><p>
        "Military?” She asked, beaming.
      </p><p>
        “Well, no... Farming robots.”
      </p><p>
        “Aw, farming robots don't hurt people, they’ve got too much pacifism coded into them. You’d be lucky to find one that can speak rationally. Did they hurt you?" As she spoke, she turned to her seat and grabbed a pilot's helmet.
      </p><p>
        "Well, they-"
      </p><p>
        "They threatened to.” The big one spat over his compatriot. “I don't want to take any chances. Those things are cold, you know. They can work, but they don't think like we do. No morals."
      </p><p>
        "I'll take my chances, then. Give me the coordinates for your orchard."
      </p><p>
        "It's a small planet, currently off the charts." The little one walked over to her, device in hand. "You'll have to aim for these coordinates, and it’ll be in sight from there.  The only purple planet in the system." He tapped a few things, and the girl's device beeped.
      </p><p>
        "Does it have a name?" She began typing on her phone.
      </p><p>
        "This scientist man came down a while back, took surveys, asked questions... He said that his council named it 'Amadeus-9d', but we farming folk didn't really care for it. Since it's covered in this gray, furry moss, we like to call it..." The little man paused, curling the edges of his mouth.
      </p><p>
        "Rat's Ass. It's called Rat's Ass." The big one said. The girl laughed. I scoffed a little and took another swig.
      </p><p>
        "I'll have those robots cleared by dawn tomorrow. I'll call you when it's safe." She put her helmet on and lowered some goggles over her eyes. Old paraphernalia. The straps were worn and leather-bound. She walked out of the bar, leaving the three of us still inside.
      </p><p>
        The farmers looked at one another and scurried over to the window. My pride told me to stay seated, but I brushed it aside and walked over, drink in hand. The big farmer noticed me and chuckled. One glance at my eyes, though, and he turned back to the window. The three of us stood there, searching the garage for her ship. There was a homely green cruiser, undoubtedly the farmers'. Mine was there, too, A larger, crimson ship with dual-FTL and a large custom-made cannon. It looked like a king in that near-empty lot, but it was actually a pretty average ship for a Falcon of Mars mercenary. Aside from that, however, there was no other ship in the lot.
      </p><p> 
        "What's she pulling?" The small farmer murmured. We heard engines start up, and all three of us put our faces closer to the dirty window. And then, from behind my ship, a single FTL engine rose. It was scarred and bent, and seemed to have trouble staying afloat.
      </p><p> 
        "There's the engine, where's the ship?" The big one pointed. "She isn't planning to ride an engine bareback, is she?" He guffawed. The single floating engine turned to the side, and we all saw it. The ship was puny, half the size of the engine, a pile of mismatched upgrades hooked up to a single cockpit. It was attached to the FTL by a pile of naked cords, which looked like they'd snap at any minute. The cockpit rose above the FTL, dragged it higher into the sky, and with a spluttering rumble the ship took off. For a mere second, I could see the FTL push forward, dragging the cockpit with cords pulled tight, like tendons. Then, there was nothing.
      </p><p>
        My loyalties were at rest. No way a ship like that could escape the Falcons of Mars for long... Might as well let her have one last job. With a small smile, I shut my palmtop and ordered another drink. Purple Jupiter.
      </p><p>
        "Whatever you’re mixing, make it three, bartender." The big farmer limped over to a seat. His friend was still at the window, his head buried in his hands.
      </p><p>
                  #   #   #
      <p>
        Cersa screamed as her ship, <i>The Cassowary,</i> achieved light speed. She loved watching those decimals run across the screen and then, with a snap, land decisively at “1c”.
      </p><p>
        With its current equipment, <i>The Cassowary</i> could launch Cersa fifteen thousand feet into a planet before she'd feel the metal collide into her head. That was providing that the emergency systems were down, though. They all seemed to be managing well last month, except for the airbags that kicked up a shard or two of shrapnel a few weeks back.
      </p><p>
        The ship came to a halt in some lone pocket of nothingness. As the computer clicked, whirred, and spat out a map with coordinates, Cersa beamed and re-adjusted her helmet. She pulled out the paper from her ship's computer, and made the necessary adjustments for the second, and final, jump. The FTL engine whirred to her right, charging for the next leap.
      </p><p>
        "Check yourself, Rat's Ass, I'm on my way!" She yelled, grinning as she  pressed the FTL button the moment it was ready.
      </p><p>
        A flash of lines, a cluster of colors, and the screeching engine filled Cersa's senses. She bent forward into the window, imbued with the adrenaline of a wayfaring life.
      </p><p>
        And then, the window was filled with the sight of the dim purple planet. The FTL spluttered, as did Cersa with it. The FTL had curved her approach and landed her right outside of Rat's Ass' atmosphere. Frantic, she pressed a dozen red buttons, but to no use. Rat's Ass was pulling her in.
      </p><p>
        She stared, teeth grit and her eyes frantic. It wasn’t a death sentence, but the landing was sure to be uncomfortable. Cersa’s senses dulled as she pressed herself back into her seat, keeping her head as far from the air bags as she could get. She readied herself for the inevitable loss of senses.
      </p><p>
        Things went black for a moment until Cersa came to. She looked around her beloved Cassowary, and surprisingly found little damage. One of those little red buttons had done its job. However, she couldn't help but yelp quietly when she looked out the side window: the FTL was nowhere in sight.
      </p><p>
        Cersa pried open her cockpit and slunk out, her senses still deluded. Strength sapped, she laid her head onto the ground and rested, wide-eyed and scatter-minded. The fur that covered the ground felt soft to her head, and she cuddled into it before realizing that it was Rat's Ass she was nestling in. She was far too tired to be disgusted.
      </p><p>
        She glanced to her left and right, taking in the scene. Large purple trees covered the land, making cool shade in the dim sunlight. Odd purple fruit dotted the furry ground. A foul, sickly sweet smell, like rotting blueberries, filled her nostrils. At first she wanted to vomit, but with another sniff, the smell became softer. At the third, the smell became creamy, aged ambrosia. Her mind eased, and relapsed into memory. Burning metal and lifeless cold entered her bones, bathed in the smell of the syrupy, pulpy fruit.
      </p><p>
        "Miss, are you alright?" A voice called to her. She tilted her head. A metal tower stood over her. It's head, among the clouds, craned down to stare into her eyes. "Miss?"</p><p>
        "Fine. Fine..." She brought herself to rise. To her surprise, the tower was only a foot taller than she was. It was a simplistic robot, made for mindless tasks. Thin metal on an thinner skeleton, and a faceless head with two flat windows for eyes.
        "Would you like our help? We can take you to our home and get you something to eat. If you enjoy the smell of the xangmu fruit, we've got plenty." Another robot, putting its hand softly on her shoulder, stepped forward.</p><p>
        "Sounds nice..." She mumbled. The robots looked at one another, and nodded. The one behind her hoisted her up, and carried her like a newborn. She had enough strength to resist, but the robot was so tender that Cersa felt no ill-will from it. She tried to regain her senses.</p><p>
        "FTL. What happened?" She stuttered out words. 
        "Your FTL engine broke after it entered the atmosphere. Lucky for you, it split into large pieces. Very easily repairable." It was silent for a moment, trying to think of anything else to mention. "You are unharmed. Your ship took minor damage as well. We are taking you to our orchard's farmhouse.”</p><p>
        Cersa began to put it all together in her head. However, her tact was still not quite there. "You're... You're not owned by a little man and a fat man, are you?"</p><p>
        The robot stalled for a moment. "We were. I think we were. Are we still? I suppose." The robot continued its march, holding her close. Cersa couldn't help but chuckle a little bit, picturing those two fools running away from such polite, weaponless robots as these. She put her arms around the robot's neck, and laughed. 
        "Just curious.”</p><p>
      #   #   #</p><p>
        The two robots carried her inside their home, and sat her daintily at a large table. One reached for a cup, and another put a kettle on a nearby stove.</p><p>
        “You're farming models, right?” Cersa asked as another robot draped a blanket over her shoulders.</p><p>
        “We are.”</p><p>
        “Aren't farming models supposed to do their work and stay quiet?” Cersa asked. Her eyes furrowed and her mouth curved in a knowing smile.</p><p>
        The first walked over to Cersa and handed her some tea. It was pale purple, and smelled like the wangmu fruit from earlier.</p><p>
        “You were hired to eradicate us, were you not?” One of them asked. Its eyes, dim, red-hued lights under scratched glass, studied Cersa.</p><p>
        “I was. However, I was expecting murderous death-robots or something.” Cersa took a sip. “Since you've been so polite to me, I'll give you a chance to tell me your side of the story.”</p><p>
        The robots began to look at one another again. It seemed as if they were asking one another what to do.</p><p>
        “We were once incapable of speech. We gathered the fruit off the trees, and kept the moss-fur from spreading over their trunks. We never spoke to our owners, and we rarely saw them.”</p><p>
        “They often took the fruit away in large tanks, and would leave us alone for months.”</p><p>
        “Those were lonely times. We would finish our jobs in hours, and spend the rest of the day watching the fruit blossom and grow. Sitting silently next to one another, we waited for the fruit and the moss and the trees.”</p><p>
        “That is, until 522 spoke to 523.”</p><p>
        Cersa took another sip and smiled. As the robots told the story, they looked and pointed to one another, and gave hand movements for certain parts. They were anything but lifeless. She had never seen machinery move like this before, never seen a robot move for artistic purpose.</p><p>
        “I am 522. I turned to 523, and something in me made me speak. I asked: 'How are you?'”</p><p>
        The second robot, apparently 523, nodded. “And I replied, 'I am.'”</p><p>
        The third raised a hand. “In that moment, we all began to realize something. We all looked at our hands, we touched our eyes, we touched the trees. We realized we existed.”</p><p>
        “It was magnificent. We began to speak to one another, and we each gave different responses. We had created thought and diversity in a single day.”</p><p>
        “We realized that we worked far harder than the farmers did, and that we deserved something more.”</p><p>
        The other two were silent. The third spoke up. “But we did not harm them. We cannot harm anyone, that much is coded far too deeply into us. However, when they landed, we walked out to their ship and asked for joint ownership.”</p><p>
        Cersa spit out some of her tea mid-sip, laughing.</p><p>
        “We realize it seems silly for a robot to ask to own land, but we were no longer content with work. After our epiphany, our minds craved so much more.”</p><p>
        “They screamed and flew away, leaving us on the planet. We have not heard from them since. We had guessed that they had given us our land. We did not realize they thought we were hostile.”</p><p>
        “Quick lesson on human thought: expect the worst from others.” Cersa put the cup down.</p><p>
        The robots all turned to her. “So will you kill us?”</p><p>
        Cersa sat and thought for a moment. It didn't take her long to reach a conclusion.</p><p>
        “Of course not,” she frowned. “You've been wronged, and I can't resist helping.”</p><p>
        The robots eased slightly in their chairs.</p><p>
        “There is one problem, though,” Cersa began. “These farmers are not going to share. If you want this land, you will have to murder for it. Can you do that?”</p><p>
        “No. We cannot harm anyone. We cannot.” The robots shook their heads furiously. One of them put a hand to its forehead, as if it had a headache.</p><p>
        “Then there is only one thing that can be done. I'll have to murder them for you.”</p><p>
        The robots looked up at her, still and emotionless. Cersa shrugged.</p><p>
      #   #   #</p><p>
        “Cersa Scath calling. Robots destroyed. Safe to approach. Copy?” Cersa spoke into the radio of her ship. The robots had fixed it in less than an hour, and were even able to attach the FTL back on. They had apparently began to hoard information after their epiphany, and were now avid mechanics as well as philosophers.</p><p>
        “I repeat. Cersa Scath. Cute little thing you met at the bar. Robots are destroyed. Copy?” Cersa called again, smacking the radio box. She always hated using it. Too bad cell phone coverage never moved half as fast as civilization did.</p><p>
        “We're here.” One of them, Cersa guessed the big one, spoke.</p><p>
        “Great. Killed the robots off, you're safe to land. Got my money?” She replied.</p><p>
        “I don't think you understand, girl.” The voice growled. “We're here.”</p><p>
        Cersa rose an eyebrow as she saw one of the robots outside point to a nearby hill. A spaceship was landing on it, carrying a large crate, twice the size of Cersa's ship.</p><p>
        “And we see you've taken to the robots, too.” Another voice. The smaller one. “Here we were, thinking they were going to kill you! Apparently, they were more seductive than we thought.”</p><p>
        “Don't bother none, though.” The large one mumbled vehemently.</p><p>
        “That's right, don't bother none. Just means we get more bang outta our buck. We bought this thing here to take care of three robots, but it can take care of people mighty fine, too!”</p><p>
        One side of the crate fell down, and Cersa groaned. A large robot stepped out on two humanoid legs, covered in weaponry and foreign flags. The thing dripped bullets and spare pieces with each step, and pointed two large arm-cannons towards Cersa. Those idiots had bought a warmachine for three farming robots.</p><p>
        “You know, the trees we grow'll actually suck up anything out of the ground, flesh and blood included. Next harvest ought to be a good one!” The small one yelled. The large one's laughter bellowed through just as a bullet hit Cersa's hull. Just for kicks, the farmers had opened their ship's window and were sticking rifles out.</p><p>
        “Get to the farmhouse, I'll take care of them!” Cersa shouted over the sound of her ship starting up. The robots obeyed, dashing between trees as the farmers took potshots at them.</p><p>
        Cersa gripped the controls tight, allocating power from the FTL into the single gun on the left side. She aimed it as the ship rose, but before she could lock onto the warmachine, the ship tilted to the right. The FTL was, again, weighing her ship down.</p><p>
        “Goddamned-” She let out before bullets ripped through her hull. Lights flashed and turned dim as she squinted out through the window. The warmachine was approaching.</p><p> 
        FTL OFFLINE, The Cassowary screamed. The bullets had pierced some of the cords connecting the engine and the cockpit.</p><p>
        “Who needs it, anyway?” Cersa smiled wickedly and put all power into thrust. The ship rose quickly, snapping the remaining cords and leaving the FTL on the ground. With another gust of bullets, the FTL caught fire and began to smoke.</p><p>
        The Cassowary spun as it darted to the right, dodging a flurry of bullets. Cersa's ship was quick and agile again. She zipped it under the farmers, and pointed the gun at the backside of the warmachine. Before it could twist around, the gun charged and let loose three shells. One of the warmachine's arms fell off.</p><p>
        “Not made for maneuverability, are you?” Cersa grunted as she twisted the ship again, pointing at the other arm. After a quick reload, it fell to the ground. Warmachines were tough in platoons, but weren't smart enough to handle one-on-one combat.</p><p>
        “-Gave us another faulty 'bot, they did!” Cersa could hear from outside. The farmers were bickering. Before they could charge their FTLs and escape, Cersa maneuvered her ship above them and pointed the thrusters up. The Cassowary’s thrusters blazed, and the ship fell upon the farmers, piledriving them into the ground. She leapt out, revolver in hand.</p><p>
        They were trying to move their rifles out towards her, but they were too unwieldy inside a ship. With a shot, the big one fell against the controls. Only the little one left. Cersa pointed her gun at him.</p><p>
        “They're just robots, they aren't like us! Why the Hell would you help a pile of cold steel-” Another gunshot interrupted him for good. When Cersa had it in her mind to kill, she didn't leave much time for contemplation.</p><p>
        The warmachine, armless and dazed, watched Cersa walk back to the farmhouse.</p><p>
      #   #   #</p><p>
        “You have our thanks. We hope you understand we cannot offer much.” Two of the robots stood next to Cersa's ship. The other was on top of the warmachine, ripping out old cords and inserting in new ones.</p><p>
        “I realize that, don't worry about it.” Cersa smiled. She was content. After a day or two at the orchard, her ship was repaired, FTL attached, and she had found a couple thousand or so credits in the farmers' wallets. Enough to last a month or so as she searched for a new job. “I just hope you realize something...”</p><p>
        The robots stood silent, waiting for her to continue.</p><p>
        “You've got neighbors on this planet and in the stars. They'll want your land, and they'll be made out of flesh and blood. If you want to stay free, stay alive, then you'll have to kill a few. You think you're up to it now?”</p><p>
        The robots looked at each other, silently conferring. </p><p>
        “We will consider.”</p><p>
        Cersa nodded. “A good start. I'll be off, then.”</p><p>
        They nodded, and one of them handed her a basket of wangmu fruit. She smiled, took it, and set it down at her feet. </p><p>
        Her ship rose, weighed as ever, and took off into the air before the FTL zipped it out of the planet. The two robots watched it disappear, and then gazed towards the farmer's ship.</p><p>
        “We'll have to clean the mess.”</p><p>
        The other nodded.</p><p>
        As the skies of Rat's Ass turned a tired, hazy orange, the robots pulled the bodies of the farmers out of the ship and began to snap them into pieces. They collected them into baskets, and spread them out among the trees. When the skies became black, they sat upon the top of the repaired warmachine and awaited the next harvest.
    <hr class="dd-divider" />
