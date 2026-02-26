---
layout: default
title: "WSUK Hackathon Club"
permalink: /clubs/hackathon/
---

# Welcome to WSUK Hackathon Club!

Students of **Woosong University Kazakhstan (WSUK)** actively participate in regional and national hackathons, demonstrating their expertise in artificial intelligence, data analytics, and digital technologies..

### AI Hackathon Turkistan 2026

On February 25–26, 2026, our students took part in **AI Hackathon Turkistan 2026**, organized within the framework of the interregional forum: **“Financial Security: In the Age of Digitization and AI.”**

- 114 teams in the qualification stage
- 25 finalist teams (Top 5 in each track)
- ~400 participants nationwide.

Participants represented universities and regions across Kazakhstan, including: KBTU, Astana IT, NU, Korkyt Ata, Yassawi, NIS and others. As well as teams from Astana, Almaty, Atyrau, Kyzylorda, Taraz, Shymkent and Turkistan.

### Challenge Tracks

Participants developed AI-driven solutions across five key directions:

- **AI Digital Trace** – Detection of illegal sellers on the Telegram platform.
- **AI Against Gambling Addiction** – Early detection and prevention of ludomania (gambling addiction).
- **AI for Public Procurement Analysis** – Identification of manipulative technical specifications in government tenders.
- **AI Monitoring of Illegal Online Resources** – Detection of online casinos, financial pyramids, and fraudulent websites.
- **Open AI Challenge: Financial Security** – Open-format solutions targeting fraud, shadow schemes, and financial risks.

  
### Hackathon Results

Out of five teams representing Woosong University Kazakhstan, **two teams - DarkSoup AI and AI Girls** - advanced to the finals, ranking among the TOP25 teams nationwide.

🏅 Both teams were awarded **200'000 KZT certificates** for their outstanding performance.

Their success highlights the growing strength of AI-focused project development at WSUK and confirms our students’ competitiveness on a national level.


### Inside Hackathon Club
Check out photos and videos of our teams in action! From intense brainstorming sessions and late-night prototyping to final project pitches and award ceremonies.

<div class="gallery">
{% assign fotos = site.static_files | where_exp:"f","f.path contains '/assets/hackathon/'" %}
{% for f in fotos %}
  <img class="gallery-img" src="{{ f.path | relative_url }}" alt="Hackathon">
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
