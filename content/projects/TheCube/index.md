---
title: "The Cube"
summary: "This was a UX based tiny project where we had to create a game that transmitted something philosophical."
categories: ["projects","schoolproject"]
#tags: ["projects"]


#externalUrl: ""
#showSummary: true
date: 2025-06-01
draft: false
featureimage: "card.png"   # fond de la page
thumbnail: "cover.png"     # image de la carte


---
<span style="opacity:0">aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa</span>

<div class="video-centree">
    {{< youtubeLite id="A5o6ORmt3hc" label="The Cube" >}}
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
  <a href="https://kdrive.infomaniak.com/app/share/1711732/037f3bfa-30b9-4641-8ecf-886009a601a7" class="btn-itch">
    Download the latest Build
  </a>
</div>



<div style="height: 20px;"></div> 




## What is The Cube : A useless journey ?

This is a UX-focused mini-game centered around a unique, experimental mechanic. Developped in one month.

Developed as a solo project, the challenge was to build a simple yet fluid experience from scratch, using only a single mechanic that is intentionally ambiguous and hard to understand upon first playthrough. That should represent a "phillosophic" thought.

The objective is to survive and travel as far as possible. Controlling a cube, the player must figure out the correct path through trial and error, relying purely on sensory feedback:

- Correct Path: Each successful forward move triggers a high-pitched audio cue and illuminates the path in blue.

- Incorrect Path: Stepping onto the wrong path triggers a low-pitched audio cue and turns the environment orange.

Players have a limited number of allowed mistakes: each fail progressively dissolves the cube. Once fully dissolved, the cube dies, and it's game over. Additionally, backing up or backtracking is strictly forbidden. Attempting to move backward results in instant death.

In this prochect everything was self made except the sky boxes in space and the ocean that was made using the water plug in from 
unreal.

The path Generation is procedural and self made.

{{< gallery >}}
    {{< figure src="img/2.png" alt="Gallery image 1"  figureClass="grid-w100" >}}
    {{< figure src="img/1.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/3.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/4.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/5.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}} 




