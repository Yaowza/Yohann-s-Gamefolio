---
title: "Jusant DLC, ABYSS"
summary: "A Jusant imaginary DLC, made in two months with a 8 person group projet. It was a shared project with two group (total of 17 members) sharing some code and assets to speed up the production and higher the results"
categories: ["projects","schoolproject"]
#tags: ["projects"]


#externalUrl: ""
#showSummary: true
date: 2025-05-01
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
</style>


<!-- Le fond noir invisible par défaut -->
<div id="videoOverlay" class="video-bg-overlay" onclick="closeVideo()"></div>

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
    {{< youtubeLite id="P9CIuK5e5Mo" label="Jusant Abyss & Embrun TRAILER" >}}
</div>

<style>
  .video-centree > * {
    margin: 0 auto !important;
    display: block !important;
  }
</style>

{{< lead >}}
{{< /lead >}}

<!--
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

-->


_________________________________________

## **What is Jusant DLC Abyss & Embrun ?**

For this Master’s 1 project, developed in collaboration with professionals from the game studio "Don't Nod", our promotion created two imaginary DLCs from Jusant : "Abyss" and "Embrun."

We had to recreate the base game experience and visuals as close as possible to the original game and create a new narration and add a new unique mechanic. All from scratch, we didn't have any asset or code given by the Jusant Team.

While my group focused on "Abyss" and the second group handled "Embrun," we established a highly efficient cross-team pipeline to share code and assets. For instance, a member from the Embrun team developed the climbing system, while I programmed the rope mechanics used by both groups.


### **Narration**

Both DLCs serve as a speculative sequel to the main game. Gravity has been restored, and water has finally begun to fall once again.

Players embody a survivor of a forgotten, subterranean civilization. Generations ago, their ancestors fled into the dark, rifts of what remains of oceans, desperately chasing the last remnants of evaporating water. 

*We structured our collaborative projects into a tragic two-part exodus:*

- Chapter 1 (DLC "Abyss"): Our chapter opens at the exact point when water cascades back into the deep. Awakened by this miracle, the subterranean people begin a march back toward the surface. However, a sudden, catastrophic accident sends our protagonist plunging back down into the absolute darkest depths of the world.

    The protagonist wakes up suspended in the deep abyss, bound to a repurposed cargo drone. In this crushing, high-density atmosphere, the machine struggles to keep the character airborne, initiating a slow, dramatic descent into a beautiful yet terrifying ecosystem.

    The narrative relies entirely on the environment to convey danger and awe:

    The ascension takes place through a butifull underworld where the eerie glow of the underground flora illuminates the wall just like you where underwater.
    However be carefull the beasts here are curious and won't miss the opportuniy to taste the new arrivant.

- Chapter 2 (DLC "Embrun") : This chapter start when the player finaly get out of the depth back to his abondonned village. And tells the story of our protagonist climbing back to the surface with his lost friend "Raak".

*I will not explain it further as I have not worked on this chapter.*

## <h1>Gameplay</h1>

 {{< youtubeLite id="6PFvjuGW7SQ" label="Jusant DLC - Abyss Gameplay Video" >}}


- ### Climbing
    To create an experience close to Jusant, it was essential to replicate their climbing mechanic. This is what we did, and apart from a few character animation bugs, we succeeded. The climbing in our game works exactly like in the original game.

{{< gallery >}}
    <figure class="grid-w50 decal-droite">
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="Gameplay/JusantClimbing.mp4" type="video/mp4">
        </video>
        <figcaption><h4> </h4></figcaption>
    </figure>
{{< /gallery >}}

<style>
figure.decal-droite {
    margin-left: 30px !important; /* Ajuste les pixels (ex: 40px, 100px) pour la décaler plus ou moins */
}
</style>

