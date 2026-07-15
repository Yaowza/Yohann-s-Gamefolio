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

_________________________________________

## <b>My Part of the Work</b>

I am one of the two <b>original creators</b> of this project. A friend and I came up with the concept back in September. We wanted to break away from the walking simulator loop that dominates most student games, so we designed a <b>gameplay-focused</b> game featuring a rolling main character!

As one of the two <b>main gameplay programmers</b> in Unreal Engine, I co-developed :
- The <b>core gameplay loops</b> and mechanics including :
    - Player's movement and physics
    - Meteor Strike ability
    - Combat system
    - Moss system
    - A bit of the dialogue system
- All the Levels Mechanics :
    - Boosters
    - Cannons
    - Tubes adn rails (made with spline meshes) 
    - The "Cannon Lighthouse"
- And some other systems in the levels such as :
    - The Railed camera system
    - The checkpoint, death and revive systems
    - And some "Secrets"


I aslo worked on <b>the sytem design</b>.
- The Amount of moss quantity per level, or given by ennemies
- Ennemies and player damages
- Movement speed and gravity

I heavily worked on the **Level Desing** from start to end of the project.

While I contributed to <b>every level</b>, I focused mostly on :
- The Hub
- The cave section in the "Shrooms" level
- The "Ruins" level 
- The Boss fight

I also made some <b>VFX</b>. (a personnal passion of mine)

And in the end I worked on a Steam Deck port, including performance optimisation.

_________________________________________
## <h1><b>Gameplay</b></h1>

 {{< youtubeLite id="5bzi0w5omNY" label="Pierre Qui Roule Gameplay Video" >}}


The movements of the characters are all physic based, wich allows us a nice boulder physics feeling.

### Mechanics


The main gameplay mechanics are simple, you can <b>roll</b>, <b>jump</b> and jump again in the air to do a <b>"meteor strike"</b> (a down dash).

{{< gallery >}}
        <figure class="grid-w33">
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="Gameplay/rolling.mp4" type="video/mp4">
            </video>
            <figcaption><b>Rolling</b></figcaption>
        </figure>
        <figure class="grid-w33">
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="Gameplay/jump.mp4" type="video/mp4">
            </video>
            <figcaption><b>Jumping</b></figcaption>
        </figure>
        <figure class="grid-w33">
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="Gameplay/meteor.mp4" type="video/mp4">
            </video>
            <figcaption><b>Meteor Strike</b></figcaption>
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
            <figcaption><b>Fighting</b></figcaption>
        </figure>
    {{< /gallery >}}

    <div style="height: 30px;"></div>

That's all for the Character's mechanics. We wanted simple and player gameplay to make the game more accessible as the player already have a new "movement" mechanic to learn. 
Our goal was to let the gameplay breathe and avoid overloading the player with mechanics.

Consequently, the majority of the game's mechanical depth and variety is driven directly by the level design
_________________________________________
## <h2><b>Level Design</b></h2>

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
    <figcaption><b> </b></figcaption>
</figure>
{{< /gallery >}}

This level is designed in a way that the player easely finds the main point of interrest that is the Cannon Lighthouse. However it is vast enough to let the player move around, explore and find Secrets.

#### Hub top view :

{{< gallery >}}
{{< figure src="Hub/HubTopView.png" alt="Gallery image 1" figureClass="grid-w80" >}}
{{< /gallery >}}

<!--
    - #### Hub Highlight :

    {{< gallery >}}
        <figure class="grid-w100">
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="Hub/Hubhg.mp4" type="video/mp4">
            </video>
            <figcaption><b>Hub Peak</b></figcaption>
        </figure>
    {{< /gallery >}}

Expliquer ce que c'est :

-->

<div style="height: 30px;"></div>


- ### The Level "Shrooms" :
    {{< gallery >}}
        {{< figure src="Shrooms/shroom1.jpeg" alt="Gallery image 1" figureClass="grid-w80" >}}
    {{< /gallery >}}

This is the first level of the vertical slice. It allows the player to experience platforming with our unique movement style. This level introduces moss harvesting and combat, along with two new mechanics :

- Boosters : They grant a temporary, Mario Kart-style speed boost.

- Meteor Strike : They serves here as both a platforming and combat tool.

{{< gallery >}}
<figure class="grid-w50">
    <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
    <source src="Gameplay/booster.mp4" type="video/mp4">
    </video>
    <figcaption><b>Boosters</b></figcaption>
</figure>
<figure class="grid-w50">
    <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
    <source src="Gameplay/meteorparkour.mp4" type="video/mp4">
    </video>
    <figcaption><b>Meteor Strike Platforming</b></figcaption>
