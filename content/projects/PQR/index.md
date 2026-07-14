---
title: "Pierre Qui Roule"
summary: "PierreQuiRoule is a third-person platformer physic-based game developed on UE5. You play as a rock tax collector gathering moss from the other rolling stones in the kingdom of Rouleroche."
categories: ["projects","schoolproject"]
#tags: ["projects"]
extendedWidth: true

#externalUrl: ""
#showSummary: true
date: 2026-07-02
draft: false
featureimage: "card.png"   # fond de la page
thumbnail: "cover.png"     # image de la carte
---

<style>
  /* --- STYLE DE BASE DE LA VIDÉO --- */
  .zoomable-video {
    border-radius: 8px;
    overflow: hidden;
    display: block;
    cursor: zoom-in;
    width: 100%;
    position: relative;
    z-index: 1;
    
    /* Le secret : on anime la transition du transform avec un super ease-in-out */
    transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1), box-shadow 0.4s ease;
  }

  /* --- ÉTAT ZOOMÉ --- */
  .zoomable-video.is-zoomed {
    z-index: 9999;
    cursor: zoom-out;
    box-shadow: 0 20px 50px rgba(0, 0, 0, 0.6);
  }

  /* --- FOND NOIR --- */
  .video-bg-overlay {
    position: fixed;
    top: 0; left: 0; width: 100%; height: 100%;
    background: rgba(10, 10, 10, 0.85);
    z-index: 9998;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.4s ease-in-out;
  }
  .video-bg-overlay.is-active {
    opacity: 1;
    pointer-events: auto;
  }

  /* --- FIX RADICAL DES ARRONDIS DU CARROUSEL --- */
  /* On force l'arrondi sur absolument toute la structure du carrousel, de ses enfants et de ses images */
  .gallery-carousel, 
  .carousel,
  [id^="carousel-"],
  .glide,
  .glide__track,
  .glide__slides,
  .glide__slide {
    border-radius: 8px !important;
    overflow: hidden !important;
    transform: translate3d(0, 0, 0) !important; /* Force le clip de l'overflow */
    -webkit-transform: translate3d(0, 0, 0) !important;
    -webkit-backface-visibility: hidden !important;
    -webkit-perspective: 1000 !important;
  }
  
  /* On applique l'arrondi chirurgicalement à tout élément interne (div, figure, img) qui pourrait dépasser en bas */
  .gallery-carousel *, 
  .carousel *,
  [id^="carousel-"] * {
    border-radius: 8px !important;
  }

  /* Protection spécifique pour les images */
  .gallery-carousel img,
  .carousel img,
  [id^="carousel-"] img,
  .glide__slide img,
  .carousel-item img {
    border-radius: 8px !important;
    overflow: hidden !important;
    object-fit: cover !important;
  }

  /* Si le thème utilise des boutons de navigation ou des points en bas (dots) qui sont enfants du carrousel,
     on leur retire l'arrondi de 8px pour qu'ils gardent leur forme d'origine (souvent ronds ou ovales). */
  .glide__bullets,
  .glide__bullets *,
  .glide__arrows,
  .glide__arrows * {
    border-radius: 9999px !important; /* Garde les ronds de navigation intacts */
  }
</style>


<!-- Le fond noir invisible par défaut -->
<div id="videoOverlay" class="video-bg-overlay" onclick="closeVideo()"></div>



<!-- Toggle Zoom -->
<script>
const isMobileLike = window.matchMedia("(max-width: 768px), (pointer: coarse)").matches;

function getScale(firstRect) {
  // Mobile: zoom plus doux pour éviter de dépasser l'écran
  const targetWidthRatio = isMobileLike ? 0.92 : 0.50;
  const targetWidth = window.innerWidth * targetWidthRatio;
  return targetWidth / firstRect.width;
}

