---
title: "Clair Obscurd inspired VFX"
summary: "Some Clair Obscur : Expedition 33 VFX I made for a potential personnal project."
categories: ["vfx"]

heroStyle: background

#externalUrl: ""
#showSummary: true
date: 2025-07-20
draft: false

featureimage: "card.png"  
thumbnail: "card.png"
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



{{< youtubeLite id="ksPjLYkzHdE" label="  Clair Obscur inspired VFX " >}}


I made these vfx after playing Clair Obscur (obviously). These where parts of a small project we made for a week.

<b>Fun fact : </b> it's Clair obscur that made me start using Refraction in all my VFX to add more impact and depth.