- ### The Rope

    Then there is "The Rope" that connects the player to the pitons. It is an integral part of Jusant's experience, but a technical nightmare to develop. Managing the rope's physics, collisions, environmental interactions, how it pulls the character, and the swinging mechanics in mid-air is incredibly complex.

    We were strongly advised against implementing it, as it reportedly took Don't Nod two years to perfect it without bugs.

    HOWEVER, I really wanted to recreate this rope, especially since it was necessary for our new custom mechanic, "The Drone". So, I took on the challenge and built it anyway. While my version isn't as flawless as the one in Jusant, it comes very close. Considering I only had two months to develop it alongside my other tasks, I am very proud of the result !


    <details class="mon-menu-deroulant">
    <summary>→ For further explainations clic here ! ←</summary>
    <div class="contenu-texte">
        <p>

    To build it, I started with Unreal Engine’s Cable Component, which gave me a solid starting point. However, its built-in physics collisions were terrible, the cable constantly clipped through every single piece of geometry. (At that moment, I knew I was in for a long and painful journey...)

    First, I tweaked its length, segment count, and stiffness to dial in a satisfying, natural rope feel.

    To fix the collision issues, I enabled Substepping to increase the precision of the physics calculations, alongside other specific parameters. Through continuous trial and error, I finally managed to achieve reliable collisions on the rope itself.

    Now that the visual rope was behaving, the code responsible for pulling the player toward the drone (or vice versa) was still completely broken. Mathematically, the connection between the player and a piton or the drone was still just a rigid, straight 3D vector that completely ignored walls. If I walked around a pillar, the rope would clip right through it once it reached its maximum length, failing to pull the drone or restrict the player's movement.

    To solve this, I implemented a dynamic point-tracking system :

    - I fetched the world positions of a set number of points along the active Cable Component.

    - I calculated the average distance between adjacent points to track the rope's tension across its entire length.

    - When the distance between two points exceeded a specific threshold, the system applied a force pulling either the player or the drone toward the nearest point on the rope rather than the anchor itself.

    Thanks to this system, the physics now accurately wrap around corners and wall edges. No more invisible straight lines clipping through geometry. The result is a fully functional, physically reactive rope system, very close to Jusant's behavior!
    </p>
    </div>
    </details>

<style> .mon-menu-deroulant summary { cursor: pointer; font-weight: bold; padding: 10px; background-color: #00000000; border-radius: 4px; list-style: none; color: #c4fa45; } .mon-menu-deroulant summary:hover { color: #fad045; } .mon-menu-deroulant .contenu-texte { padding: 15px; border: 1px solid #e0e0e000; border-top: none; background-color: #ffffff00; color: #d4d4d4; } </style> 
  

{{< gallery >}}
    <figure class="grid-w50 decal-droite">
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="Gameplay/ropedemo.mp4" type="video/mp4">
        </video>
        <figcaption><h4> </h4></figcaption>
    </figure>
{{< /gallery >}}


- ### The Drone

    The core mechanic we introduced to innovate on the climbing loop is the repurposed cargo drone. It bridges the gap between a mobile companion and a dynamic anchor, operating across three distinct states:

    - IDLE Mode: While the player is climbing normally, the drone follows passively, being pulled along smoothly by the physical tension of the rope.

    - FALLING Mode: The moment the player falls, the drone instantly locks its position in mid-air, acting as a mobile, floating piton. However, because it cannot fully support the protagonist’s weight in this high-density atmosphere, it steadily loses altitude. While suspended, the player can climb up or down the rope and use momentum to swing across gaps.

    - CONTROLLED Mode: When grounded, the player can manually pilot the drone to reposition it. This allows the player to fly the drone over obstacles or high ledges, lock it into place, and then use it as a custom anchor point to swing across otherwise impassable terrain.

    *Note : All Drone movements are physic based.*

{{< gallery >}}
    <figure class="grid-w33">
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="Gameplay/Jusantdrone1.mp4" type="video/mp4">
        </video>
        <figcaption><h4> </h4></figcaption>
    </figure>
    <figure class="grid-w33">
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="Gameplay/Jusantdrone2.mp4" type="video/mp4">
        </video>
        <figcaption><h4> </h4></figcaption>
    </figure>
    <figure class="grid-w33">
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="Gameplay/drone3.mp4" type="video/mp4">
        </video>
        <figcaption><h4> </h4></figcaption>
    </figure>

{{< /gallery >}}

<!--
### <h2><i>Level Design</i></h2>
-->


## <h1>ART</h1>

{{< gallery >}}
    {{< figure src="img/1.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/3.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/4.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/5.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/6.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/7.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/8.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}} 


### <h2><i>Cinematics</i></h2>

A ubiquitous element in Jusant is the short cinematic sequences found at various moments throughout the adventure. We reproduced two of these cinematics in our project.


- Intro cinematic :

{{< gallery >}}
    <figure class="grid-w80 decal-droite">
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="Gameplay/cine1.mp4" type="video/mp4">
        </video>
        <figcaption><h4> </h4></figcaption>
    </figure>
{{< /gallery >}}


- Outro cinematic :

{{< gallery >}}
    <figure class="grid-w80 decal-droite">
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="Gameplay/cine2.mp4" type="video/mp4">
        </video>
        <figcaption><h4> </h4></figcaption>
    </figure>
{{< /gallery >}}