function toggleZoom(video) {
  const overlay = document.getElementById("videoOverlay");
  if (!overlay) return;

  const alreadyZoomed = video.classList.contains("is-zoomed");
  const otherZoomed = document.querySelector(".zoomable-video.is-zoomed");

  // Si une autre vidéo est déjà zoomée, on la ferme d'abord
  if (otherZoomed && otherZoomed !== video) {
    otherZoomed.style.transform = "";
    otherZoomed.classList.remove("is-zoomed");
  }

  // 2e tap sur la même vidéo => dézoom
  if (alreadyZoomed) {
    video.style.transform = "";
    overlay.classList.remove("is-active");
    setTimeout(function () {
      video.classList.remove("is-zoomed");
    }, 300);
    return;
  }

  // Zoom
  const first = video.getBoundingClientRect();
  video.classList.add("is-zoomed");
  overlay.classList.add("is-active");

  const centerX = window.innerWidth / 2;
  const centerY = window.innerHeight / 2;

  const videoCenterX = first.left + first.width / 2;
  const videoCenterY = first.top + first.height / 2;

  const moveX = centerX - videoCenterX;
  const moveY = centerY - videoCenterY;
  const dynamicScale = getScale(first);

  video.style.transform =
    "translate(" + moveX + "px, " + moveY + "px) scale(" + dynamicScale + ")";
}

function closeVideo() {
  const overlay = document.getElementById("videoOverlay");
  const zoomedVideo = document.querySelector(".zoomable-video.is-zoomed");
  if (!zoomedVideo) return;

  zoomedVideo.style.transform = "";
  zoomedVideo.classList.remove("is-zoomed");
  if (overlay) overlay.classList.remove("is-active");
}
</script>


<script>
document.addEventListener("DOMContentLoaded", function () {
  var videos = Array.prototype.slice.call(
    document.querySelectorAll(".article-content video")
  );
  if (!videos.length) return;

  function prime(video) {
    if (video.dataset.primed === "1") return;
    video.dataset.primed = "1";
    video.preload = "metadata";
    video.load();
  }

  videos.forEach(function (video) {
    video.muted = true;
    video.playsInline = true;
    video.loop = true;
    video.controls = false;
    video.preload = "none";
  });

  if (!("IntersectionObserver" in window)) {
    videos.forEach(function (video) {
      prime(video);
      var p = video.play();
      if (p && typeof p.catch === "function") p.catch(function () {});
    });
    return;
  }

  var io = new IntersectionObserver(function (entries) {
    entries.forEach(function (entry) {
      var video = entry.target;

      if (entry.isIntersecting) {
        prime(video);
        var p = video.play();
        if (p && typeof p.catch === "function") p.catch(function () {});
      } else {
        video.pause();
      }
    });
  }, {
    threshold: 0.35,
    rootMargin: "150px 0px"
  });

  videos.forEach(function (video) {
    io.observe(video);
  });
});
</script>


_________________________________________

# Trailer 

<div class="video-centree">
    {{< youtubeLite id="bgnM90MWV-c" label="Pierre Qui Roule TRAILER" >}}
</div>

<style>
  .video-centree > * {
    margin: 0 auto !important;
    display: block !important;
  }
  @media (max-width: 768px) {
.gallery video {
object-fit: contain !important;
}
}
</style>

{{< lead >}}
{{< /lead >}}






<style>
  /* Le "div a.btn-itch" rend la règle ultra-prioritaire sur le thème */
  div a.btn-itch {
    display: inline-block !important;
    background: #82c702 !important;       /* Ta couleur par défaut (Bleu) */
    color: #ffffff !important;            
    padding: 12px 24px !important;                    
    font-weight: bold !important;
    border-radius: 15px !important;        /* Bords moins ronds (6px) */
    text-decoration: none !important;     
    transition: background 0.2s ease !important; 
  }

  div a.btn-itch:hover {
    background: #fab05c !important;       /* Ta couleur au survol (Rouge Itch.io) */
    color: #ffffff !important;
  }
</style>

<div class="text-center w-full">
  <a href="https://colorivine.itch.io/pierre-qui-roule" class="btn-itch">
    Play it now on Itch.io !
  </a>
</div>



<div style="height: 20px;"></div> 





<style>
  .mon-keyword * {
    background-color: #ef4444 !important; /* Couleur de fond */
    color: #ffffff !important;            /* Couleur de texte */
    border-radius: 8px !important;        /* Arrondit les bords (ex: 8px ou 9999px pour un effet pilule) */
  }
</style>

