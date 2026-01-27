---
layout: default
title: "WSUK ICPC Coding Club"
permalink: /clubs/icpc/
---

# Welcome to WSUK ICPC Club!

We are excited to introduce our ICPC Club, where young programmers take their first steps into the world of **competitive programming**. This year, Woosong University Kazakhstan (WSUK) in Turkistan joined ICPC with six first-year teams. Five teams advanced to the quarterfinals, ranking **2nd among new universities** and 15th overall.

Even though one of WSUK teams from our university was invited to the **ICPC NERC Finals** in Almaty, they performed very well and received an **honorary certificate**. 

The experience allowed them to meet the wider IT community, gain valuable skills, and lay a strong foundation for future programming competitions.
  
### ICPC 2025 Results
- [ICPC2025 - 1/8 Qualification Round](https://esep.cpfed.kz/contest/8icpc25/ranking/)
- [ICPC2025 - 1/4 Regional Round](https://nerc.itmo.ru/archive/2025/kazakhstan/standings.html)
- [ICPC2025 - 1/2 NERC Finals](https://nerc.itmo.ru/archive/2025/standings-kaz.html)

### Training
- [ACMP Ranking](https://acmp.ru/index.asp?main=rating&str=%u0412%u0443%u0441%u043E%u043D%u0433)
- [Codeforces Ranking](https://codeforces.com/ratings/organization/51681)

### Inside ICPC Club
Check out photos and videos of our teams in action! From practice sessions to competitions, see how our members train, collaborate, and celebrate their achievements in competitive programming.

<div class="gallery">
{% assign fotos = site.static_files | where_exp:"f","f.path contains '/assets/foto/'" %}
{% for f in fotos %}
  <img class="gallery-img" src="{{ f.path | relative_url }}" alt="ICPC">
{% endfor %}
</div>

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

  document.querySelectorAll(".gallery-img").forEach((img, idx) => {
    img.onclick = () => {
      currentIndex = idx;
      sliderImg.src = fotos[currentIndex];
      sliderModal.style.display = "flex";
    };
  });

  document.getElementById("close-slider").onclick = () => {
    sliderModal.style.display = "none";
  };

  document.getElementById("prev-btn").onclick = () => {
    currentIndex = (currentIndex - 1 + fotos.length) % fotos.length;
    sliderImg.src = fotos[currentIndex];
  };
  document.getElementById("next-btn").onclick = () => {
    currentIndex = (currentIndex + 1) % fotos.length;
    sliderImg.src = fotos[currentIndex];
  };

  document.addEventListener("keydown", (e) => {
    if(e.key === "Escape") sliderModal.style.display = "none";
  });
</script>
