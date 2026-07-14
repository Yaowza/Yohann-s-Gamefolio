---
title: "Save System"
summary: "This was a small Narrative project where we had to create a understandable scene with a maximum of environemental storytelling as possible and without any dialogs."
categories: ["projects","schoolproject"]
#tags: ["projects"]


#externalUrl: ""
#showSummary: true
date: 2025-06-01
draft: false
featureimage: "card.png"   # fond de la page
thumbnail: "cover.png"     # image de la carte


---

_________________________________________


<div class="video-centree">
    {{< youtubeLite id="kUncNskrx6o" label="Save System" >}}
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
  <a href="https://kdrive.infomaniak.com/app/share/1711732/2113df97-2318-4534-8912-be5a36b974e3" class="btn-itch">
    Download the latest Build
  </a>
</div>


<div style="height: 20px;"></div> 


## What is Save System ?


This project focuses entirely on environmental storytelling.

The brief was to create a short experience without any dialogue or upfront explanations in one month. Through pure exploration, the player must deduce who they are, understand where they are, and figure out their ultimate objective. To focus heavily on the design and narrative, we utilized pre-existing environment asset packs. And composed our environement with them. 

- **Interactive Screen System & UX**

    One of the core features of the game is the interactive screens. I invested a lot of effort into polish and game feel to ensure a seamless user interaction.

    - World-to-2D Projection : By utilizing a precise raycast on the screen, I accurately mapped and translated 3D world space coordinates into a 2D interface position, allowing the player to interact directly with the monitors.

    - Diegetic UI : The user interface was meticulously crafted to act as a primary pillar of the environmental narrative, guiding the player implicitly without breaking immersion.

    - Drone Movement : Character movement is designed to be highly fluid, utilizing smooth acceleration and deceleration curves to reinforce the weightless, mechanical feel of the drone.

### Concept & Narrative Background :

The player is plunged into an imminent danger simulation aboard an inter-spatial "Orient Express" like transport vessel.

In reality, the playable character is an advanced tactical drone engineered specifically to intervene during catastrophic emergencies. Equipped with an adaptive AI, the drone is designed to learn from every single mistake, constantly recalculating to find the optimal solution to resolve the crisis.

When a fatal threat endangers the ship, an emergency "Save System" triggers. This activates a localized black hole generator that drastically slows down atomic movement within a perimeter around the vessel, effectively freezing the destruction process in place.

Operating at near-instantaneous processing speeds, the drone moves freely through this dilated timeline to fix the ship. If the drone fails and the ship is destroyed, the black hole collapses, creating a localized time loop. It transmits all gathered analytical data back to the drone's past self, allowing a new loop to begin with accumulated knowledge.

### Level Design Structure :

The level layout is strategically divided into three distinct areas:

- The Main Cabin (The Car) : The primary gameplay area, designed to simulate a space train car.

- The Generator Room : Located at the far end of the cabin, this room houses the black hole generator and an interactive control tablet.

- The Control Room : Positioned directly above the main cabin, this area contains the master tablet used to pilot the ship. It is accessed via a ceiling hatch located near the windows at the back of the car.

{{< gallery >}}
    {{< figure src="img/1.png" alt="Gallery image 1"  figureClass="grid-w100" >}}
    {{< figure src="img/2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/3.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/4.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/5.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/6.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/7.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}} 