<div class="flex justify-center mon-keyword">
  {{< keyword >}} Controller Highly recomended {{< /keyword >}}
</div>



_________________________________________

## <b>What is Pierre Qui Roule ?</b>

<b>PierreQuiRoule</b> is a third-person platformer physic-based game developed on UE 5.6. You play as a rock tax collector gathering moss from the other rolling stones in the kingdom of Rouleroche.
It's an old-school 3D platformer and physic based.

This is our graduation project. We had approximately <b>eight months</b> with a team of eight people to create a game from scratch. The team consisted of four Game Designers and four Tech Artists.

The game is a <b>vertical slice</b> of a full game, focusing on the third and fourth levels. The demo features <b>three distinct environments</b> : The Hub, The level "Shrooms", and The level "Ruins"

I am one of the two <b>original creators</b> of this project. A friend and I came up with the concept back in September. We wanted to break away from the walking simulator loop that dominates most student games, so we designed a <b>gameplay-focused</b> game featuring a rolling main character!

As a Game Designer, I was also one of the two <b>main gameplay programmers</b>. I worked on the <b>core gameplay loops, main mechanics and sytem design</b>. While I contributed to <b>every level</b>, I focused mostly on the cave section in the "Shrooms" level, and the second half of the "Ruins" level starting from the rails after the fight, all the way to the boss fight, which I also designed.

I also made some <b>VFX</b> since I personally love doing them.



_________________________________________
## <h1><b>Gameplay</b></h1>

 {{< youtubeLite id="5bzi0w5omNY" label="Pierre Qui Roule Gameplay Video" >}}


The movements of the characters are all physic based, wich allows us a nice boulder physics feeling.

The main gameplay mechanics are simple, you can <b>roll</b>, <b>jump</b> and jump again in the air to do a <b>"meteor strike"</b> (a down dash).

{{< gallery >}}
        <figure class="grid-w33">
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="Gameplay/rolling.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Rolling</h4></figcaption>
        </figure>
        <figure class="grid-w33">
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="Gameplay/jump.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Jumping</h4></figcaption>
        </figure>
        <figure class="grid-w33">
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="Gameplay/meteor.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Meteor Strike</h4></figcaption>
        </figure>
    {{< /gallery >}}


<div style="height: 30px;"></div> 


The main objective ot our game is th "Gather moss". To do so you have several methods: 
- Speaking : Some NPCs are not a threat to you and you can simply talk to them to pick up their moss
- Fighting : Some NPCs are threats and won't simply give you their moss. You'll have to fight for it. You can either rush at them faster than they rush at you to damage them and make them lose moss or you can do Meteor strike on them dealing way much damages. 

    *If you're tired of talking you can also hit peacefull NPCs to gather their moss.

    {{< gallery >}}
        <figure class="grid-w80">
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="Gameplay/fight.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Fight</h4></figcaption>
        </figure>
    {{< /gallery >}}

    <div style="height: 30px;"></div>

That's all for the Character's mechanics. We wanted simple and player gameplay to make the game more accessible as the player already have a new "movement" mechanic to learn. 
Our goal was to let the gameplay breathe and avoid overloading the player with mechanics.

Consequently, the majority of the game's mechanical depth and variety is driven directly by the level design
_________________________________________
### <h2><i><b>Level Design</b></i></h2>

The demo features three different levels.

- ### The HUB :
    {{< gallery >}}
        {{< figure src="Hub/Screen_MAIN.0020.jpeg" alt="Gallery image 1"  figureClass="grid-w80" >}}
    {{< /gallery >}}

     This is where the player spawns and returns between each level to deposit their moss (similar to Super Mario 64). 
     It’s a small zone that players can freely explore, featuring a few secrets and NPCs to talk to.

     It also hosts the 'Cannon Lighthouse', the hub's primary landmark that connects it to every level.
     It allows the player to select and launch each level.

     {{< gallery >}}
        {{< figure src="Hub/Screen_MAIN.0110.jpeg" alt="Gallery image 1"  figureClass="grid-w50" >}}
        <figure class="grid-w50">
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="Hub/ptp.mp4" type="video/mp4">
            </video>
            <figcaption><h4> </h4></figcaption>
        </figure>
     {{< /gallery >}}



    - #### Hub Highlight :

    {{< gallery >}}
        <figure class="grid-w100">
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="Hub/Hubhg.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Hub Peak</h4></figcaption>
        </figure>
    {{< /gallery >}}

