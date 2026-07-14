---
title: "Tokar Tournament's VFX"
summary: "The Main VFX I made for Tockar Tournament."
categories: ["vfx"]

heroStyle: background

#externalUrl: ""
#showSummary: true
date: 2025-06-25
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







{{< youtubeLite id="3Qs9SjkK5yM" label=" VFX_Black Hole Star Explosion with sound " >}}


These are the main VFX I made for "Tockar Tournament". These are my first VFX using Refraction. For the orbital strike I used an asset pack to help me get the result I wanted. I needed help with the "dissolution" so I dug in premade VFX to understand how it was made and how it worked.



