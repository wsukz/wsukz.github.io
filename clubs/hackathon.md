---
layout: default
title: "WSUK Hackathon Club"
permalink: /clubs/hackathon/
---

# 🧑‍💻 WSUK Hackathon


Welcome to the WSUK ICPC coding club! Here are some highlights:

<!-- Slider Start -->
<div id="icpc-slider" style="text-align:center;">
  <img id="slider-img" src="" alt="ICPC" style="width:300px; height:200px; object-fit:cover; border-radius:10px; cursor:pointer;">
</div>

<script>
  // Получаем все картинки из assets/foto
  const fotos = [
    {% assign all_imgs = site.static_files | where_exp:"f","f.path contains '/assets/foto/'" %}
    {% for f in all_imgs %}
      "{{ f.path | relative_url }}"{% if forloop.last == false %},{% endif %}
    {% endfor %}
  ];

  // Случайное начальное изображение
  let currentIndex = Math.floor(Math.random() * fotos.length);
  const sliderImg = document.getElementById("slider-img");
  sliderImg.src = fotos[currentIndex];

  // Клик открывает картинку в новой вкладке
  sliderImg.onclick = function() {
    window.open(fotos[currentIndex], '_blank');
  }

  // Автоматическая смена каждые 3 секунды
  setInterval(() => {
    currentIndex = (currentIndex + 1) % fotos.length;
    sliderImg.src = fotos[currentIndex];
  }, 3000);
</script>
<!-- Slider End -->