<div style="height: 30px;"></div>

- ### The Level "Shrooms" :
    {{< gallery >}}
        {{< figure src="Shrooms/shroom1.jpeg" alt="Gallery image 1" figureClass="grid-w80" >}}
    {{< /gallery >}}

    This is the first level of the vertical slice. It allows the player to experience platforming with our unique movement style. This level introduces moss harvesting and combat, along with two new mechanics :

    - Boosters: which grant a temporary, Mario Kart-style speed boost.

    - Meteor Strike: which serves here as both a platforming and combat tool.

    {{< gallery >}}
        <figure class="grid-w50">
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="Gameplay/booster.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Boosters</h4></figcaption>
        </figure>
        <figure class="grid-w50">
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="Gameplay/meteorparkour.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Meteor Strike Platforming</h4></figcaption>
        </figure>
    {{< /gallery >}}

    It also features a railed camera system during a 2D segment. This level has a fairly slow pace to allow players to easily get a feel for the game.

    The pacing of this level is mostly slow to let the player learn the mecanics at his own rythm. 

    - #### Level Shrooms highlights :

{{< gallery >}}
    <figure class="grid-w100">
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="Shrooms/boosterss.mp4" type="video/mp4">
        </video>
        <figcaption><h4>Boosters road</h4></figcaption>
    </figure>
{{< /gallery >}}

<div style="height: 70px;"></div>

{{< gallery >}}
    <figure class="grid-w100">
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="Shrooms/village.mp4" type="video/mp4">
        </video>
        <figcaption><h4>Village of Pierrequiroule</h4></figcaption>
    </figure>
{{< /gallery >}}

<div style="height: 70px;"></div> 

- ### The Level "Ruins" :
    {{< gallery >}}
        {{< figure src="Ruins/ruin1.jpeg" alt="Gallery image 1" figureClass="grid-w80" >}}
    {{< /gallery >}}

    This is the final level of our vertical slice. It is longer than the others and culminates in a boss fight. While it reuses previously learned mechanics, the level is much more linear and stretched out, allowing the player to build up massive speed on straightaways packed with boosters. This level also introduces two new mechanics:

    - Cannons: Once inside, they automatically launch the player in the direction they are facing after a short delay.

    - Pipes: Which act as ramps and slides.
    
    {{< gallery >}}
        <figure class="grid-w50">
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="Gameplay/tub.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Tubes</h4></figcaption>
        </figure>
        <figure class="grid-w50">
            <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="Gameplay/cannon.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Cannon</h4></figcaption>
        </figure>

    {{< /gallery >}}


    The pacing of this level is much more energetic, driven entirely by a rhythm of boosters and speed bursts. 

    - #### Level Ruins highlights :

    {{< gallery >}}
        <figure class="grid-w100">
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="Ruins/ruinfight.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Tower Fight</h4></figcaption>
        </figure>
    {{< /gallery >}}
    <div style="height: 70px;"></div>
    {{< gallery >}}
        <figure class="grid-w100">
            <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="Ruins/ruinplanes.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Last Cannons</h4></figcaption>
        </figure>
    {{< /gallery >}}


<div style="height: 70px;"></div> 

