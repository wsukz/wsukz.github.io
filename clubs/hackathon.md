---
layout: default
title: "WSUK Hackathon Club"
permalink: /clubs/hackathon/
---

# 🧑‍💻 WSUK Hackathon

Welcome to the WSUK ICPC coding club! Here are some highlights:

<!-- Slider Start -->
<div id="icpc-slider" style="text-align:center;">
  <img id="slider-img" src="" alt="ICPC" style="width:450px; height:300px; object-fit:cover; border-radius:10px; cursor:pointer;">
</div>

<script>
  const fotos = [
    {% assign all_imgs = site.static_files | where_exp:"f","f.path contains '/assets/foto/'" %}
    {% for f in all_imgs %}
      "{{ f.path | relative_url }}"{% if forloop.last == false %},{% endif %}
    {% endfor %}
  ];
  let currentIndex = Math.floor(Math.random() * fotos.length);
  const sliderImg = document.getElementById("slider-img");
  sliderImg.src = fotos[currentIndex];
  sliderImg.onclick = function() {
    window.open(fotos[currentIndex], '_blank');
  }
  setInterval(() => {
    currentIndex = (currentIndex + 1) % fotos.length;
    sliderImg.src = fotos[currentIndex];
  }, 3000);
</script>
<!-- Slider End -->
