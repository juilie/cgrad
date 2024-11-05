---
layout: default
title: Bio | Calvin Grad
css: "/static/css/bio.css"
---

<div class="bio-container">
  <div class="polaroid">
    <img src="{{ site.data.bio.image }}" alt="Calvin Grad">
    <div class="tape"></div>
  </div>
  
  <div class="bio-text sketchy">
    <h2>Calvin Grad</h2>
    {{ site.data.bio.text | markdownify }}
  </div>

  <div class="instruments">
    <img src="/static/assets/photos/dogs.png" alt="Binx" class="small-logo dogs">
    <div class="instrument-icon">🥁</div>
    <img src="/static/assets/photos/binx.png" alt="Binx" class="small-logo">
    <div class="instrument-icon">🎸</div>
  </div>
</div>