- ### The Final Boss : 

    {{< gallery >}}
        {{< figure src="boss/boss1.jpeg" alt="Gallery image 1"  figureClass="grid-w80" >}}
    {{< /gallery >}}

    To close out the vertical slice, we created a boss fight. The boss is a massive rolling rock located in a unique, half-ruined structure. The fight is split into two major phases:

    - Phase 1: The boss stays in the center of the arena, periodically sending out shockwaves to push the player into the void. Meanwhile, the player must climb up two paths wrapping around the arena to reach a cannon. This cannon launches the player into the air above the boss, allowing them to execute a Meteor Strike to deal damage.

    {{< gallery >}}
        <figure class="grid-w50">
            <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="boss/bossattack.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Boss choc wave</h4></figcaption>
        </figure>
        <figure class="grid-w50">
            <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="boss/phase11.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Boss Damage</h4></figcaption>
        </figure>
    {{< /gallery >}}

    - Phase 2: This phase takes place right below the first area after the player breaks through the floor. It plays out like a classic "Whack-a-Mole" game, where the boss emerges from various molehills. The player must perform a Meteor Strike directly onto its head to deal damage. Repeating this process three times defeats the boss for good. To spice things up, the boss will start using feints after the player lands their first successful hit.

    {{< gallery >}}
        <figure class="grid-w50">
            <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="boss/phase22.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Normal</h4></figcaption>
        </figure>
        <figure class="grid-w50">
            <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="boss/phase21.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Finth</h4></figcaption>
        </figure>
    {{< /gallery >}}
 
 <div style="height: 10px;"></div> 

- ### Secrets :
Hidden throughout the levels are jokes and mini-games. Discovering these secrets rewards the player with achievements, which can be tracked on the 'Stickers' page in the pause menu.

{{< gallery >}}
    {{< figure src="secrets/secrets.png" alt="Gallery image 2" caption="Stickers Menu" figureClass="grid-w75" >}}
        <figure class="grid-w33">
            <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="vfx/trounoirpqr.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Black Hole Secret</h4></figcaption>
        </figure>
        <figure class="grid-w33">
            <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="secrets/dunk.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Basket Secret</h4></figcaption>
        </figure>
        <figure class="grid-w33">
            <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="secrets/billard.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Billard secret</h4></figcaption>
        </figure>                    
{{< /gallery >}}

_________________________________________
### <h2><i><b>UX</b></i></h2>

To give more feeling and to make the world more alive, we implemented inecrations within the environement.

We have :
- Mushrooms :
    {{< gallery >}}
        <figure class="grid-w33">
            <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="ux/sh0.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Boing Shroom</h4></figcaption>
        </figure>
        <figure class="grid-w33">
            <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="ux/sh1.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Splat Shroom</h4></figcaption>
        </figure>
        <figure class="grid-w33">
            <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="ux/sh.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Puff Shrooms</h4></figcaption>
        </figure> 
    {{< /gallery >}}

    <div style="height: 50px;"></div> 

- Destructibles :
    {{< gallery >}}
        <figure class="grid-w50">
            <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="ux/pl1.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Small Fences</h4></figcaption>
        </figure>
        <figure class="grid-w50">
            <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="ux/pl.mp4" type="video/mp4">
            </video>
            <figcaption><h4>Bigger Barriers</h4></figcaption>
        </figure>
    {{< /gallery >}}


_________________________________________
## <h1><b>ART</b></h1>

The Art Direction embraces the absurd. After all, we are in a kingdom of rolling stones ! Yet we still wanted players to be able to admire beautiful landscapes during moments of downtime.

To achieve this, we chose an ultra-stylized, semi-low-poly art style.

Our game is distinguished by its original color palette, stylized shaders and fine outlines. Its atmosphere is soft and peaceful, and the environment is enhanced by warm lighting.
Our post-processing shader enables the addition of outlines, cel shading, and stylized brush strokes (both small and large), allowing us to achieve a unique and distinctive visual style. 

