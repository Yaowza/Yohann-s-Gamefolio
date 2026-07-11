---
title: "Kokoro Renzu"
summary: "Kokoro Renzu is an open world card playing game. The player has to explore and take photos to create his own deck and beath the elders of the village."
categories: ["projects","schoolproject"]
#tags: ["projects"]
#externalUrl: ""
#showSummary: true
date: 2024-07-20
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
  function toggleZoom(video) {
    const overlay = document.getElementById('videoOverlay');
    
    if (!video.classList.contains('is-zoomed')) {
      // 1. Taille et position initiales de la vidéo
      const first = video.getBoundingClientRect();
      
      video.classList.add('is-zoomed');
      overlay.classList.add('is-active');
      
      // 2. Calcul du centre de l'écran
      const centerX = window.innerWidth / 2;
      const centerY = window.innerHeight / 2;
      
      const videoCenterX = first.left + first.width / 2;
      const videoCenterY = first.top + first.height / 2;
      
      const moveX = centerX - videoCenterX;
      const moveY = centerY - videoCenterY;
      
      // 3. LE CALCUL MAGIQUE POUR LA TAILLE UNIQUE :
      // On veut que la vidéo zoomée occupe 70% de la largeur de la fenêtre (0.7).
      // Tu peux changer 0.7 par 0.8 (80%) ou 0.6 (60%) selon tes préférences.
      const targetWidth = window.innerWidth * 0.5;
      const dynamicScale = targetWidth / first.width; 
      
      // On applique le déplacement et le scale sur-mesure
      video.style.transform = `translate(${moveX}px, ${moveY}px) scale(${dynamicScale})`;
    } else {
      video.style.transform = '';
      overlay.classList.remove('is-active');
      
      setTimeout(() => {
        video.classList.remove('is-zoomed');
      }, 400);
    }
  }

  function closeVideo() {
    const zoomedVideo = document.querySelector('.zoomable-video.is-zoomed');
    if (zoomedVideo) toggleZoom(zoomedVideo);
  }
</script>



<span style="opacity:0">aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa</span>
_________________________________________

# Trailer :

<div class="video-centree">
    {{< youtubeLite id="rms6F75WQrE" label="Kokoro Renzu Trailer" >}}
</div>

<style>
  .video-centree > * {
    margin: 0 auto !important;
    display: block !important;
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
  <a href="https://drive.google.com/file/d/1TxXzb2zME_FFTUX7PossWxn1eNBuzbjb/view" class="btn-itch">
    Download the last Build !
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
  {{< keyword >}} Mouse and Keyboard only ! {{< /keyword >}}
</div>

<div style="height: 10px;"></div>

<style>
  .mon-keyword2 * {
    background-color: #ec792b !important; /* Couleur de fond */
    color: #ffffff !important;            /* Couleur de texte */
    border-radius: 8px !important;        /* Arrondit les bords (ex: 8px ou 9999px pour un effet pilule) */
  }
</style>

<div class="flex justify-center mon-keyword2">
  {{< keyword >}} Controller is only for debug {{< /keyword >}}
</div>




## What is Kokoro Renzu ?
Kokoro Renzu takes place on the Japanese fictional island of Kokoro during the Edo period.

The game mixes third person exploration and card game. 

On this mystical island, everything you take a picture of with your edo-steampunk Polaroid will be transformed into a playing card.

# Gameplay Video :

 {{< youtubeLite id="m0P7ABK71vA" label="Kokoro Gameplay Video" >}}

## My Roles on this project :

We where a team of 13 students working on Kokoro Renzu (5 Game Artists, 4 Tech Artists, and 4 Game Designers). As the Lead Tech, I also serve as one of the 2 gameplay programmers for the project.

- **Lead Tech & Version Control**

    Repository Management : I was responsible for the GitHub management, including repository setup, branching strategies, conflict resolution, and important merge management. I also taught the Tech Artists how to use github to pull, push and merge branches.

- **Gameplay Programming**

    - *Note: Responsible for nearly 100% of the scripting and systems implementation within the game's main level.*

    - Core Systems : Developed the 3Cs (Character, Camera, Controls with full controller support), the save/load system, and the inventory.

    - Photo Camera & Card Mechanics : Scripted the core photography mechanic, including the dynamic creation, invocation, and special traits of the resulting cards.

    - World & Exploration : Implemented the Day/Night cycle, dynamic weather, exploration mechanics, interactable props, environmental puzzles, and wild animals.

    - Narrative Tools : Built the cinematic introduction and the dialogue system from scratch.

- **Game & Level Design**

    - System & Mechanics Design : Designed the core gameplay loops, camera-to-card mechanics, Toris (serving as respawn, save, and fast-travel points), and established the master sound lists.

    - Level Design & World Layout : Sculpted the island's landscape, including the layout of distinct locations, caves, rivers, and paths, while configuring environmental mechanics.

    - Documentation : Authored and maintained Game Design Documents (GDD) and technical specifications.

- **Lore Creation :** Participated in writing the overarching narrative lore and the worldbuilding of Kokoro.

- **VFX Art & Integration :** Designed and implemented all current in-game visual effects to support gameplay feedback and atmosphere.

## Environment :

{{< gallery >}}
    {{< figure src="img/1.png" alt="Gallery image 1"  figureClass="grid-w100" >}}
    {{< figure src="img/2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/3.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/4.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/5.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/6.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/7.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/8.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/9.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/11.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/12.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}} 

## Yokai no Kake :

{{< gallery >}}
    {{< figure src="img/10.png" alt="Gallery image 1"  figureClass="grid-w100" >}}
{{< /gallery >}} 