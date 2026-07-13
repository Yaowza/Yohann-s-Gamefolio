---
title: "LD_Chemical Laboratory"
summary: "This is a Level Design exercise. Based on a theme we had to create a fully playable Level design dressed by the TA."
categories: ["projects","schoolproject"]
#tags: ["projects"]
#externalUrl: ""
#showSummary: true
date: 2025-11-28
draft: false

featureimage: "card.png"   # fond de la page
thumbnail: "cover.png"     # image de la carte

---
<span style="opacity:0">aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa</span>

# Walkthrough

{{< youtubeLite id="r0iDYNpjsJA" label="LD Walkthrough" >}}


## **Whats is the Chemical Laboratory ?**

Developed within a tight one-month timeline alongside two other major concurrent projects, the goal of this assignment was to craft a unique, theme-driven level design with structured gameplay phases.

This project was a highly collaborative, cross-disciplinary effort :

- Game Designers handled the level design layout and core gameplay scripting.

- Environment Artists took charge of dressing the blockout.

- Together, we co-authored the pacing to deliver a logical, cohesive narrative experience throughout the entire walkthrough.


To keep the player engaged, the level layout was strictly structured to alternate between distinct gameplay beats, balancing tension and release :

- Platforming Phases : Traversal challenges utilizing the environment.

- Combat Encounters : Arena setups designed for tactical engagements.

- Boss Fight : A climatic, high-stakes encounter serving as the level's peak.

- Rest Areas : Quiet zones designed for pacing recovery, atmosphere building, and narrative delivery.



Given the extreme time constraints of managing three major projects simultaneously, efficiency was our top priority.

Some early layout schemes and blockouts remained intentionally minimal, and occasionally evolved during the production pipeline. We purposely bypassed heavy detailing in the initial design stages to prioritize a "fail fast, iterate faster" workflow. This agile approach allowed us to quickly playtest the core mechanics, hand off the layout to the art team for dressing, and refine the gameplay loops on the fly.


## **Level Design**

### Introduction

The introduction functions as an environmental narrative prologue. By embedding broken down or active robots and massive fan directly into the starting scenery, it naturally introduces the player to the exact mechanics and visual cues that will serve as the core gameplay components throughout the entire level.

<h3>Pacing</h3>
{{< gallery >}}
    {{< figure src="intro/intropacing.png" alt="Gallery image 1"  figureClass="grid-w100 mon-image-speciale" >}}
{{< /gallery >}} 

<div style="height: 20px;"></div>