</figure>
{{< /gallery >}}

It also features a railed camera system during a 2D segment. This level has a fairly slow pace to allow players to easily get a feel for the game.

The pacing of this level is mostly slow to let the player learn the mecanics at his own rythm. 


<!--
    - #### Level Shrooms highlights :

{{< gallery >}}
    <figure class="grid-w100">
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="Shrooms/boosterss.mp4" type="video/mp4">
        </video>
        <figcaption><b>Boosters road</b></figcaption>
    </figure>
{{< /gallery >}}

<div style="height: 70px;"></div>

{{< gallery >}}
    <figure class="grid-w100">
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="Shrooms/village.mp4" type="video/mp4">
        </video>
        <figcaption><b>Village of Pierrequiroule</b></figcaption>
    </figure>
{{< /gallery >}}

Expliquer ce que c'est :

-->
<div style="height: 70px;"></div> 


- ### The Level "Ruins" :
    {{< gallery >}}
        {{< figure src="Ruins/ruin1.jpeg" alt="Gallery image 1" figureClass="grid-w80" >}}
    {{< /gallery >}}

This is the final level of our vertical slice. It is longer than the others and culminates in a boss fight. While it reuses previously learned mechanics, the level is much more linear and stretched out, allowing the player to build up massive speed on straightaways packed with boosters. This level also introduces two new mechanics:

- Cannons : Once inside, they automatically launch the player in the direction they are facing after a short delay.

- Pipes : They act as ramps and slides.

{{< gallery >}}
<figure class="grid-w50">
    <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
    <source src="Gameplay/tub.mp4" type="video/mp4">
    </video>
    <figcaption><b>Tubes</b></figcaption>
</figure>
<figure class="grid-w50">
    <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
    <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
    <source src="Gameplay/cannon.mp4" type="video/mp4">
    </video>
    <figcaption><b>Cannon</b></figcaption>
</figure>

{{< /gallery >}}


The pacing of this level is much more energetic, driven entirely by a rhythm of boosters and speed bursts. 

<!--
    - #### Level Ruins highlights :



    {{< gallery >}}
        <figure class="grid-w100">
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="Ruins/ruinfight.mp4" type="video/mp4">
            </video>
            <figcaption><b>Tower Fight</b></figcaption>
        </figure>
    {{< /gallery >}}
    <div style="height: 70px;"></div>
    {{< gallery >}}
        <figure class="grid-w100">
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="Ruins/ruinplanes.mp4" type="video/mp4">
            </video>
            <figcaption><b>Last Cannons</b></figcaption>
        </figure>
    {{< /gallery >}}



Expliquer ce que c'est :

-->

<div style="height: 70px;"></div> 

- ### The Final Boss : 

    {{< gallery >}}
        {{< figure src="boss/boss1.jpeg" alt="Gallery image 1"  figureClass="grid-w80" >}}
    {{< /gallery >}}

To close out the vertical slice, we created a boss fight. The boss is a massive rolling rock located in a unique, half-ruined structure. The fight is split into two major phases:

- Phase 1 : The boss stays in the center of the arena, periodically sending out shockwaves to push the player into the void. Meanwhile, the player must climb up two paths wrapping around the arena to reach a cannon. This cannon launches the player into the air above the boss, allowing them to execute a Meteor Strike to deal damage.

{{< gallery >}}
<figure class="grid-w50">
    <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
    <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
    <source src="boss/bossattack.mp4" type="video/mp4">
    </video>
    <figcaption><b>Boss choc wave</b></figcaption>
</figure>
<figure class="grid-w50">
    <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
    <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
    <source src="boss/phase11.mp4" type="video/mp4">
    </video>
    <figcaption><b>Boss Damage</b></figcaption>
</figure>
{{< /gallery >}}

<div style="height: 20px;"></div> 

- Phase 2 : This phase takes place right below the first area after the player breaks through the floor. It plays out like a classic "Whack-a-Mole" game, where the boss emerges from various molehills. The player must perform a Meteor Strike directly onto its head to deal damage. Repeating this process three times defeats the boss for good. To spice things up, the boss will start using feints after the player lands their first successful hit.

{{< gallery >}}
<figure class="grid-w50">
    <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
    <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
    <source src="boss/phase22.mp4" type="video/mp4">
    </video>
    <figcaption><b>Normal</b></figcaption>
</figure>
<figure class="grid-w50">
    <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
    <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
    <source src="boss/phase21.mp4" type="video/mp4">
    </video>
    <figcaption><b>Finth</b></figcaption>
</figure>
{{< /gallery >}}
 
 <div style="height: 10px;"></div> 

