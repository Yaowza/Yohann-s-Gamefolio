---
title: "Stellar Library"
summary: "We had to code in blueprint and then in C++ a procedural tower-library in one month."
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


## What is the Stellar Library ?

This project was focused on mastering procedural generation architectures within Unreal Engine. The objective was to build something fully procedural from scratch. My group chose to make a  "Library Tower".

The core challenge of this project lay in its dual implementation: the entire procedural logic was first prototyped and validated using Unreal Blueprints, and then entirely refactored and optimized into native production-ready C++.

- <h3>Procedural Modular Features</h3>

    The tower's architecture and interior dressing are generated dynamically through interconnected structural and decorative modules:

    - **Structural Layout :**

        - Circular Floor Generation : Algorithmic calculation of the tower’s radius and curvature to spawn repeating, stacked floor levels.

        - Dynamic Wall System : A modular wall generator that procedurally alternates between empty walls, windows, statuary alcoves, and integrated bookshelves based on geometric constraints.

        - Procedural Staircases : Dynamic positioning and alignment of stairs connecting each circular floor seamlessly.

    - **Interior Prop Dressing :**

        - Intelligent Bookshelves : Procedural bookshelves that auto-populate with individual assets.

        - Book Stacks & Rows : Randomization algorithms governing the layout, rotation, and density of book rows and messy book piles to create a lived-in atmosphere.

    - **Decorative & Environmental Details :**

        - Procedural Paintings : Wall art featuring procedurally generated canvas textures/paintings.

        - Lighting & Decor : Dynamic placement of chandeliers and statues to reinforce the gothic, academic atmosphere of the tower.

- <h3>Technical Takeaways & Workflow</h3>

    - **Blueprint Prototyping :** Allowed for fast iteration loops to perfect the mathematical logic behind the circular spawning, spacing constraints, and alternation rules.

    - **C++ Refactoring :** Porting the logic to C++ drastically improved performance during the generation phase, utilizing optimized loops, structure data types, and clean memory management.

    - **Math & Geometry :** Deepened my understanding of trigonometry and vector math required to calculate correct transformations (locations/rotations) along a circular grid layout.

    - **Designer-Friendly Tooling :** To bridge the gap between programming and level design, the entire generation system exposes an extensive set of exposed variables (parameters). A level designer can easily tweak and customize parameters such as tower height, radius, asset density, or the alternation rules of the walls in real-time, offering total creative control over the final shape and mood of the tower without writing a single line of code.

{{< gallery >}}
    {{< figure src="img/8.png" alt="Gallery image 1"  figureClass="grid-w25 mon-image-speciale" >}}
        {{< figure src="img/1.png" alt="Gallery image 1"  figureClass="grid-w75" >}}
{{< /gallery >}}

<div style="height: 20px;"></div>

{{< gallery >}}
    {{< figure src="img/2.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/3.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/4.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/5.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/6.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
    {{< figure src="img/7.png" alt="Gallery image 1"  figureClass="grid-w50" >}}
{{< /gallery >}}

<style>
    /* On cible uniquement l'image contenue dans la figure spéciale */
    .mon-image-speciale img {
        /* Exemples de modifications de format : */
        aspect-ratio: 10 / 17.2 !important; /* Force un format paysage 16:9 */
        object-fit: cover !important;    /* Remplis le cadre proprement sans déformer */
        border-radius: 8px !important;  /* Optionnel : ajoute des bords arrondis */
    }
</style>