<h3>Sketch</h3>
{{< gallery >}}
    {{< figure src="intro/introchema.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

<div style="height: 20px;"></div>

<h3>Bloc-Out</h3>
{{< gallery >}}
    {{< figure src="intro/introblocout.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="intro/introblocout2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

<div style="height: 20px;"></div>

<h3>Dressing up</h3>
{{< gallery >}}
    {{< figure src="intro/introhabille.png" alt="Gallery image 1"  figureClass="grid-w100" >}}
    {{< figure src="intro/introhabille1.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="intro/introhabille2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

<style>
    /* On cible uniquement l'image contenue dans la figure spéciale */
    .mon-image-speciale img {
        /* Exemples de modifications de format : */
        aspect-ratio: 17 / 6 !important; /* Force un format paysage 16:9 */
        object-fit: cover !important;    /* Remplis le cadre proprement sans déformer */
        border-radius: 8px !important;  /* Optionnel : ajoute des bords arrondis */
    }
</style>

_____________________________________________________________

### C1 : First Combat

Immediately after turning a corner, the player experiences their first active combat encounter.

- The Setup : A single robot activates directly in front of the player upon sight, serving as an immediate threat. Behind it, three additional robots are positioned behind a massive, slowly rotating fan.

- The Hazard : The fan acts as a dynamic line-of-sight obstacle, preventing the player from easily targeting the enemies behind it. To survive this crossfire, a strategic piece of cover is placed on the player’s left.

- Design Intent & Layering : This encounter introduces the core cover-to-cover shooting mechanics. By layering the slow-moving fan on top of standard cover layouts, the design forces the player to manage tactical timing and precise aiming under pressure, naturally ramping up the difficulty.


<h3>Pacing</h3>
{{< gallery >}}
    {{< figure src="c1/schema.png" alt="Gallery image 1"  figureClass="grid-w100 mon-image-speciale2" >}}
{{< /gallery >}} 

*As the first combat encounter of the level, the intensity is kept at a moderate level. It functions as an organic tutorial, teaching the player enemy behavior, shooting mechanics, and target prioritization without overwhelming them.*


<div style="height: 20px;"></div>

<h3>Sketch</h3>
{{< gallery >}}
    {{< figure src="c1/pathing.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}


<div style="height: 20px;"></div>

<h3>Bloc-Out</h3>
{{< gallery >}}
    {{< figure src="c1/blocout1.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="c1/blocout2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

<div style="height: 20px;"></div>

<h3>Dressing up</h3>
{{< gallery >}}
    {{< figure src="c1/habillage1.png" alt="Gallery image 1"  figureClass="grid-w100" >}}
    {{< figure src="c1/habillage2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="c1/habillage3.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

<style>
    /* On cible uniquement l'image contenue dans la figure spéciale */
    .mon-image-speciale2 img {
        /* Exemples de modifications de format : */
        aspect-ratio: 25 / 8 !important; /* Force un format paysage 16:9 */
        object-fit: cover !important;    /* Remplis le cadre proprement sans déformer */
        border-radius: 8px !important;  /* Optionnel : ajoute des bords arrondis */
    }
</style>

_____________________________________________________________

### P1 : First Platforming

This first platforming phase focuses on spatial navigation, challenging the player to find their way through a sequence of distinct micro-objectives designed around environmental puzzle-solving.

- Step 1 : The player is immediately confronted with a blocked main archway. This forces them to pivot and navigate through a mini-labyrinth to find an alternative exit.

- Step 2 : Upon entering the subterranean area, the structural exit is once again obstructed. However, strategic environmental lighting is used to draw the player's eye toward what appears to be the true exit. The player is naturally guided forward, only to realize upon closer inspection that this path is a dead end as well.

- Step 3 : Having exhausted the obvious options, the player must shift their focus to deduce the final, correct path which is intentionally concealed within the shadows, rewarding careful observation and environmental awareness.
 

<h3>Pacing</h3>
{{< gallery >}}
    {{< figure src="p1/p1pacing.png" alt="Gallery image 1"  figureClass="grid-w100 mon-image-speciale2" >}}
{{< /gallery >}} 

*Since this gameplay phase immediately follows a combat encounter, a small spiral staircase is placed just before the platforming section allowing the player to rest a litle before the next challenge.*


<div style="height: 20px;"></div>

<h3>Sketch</h3>
{{< gallery >}}
    {{< figure src="p1/p1chema.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}


<div style="height: 20px;"></div>

<h3>Bloc-Out</h3>
{{< gallery >}}
    {{< figure src="p1/p1blc.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="p1/p1blc2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="p1/p1blc3.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

<div style="height: 20px;"></div>

<h3>Dressing up</h3>
{{< gallery >}}
    {{< figure src="p1/p1habille.png" alt="Gallery image 1"  figureClass="grid-w100" >}}
    {{< figure src="p1/p1habille1.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="p1/p1habille2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

_____________________________________________________________


### R1 : First Rest

Positioned strategically after two consecutive action-heavy phases, this rest area is designed to lower the player's tention. It serves as a calm before the storm, preparing them mentally for the upcoming cinematic encounter and the high-stakes boss battle right after.

During this quiet traversal, the player walks directly above the massive industrial fans they previously observed from a distance. They then descend into a gigantic ventilation shaft via a series of ladders.

Unlike the first fan encountered earlier in the level, the player is now in direct physical contact with the machinery. This shifting proximity reinforces the environmental storytelling, grounding the player deeper within the industrial reality of the laboratory.
 

<h3>Pacing</h3>
{{< gallery >}}
    {{< figure src="r1/r1pacing.png" alt="Gallery image 1"  figureClass="grid-w100 mon-image-speciale2" >}}
{{< /gallery >}} 


<div style="height: 20px;"></div>

<h3>Sketch</h3>
{{< gallery >}}
    {{< figure src="r1/r1chema.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}


<div style="height: 20px;"></div>

<h3>Bloc-Out</h3>
{{< gallery >}}
    {{< figure src="r1/r1blc.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="r1/r1blc2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="r1/r1blc1.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

<div style="height: 20px;"></div>

<h3>Dressing up</h3>
{{< gallery >}}
    {{< figure src="r1/r1habille.png" alt="Gallery image 1"  figureClass="grid-w100" >}}
    {{< figure src="r1/r1habille1.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="r1/r1habille2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

_____________________________________________________________


### C2 : Second Combat

The encounter opens with a strategic light source that deliberately misguides the player down the wrong path. This brief misdirection subtly extends the previous rest phase while playfully testing the player's instincts.

Shortly after, the player reaches a glass window overlooking a room. From this safe vantage point, they can safely observe unaware enemies and a large, exposed power battery.

Using the doorway frame as tactical cover, the player engages the targets. This fight introduces a major mechanical twist designed to catch the player off guard: for the first time, enemies actively use cover, either by prone-positioning (lying down) or taking angles behind walls.

Eliminating the enemy closest to the power battery triggers a scripted chain reaction. The battery explodes, instantly plunging the facility into darkness, activating emergency alarms, and initiating the laboratory’s self-destruction sequence.

From this structural turning point onward, dynamic screenshakes and falling ceiling debris occur at randomized intervals. These systemic feedback loops constantly remind the player that the laboratory is actively collapsing around them, ramping up the tension before the upcoming boss fight.

 

<h3>Pacing</h3>
{{< gallery >}}
    {{< figure src="c2/c2pacing.png" alt="Gallery image 1"  figureClass="grid-w100 mon-image-speciale2" >}}
{{< /gallery >}} 

*Mechanically, the combat intensity here is kept relatively low. The design priority is shifted toward onboarding the player with the new enemy cover mechanic, while ensuring the scripted sequence delivers maximum narrative impact.*



<div style="height: 20px;"></div>

<h3>Sketch</h3>
{{< gallery >}}
    {{< figure src="c2/c2chema.png" alt="Gallery image 1"  figureClass="grid-w50 mon-image-chema" >}}
{{< /gallery >}}

<style>
    /* On cible uniquement l'image contenue dans la figure spéciale */
    .mon-image-chema img {
        /* Exemples de modifications de format : */
        aspect-ratio: 15 / 16 !important; /* Force un format paysage 16:9 */
        object-fit: cover !important;    /* Remplis le cadre proprement sans déformer */
        border-radius: 8px !important;  /* Optionnel : ajoute des bords arrondis */
    }
</style>


<div style="height: 20px;"></div>

<h3>Bloc-Out</h3>
{{< gallery >}}
    {{< figure src="c2/c2blc.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="c2/c2blc1.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="c2/c2blc2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

<div style="height: 20px;"></div>

<h3>Dressing up</h3>
{{< gallery >}}
    {{< figure src="c2/c2habille.png" alt="Gallery image 1"  figureClass="grid-w100" >}}
    {{< figure src="c2/c2habille1.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="c2/c2habille2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="c2/c2habille3.png" alt="Gallery image 1"  figureClass="grid-w100" >}}
{{< /gallery >}}

_____________________________________________________________

### B1 : First Boss

Immediately following the self-destruction trigger, the player enters a brief transition zone. This space serves as a momentary gameplay breather while reinforcing the narrative weight of the facility's collapse. Upon entering the chamber, the architectural layout, high-contrast framing, and precise placement of the entry point instantly establish clear affordance—allowing the player to naturally read the entire room, identify the final exit, and map out their path forward at a single glance.

Once the path is understood, the player is thrown into a high-intensity platforming challenge focused on rotating platforms suspended over a hazardous acid vat. The intensity and mechanical demands scale progressively across three distinct phases :

- Phase 1 : The player encounters the first rotating platform positioned flush with the solid ground (no gap). This introductory step isolates the core mechanic, requiring the player to simply read the rotation speed and walk forward at the exact right moment.

- Phase 2 : The challenge introduces a new layer of friction. The player must successfully time their movement to jump across an empty gap from one stable platform onto another spinning platform, combining physics tracking with active jump execution.

- Phase 3 : The final stretch demands a shift in spatial awareness. Instead of a long horizontal jump, the player must execute a vertical leap to reach a rotating platform positioned high above them. From this ultimate high point, they must time one last precise jump to return to safe, solid ground and escape the collapsing chamber.
 

<h3>Pacing</h3>
{{< gallery >}}
    {{< figure src="b1/b1pacing.png" alt="Gallery image 1"  figureClass="grid-w100 mon-image-speciale2" >}}
{{< /gallery >}} 


<div style="height: 20px;"></div>

<h3>Sketch</h3>
{{< gallery >}}
    {{< figure src="b1/b1chema.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}


<div style="height: 20px;"></div>

<h3>Bloc-Out</h3>
{{< gallery >}}
    {{< figure src="b1/b1blc.png" alt="Gallery image 1"  figureClass="grid-w100" >}}
{{< /gallery >}}

<div style="height: 20px;"></div>

<h3>Dressing up</h3>
{{< gallery >}}
    {{< figure src="b1/b1habille.png" alt="Gallery image 1"  figureClass="grid-w100" >}}
    {{< figure src="b1/b1habille1.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="b1/b1habille2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

_____________________________________________________________

### R2 : Second Rest

Positioned right after an exhausting boss fight, this long rest area delivers immediate psychological relief. The player enters by sliding down a massive broken pipe, an unexpected, playful movement cue that signals: "The threat is over; you can finally breathe."

The slide ejects the player into a colossal, cinematic chamber filled with ruptured industrial pipes spewing burning acid, showcasing the true scale of the facility's destruction.

Turning the background architecture into a slide bridges the gap between gameplay and worldbuilding, anchoring the player's relief directly within the collapsing environment.
 

<h3>Pacing</h3>
{{< gallery >}}
    {{< figure src="r2/r2pacing.png" alt="Gallery image 1"  figureClass="grid-w100 mon-image-speciale2" >}}
{{< /gallery >}} 

A long decompression zone with very low intensity following the grueling boss fight to fully reset the player's adrenaline.

<div style="height: 20px;"></div>

<h3>Sketch</h3>
{{< gallery >}}
    {{< figure src="r2/r2chema.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}


<div style="height: 20px;"></div>

<h3>Bloc-Out</h3>
{{< gallery >}}
    {{< figure src="r2/r2blc.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="r2/r2blc1.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

<div style="height: 20px;"></div>

<h3>Dressing up</h3>
{{< gallery >}}
    {{< figure src="r2/r2habille.png" alt="Gallery image 1"  figureClass="grid-w100" >}}
    {{< figure src="r2/r2habille1.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="r2/r2habille2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

_____________________________________________________________

### C3 : Third Combat

A brief platforming sequence that requires the player to navigate beneath their target platform, smoothly transitioning from the previous rest area into a new chamber.

A micro-encounter testing the player's accuracy against a distant, semi-sheltered enemy. A protective metal grate allows the player to safely scout the arena and line up their shot before engaging.

A surprise attack from a hidden enemy around a blind corner. Positioned directly on a rotating fan, this enemy spins while firing, introducing a unique dynamic target and a fresh combat challenge.

 

<h3>Pacing</h3>
{{< gallery >}}
    {{< figure src="c3/c3pacing.png" alt="Gallery image 1"  figureClass="grid-w100 mon-image-speciale2" >}}
{{< /gallery >}} 


<div style="height: 20px;"></div>

<h3>Sketch</h3>
{{< gallery >}}
    {{< figure src="c3/c3chema.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}


<div style="height: 20px;"></div>

<h3>Bloc-Out</h3>
{{< gallery >}}
    {{< figure src="c3/c3blc.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="c3/c3blc1.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="c3/c3blc2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

<div style="height: 20px;"></div>

<h3>Dressing up</h3>
{{< gallery >}}
    {{< figure src="c3/c3habille3.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="c3/c3habille1.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="c3/c3habille.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="c3/c3habille2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

_____________________________________________________________

### P2 : Second Platforming

A final platforming sequence using new acid pools created by the facility's destruction, scaling in difficulty across four steps:

- Basic Slalom: Introductory dodging through small, easily avoidable acid puddles.

- Narrow Passage: A tight corridor reducing the player's margin for error, requiring precise movement control.

- The Leap: A wide pool blocking the entire corridor width, forcing the player to execute a well-timed jump.

The player uses a debris mound to reach a narrow overhead pipe to cross a massive acid flood. The final challenge requires navigating a sharp 90-degree turn on this thin surface to reach safety.

 

<h3>Pacing</h3>
{{< gallery >}}
    {{< figure src="p2/p2pacing.png" alt="Gallery image 1"  figureClass="grid-w100 mon-image-speciale2" >}}
{{< /gallery >}} 

<div style="height: 20px;"></div>

<h3>Sketch</h3>
{{< gallery >}}
    {{< figure src="p2/p2chema.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}


<div style="height: 20px;"></div>

<h3>Bloc-Out</h3>
{{< gallery >}}
    {{< figure src="p2/p2blc.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="p2/p2blc1.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="p2/p2blc2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

<div style="height: 20px;"></div>

<h3>Dressing up</h3>
{{< gallery >}}
    {{< figure src="p2/p2habille1.png" alt="Gallery image 1"  figureClass="grid-w100" >}}
    {{< figure src="p2/p2habille.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="p2/p2habille2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}


_____________________________________________________________

### R3 : Third Rest

 Right before confronting the final boss, the player reaches a large window framing a cinematic "wow" moment : a massive, synchronized army of newly activated robots marching together. 
 
 This striking visual instills immediate psychological tension, confronting the player with an overwhelming force they cannot fight head-on. 

 Narratively, this scene communicates critical urgency : the entire laboratory is now online and hostile, raising the stakes and making it clear that immediate escape is the only option.

<h3>Pacing</h3>
{{< gallery >}}
    {{< figure src="r3/r3pacing.png" alt="Gallery image 1"  figureClass="grid-w100 mon-image-speciale2" >}}
{{< /gallery >}} 

<div style="height: 20px;"></div>

<h3>Sketch</h3>
{{< gallery >}}
    {{< figure src="r3/r3chema.png" alt="Gallery image 1"  figureClass="grid-w50 mon-image-chema" >}}
{{< /gallery >}}


<div style="height: 20px;"></div>

<h3>Bloc-Out</h3>
{{< gallery >}}
    {{< figure src="r3/r3blc.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="r3/r3blc1.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="r3/r3blc2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="r3/r3blc3.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

<div style="height: 20px;"></div>

<h3>Dressing up</h3>
{{< gallery >}}
    {{< figure src="r3/r3habille1.png" alt="Gallery image 1"  figureClass="grid-w100" >}}
    {{< figure src="r3/r3habille.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="r3/r3habille2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

_____________________________________________________________

### B2 : Second and Last Boss


The final boss encounter concludes the Chemical Laboratory narrative arc through a 3-phase escalation designed to build variety and tension, ending with a scripted cinematic escape. The entire arena is plunged into darkness, lit only by emergency red lights to amplify the psychological dread.

- Phase 1 : The encounter opens with a transitional skirmish where the player must eliminate three enemies, including one strategically hidden in a blind spot to the right, forcing the player to check their corners.

- Phase 2 : The player navigates through dense rows of deactivated robots. As they move, specific units suddenly spark to life and ambush them. Survival relies on visual scanning to distinguish active threats from dormant props.

- Phase 3 : Multiple robots activate simultaneously to unleash heavy firing squads. The player must use environmental walls as cover to survive the salvos. After each volley, the active threats blend back into the deactivated crowd, requiring the player to master the timing between defensive cover and offensive counter-attacks.



Upon completing Phase 3, the player rushes toward the exit door, only for it to slam shut right in front of them. Trapped, the remaining units of the robotic army begin waking up one by one. With nowhere left to run, the player is forced to take cover behind one of the final two barriers, facing certain death.

Just as the threats close in, a scripted ceiling collapse crushes the robotic forces. The resulting blast forces the exit door back open, allowing the player to finally escape the collapsing laboratory.

 

<h3>Pacing</h3>
{{< gallery >}}
    {{< figure src="b2/b2pacing.png" alt="Gallery image 1"  figureClass="grid-w100 mon-image-speciale2" >}}
{{< /gallery >}} 

*Following these three phases and the final cinematic climax, this boss fight peaks at a very high mechanical and emotional intensity. Every system from the frantic cover usage to the claustrophobic lighting is pushed to its absolute limit, leaving a powerful, lasting impression on the player as they conclude their journey through the Chemical Laboratory.*

<div style="height: 20px;"></div>

<h3>Sketch</h3>
{{< gallery >}}
    {{< figure src="b2/b2chema.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}


<div style="height: 20px;"></div>

<h3>Bloc-Out</h3>
{{< gallery >}}
    {{< figure src="b2/b2blc.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="b2/b2blc1.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="b2/b2blc2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="b2/b2blc3.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

<div style="height: 20px;"></div>

<h3>Dressing up</h3>
{{< gallery >}}
    {{< figure src="b2/b2habille1.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="b2/b2habille2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="b2/b2habille3.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="b2/b2habille.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="b2/b2habille4.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="b2/b2habille5.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}