- ### Secrets :
Hidden throughout the levels are jokes and mini-games. Discovering these secrets rewards the player with achievements, which can be tracked on the 'Stickers' page in the pause menu.

{{< gallery >}}
    {{< figure src="secrets/secrets.png" alt="Gallery image 2" caption="<b>Stickers Menu</b>" figureClass="grid-w75" >}}
        <figure class="grid-w33">
            <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="vfx/trounoirpqr.mp4" type="video/mp4">
            </video>
            <figcaption><b>Black Hole Secret</b></figcaption>
        </figure>
        <figure class="grid-w33">
            <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="secrets/dunk.mp4" type="video/mp4">
            </video>
            <figcaption><b>Basket Secret</b></figcaption>
        </figure>
        <figure class="grid-w33">
            <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
            <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
            <source src="secrets/billard.mp4" type="video/mp4">
            </video>
            <figcaption><b>Billard secret</b></figcaption>
        </figure>                    
{{< /gallery >}}

_________________________________________
## <h2><b>UX</b></h2>

To give more feeling and to make the world more alive, we implemented inecrations within the environement. We have :
- Mushrooms :


{{< gallery >}}
<figure class="grid-w33">
    <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
    <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
    <source src="ux/sh0.mp4" type="video/mp4">
    </video>
    <figcaption><b>Boing Shroom</b></figcaption>
</figure>
<figure class="grid-w33">
    <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
    <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
    <source src="ux/sh1.mp4" type="video/mp4">
    </video>
    <figcaption><b>Splat Shroom</b></figcaption>
</figure>
<figure class="grid-w33">
    <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
    <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
    <source src="ux/sh.mp4" type="video/mp4">
    </video>
    <figcaption><b>Puff Shrooms</b></figcaption>
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
    <figcaption><b>Small Fences</b></figcaption>
</figure>
<figure class="grid-w50">
    <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
    <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
    <source src="ux/pl.mp4" type="video/mp4">
    </video>
    <figcaption><b>Bigger Barriers</b></figcaption>
</figure>
{{< /gallery >}}

<!--
_________________________________________
## <h1><b>Environment</b></h1>

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
-->
_________________________________________
## <h2><b>VFX</b></h2>

Here are the VFX I worked on for Pierre Qui Roule.

{{< gallery >}}
    <figure class="grid-w50">
        <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="Gameplay/meteor.mp4" type="video/mp4">
        </video>
        <figcaption><b>Meteor Strike</b></figcaption>
    </figure>
    <figure class="grid-w50">
        <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="vfx/boss.mp4" type="video/mp4">
        </video>
        <figcaption><b>Boss Attack</b></figcaption>
    </figure>
{{< /gallery >}}

###   

{{< gallery >}}
    <figure class="grid-w50">
        <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="vfx/thunder.mp4" type="video/mp4">
        </video>
        <figcaption><b>Thunder</b></figcaption>
    </figure>
    <figure class="grid-w50">
        <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="vfx/trail.mp4" type="video/mp4">
        </video>
        <figcaption><b>Basket Secret</b><h4Player Trail</b></figcaption>
    </figure>
{{< /gallery >}}

#

{{< gallery >}}    
    <figure class="grid-w50">
        <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="vfx/trounoirpqr.mp4" type="video/mp4">
        </video>
        <figcaption><b>Basket Secret</b><h4BlackHole Secret</b></figcaption>
    </figure>
    <figure class="grid-w50">
        <!-- Ta vidéo avec la classe personnalisée et l'action au clic -->
        <video loop muted playsinline preload="none" class="zoomable-video" onclick="toggleZoom(this)">
        <source src="secrets/dunk.mp4" type="video/mp4">
        </video>
        <figcaption><b>Basket Secret</b></figcaption>
    </figure>
{{< /gallery >}}

_________________________________________

## <h1><b>Steam Deck ???</b></h1>

Having recently got my hands on a Steam Deck, one of my personal goals was to get PierreQuiRoule running on it. And that’s exactly what I did!

At the very end of the project, I tweaked the game's quality settings to offer better performance and optimization for the Steam Deck. Unfortunately, because we used real-time lighting, the Steam Deck struggled to run the game smoothly. However, by switching the rendering mode for lights and shadows and dropping the graphics to "Low," I managed to make the game playable (even if it’s not the prettiest). Players can even push the settings to "Medium" if they disable foliage, allowing them to enjoy better lighting.

To avoid maintaining two separate builds, I implemented a check at startup that detects the player's screen resolution. Since the Steam Deck's resolution is fairly unique, this is enough for me to automatically apply the necessary graphical settings to keep the game running smoothly.