{{< gallery >}}
    {{< figure src="img/cel.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}




### HUB
{{< carousel images="hubart/*" aspectRatio="16-10" interval="2500">}}

<div style="height: 70px;"></div> 

### Shrooms
{{< carousel images="shroomsart/*" aspectRatio="16-10" interval="2500">}}

<div style="height: 70px;"></div> 

### Ruins
{{< carousel images="ruinart/*" aspectRatio="16-10" interval="2500">}}

<div style="height: 70px;"></div> 

_________________________________________
### <h2><i><b>VFX</b></i></h2>

The VFX with a "*" at the end of their name are the VFX I worked on.

#### Environment :

{{< gallery >}}
    <figure class="grid-w100">
        <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="vfx/wind.mp4" type="video/mp4">
        </video>
        <figcaption><h4>Wind</h4></figcaption>
    </figure>
{{< /gallery >}}

<div style="height: 70px;"></div>

{{< gallery >}}
    <figure class="grid-w33 format-carre">
        <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="vfx/lucioles.mp4" type="video/mp4">
        </video>
        <figcaption><h4>Fireflies</h4></figcaption>
    </figure>
    <figure class="grid-w33 format-rect">
        <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="vfx/thunder.mp4" type="video/mp4">
        </video>
        <figcaption><h4>Thunder*</h4></figcaption>
    </figure>
    <figure class="grid-w33 ">
        <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="vfx/bee.mp4" type="video/mp4">
        </video>
        <figcaption><h4>Bees</h4></figcaption>
    </figure>
{{< /gallery >}}

<style> .format-carre video { aspect-ratio: 1 / 1.5 !important; } .format-rect video { aspect-ratio: 1 / 1 !important; } .gallery video { width: 100% !important; height: auto !important; object-fit: cover !important; } @media (max-width: 768px) { .gallery video { object-fit: contain !important; } } </style>


_________________________________________
#### Characters :

{{< gallery >}}
    <div class="text-center w-full">
        <figure class="grid-w100">
        <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="Gameplay/meteor.mp4" type="video/mp4">
        </video>
        <figcaption><h4>Meteor Strike*</h4></figcaption>
    </figure>
    <figure class="grid-w75">
        <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="vfx/boss.mp4" type="video/mp4">
        </video>
        <figcaption><h4>Boss Attack*</h4></figcaption>
    </figure>
    </div>
{{< /gallery >}}


<div style="height: 60px;"></div>


{{< gallery >}}
    <figure class="grid-w50">
        <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="vfx/ennemideath.mp4" type="video/mp4">
        </video>
        <figcaption><h4>Ennemies Death</h4></figcaption>
    </figure>
    <figure class="grid-w50">
        <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="vfx/trail.mp4" type="video/mp4">
        </video>
        <figcaption><h4>Player Trail*</h4></figcaption>
    </figure>
{{< /gallery >}}

_________________________________________
#### Secrets :

{{< gallery >}}
    <figure class="grid-w33">
        <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="vfx/trounoirpqr.mp4" type="video/mp4">
        </video>
        <figcaption><h4>BlackHole Secret*</h4></figcaption>
    </figure>
    <figure class="grid-w33">
        <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="secrets/dunk.mp4" type="video/mp4">
        </video>
        <figcaption><h4>Basket Secret*</h4></figcaption>
    </figure>
    <figure class="grid-w33">
        <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="vfx/confetti.mp4" type="video/mp4">
        </video>
        <figcaption><h4>Confettis</h4></figcaption>
    </figure>
{{< /gallery >}}

_________________________________________

### <h2><i><b>Cinematics</b></i></h2>

To effectively tell our game's story, we opted for various cinematic sequences throughout the vertical slice to contextualize the narrative experience for the players.

- #### Intro :
    {{< youtubeLite id="3I-4gYCh59c" label="Introduction Cinematic" params="loop=1&controls=1" >}}

    <div style="height: 70px;"></div> 

- #### Plot twist / transition :
    {{< youtubeLite id="KiG5Az0lmFE" label="Plot Twist Cinematic" params="loop=1&controls=1" >}}

    <div style="height: 70px;"></div> 

- #### Boss Cinematics:
    {{< youtubeLite id="58U5nzUcDyY" label="Introduction Cinematic" params="loop=1&controls=1" >}}


_________________________________________

## <h1><b>Steam Deck ???</b></h1>

Having recently got my hands on a Steam Deck, one of my personal goals was to get PierreQuiRoule running on it. And that’s exactly what I did!

At the very end of the project, I tweaked the game's quality settings to offer better performance and optimization for the Steam Deck. Unfortunately, because we used real-time lighting, the Steam Deck struggled to run the game smoothly. However, by switching the rendering mode for lights and shadows and dropping the graphics to "Low," I managed to make the game playable (even if it’s not the prettiest). Players can even push the settings to "Medium" if they disable foliage, allowing them to enjoy better lighting.

To avoid maintaining two separate builds, I implemented a check at startup that detects the player's screen resolution. Since the Steam Deck's resolution is fairly unique, this is enough for me to automatically apply the necessary graphical settings to keep the game running smoothly.