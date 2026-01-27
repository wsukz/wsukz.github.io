---
layout: default
title: "WSUK Drones Club"
permalink: /clubs/drones/
---

# 🧑‍💻 WSUK Drones

Welcome to the WSUK ICPC coding club! Click any image to open the slider:

<!-- Gallery -->
<div class="icpc-gallery">
{% assign fotos = site.static_files | where_exp:"f","f.path contains '/assets/foto/'" %}
{% for f in fotos %}
  <img class="gallery-img" src="{{ f.path | relative_url }}" alt="ICPC">
{% endfor %}
</div>

<!-- Slider Modal -->
<div id="slider-modal" style="display:none; position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,0.9); justify-content:center; align-items:center; z-index:1000;">
  <span id="close-slider" style="position:absolute; top:20px; right:30px; font-size:40px; color:white; cursor:pointer;">&times;</span>
  <img id="slider-img" src="" style="max-width:90%; max-height:90%; border-radius:10px;">
  <button id="prev-btn" style="position:absolute; left:30px; font-size:30px; color:white; background:none; border:none; cursor:pointer;">&#10094;</button>
  <button id="next-btn" style="position:absolute; right:30px; font-size:30px; color:white; background:none; border:none; cursor:pointer;">&#10095;</button>
</div>

<script>
  const sliderModal = document.getElementById("slider-modal");
  const sliderImg = document.getElementById("slider-img");
  const fotos = [
    {% for f in fotos %}
      "{{ f.path | relative_url }}"{% if forloop.last == false %},{% endif %}
    {% endfor %}
  ];
  let currentIndex = 0;

  // Галерея клики
  document.querySelectorAll(".gallery-img").forEach((img, idx) => {
    img.onclick = () => {
      currentIndex = idx;
      sliderImg.src = fotos[currentIndex];
      sliderModal.style.display = "flex";
    };
  });

  // Закрыть modal
  document.getElementById("close-slider").onclick = () => {
    sliderModal.style.display = "none";
  };

  // Навигация
  document.getElementById("prev-btn").onclick = () => {
    currentIndex = (currentIndex - 1 + fotos.length) % fotos.length;
    sliderImg.src = fotos[currentIndex];
  };
  document.getElementById("next-btn").onclick = () => {
    currentIndex = (currentIndex + 1) % fotos.length;
    sliderImg.src = fotos[currentIndex];
  };

  // Esc закрытие
  document.addEventListener("keydown", (e) => {
    if(e.key === "Escape") sliderModal.style.display = "none";
  });
</script>

<style>
.icpc-gallery {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 10px;
}
.icpc-gallery img {
  width: 200px;
  height: 150px;
  object-fit: cover;
  border-radius: 10px;
  cursor: pointer;
  transition: transform 0.2s;
}
.icpc-gallery img:hover {
  transform: scale(1.05);
}
</style>
