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

    - *I am responsible for nearly 100% of the scripting and systems implementation within the game's main level.*

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