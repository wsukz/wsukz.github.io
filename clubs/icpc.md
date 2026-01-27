---
layout: default
title: "WSUK ICPC coding club"
permalink: /clubs/icpc/
---

# 🧑‍💻 WSUK ICPC

Welcome to the WSUK ICPC coding club! Here are some highlights:

<!-- Галерея -->
<div class="gallery">
{% assign fotos = site.static_files | where_exp:"f","f.path contains '/assets/foto/'" %}
{% for f in fotos %}
  <a href="{{ f.path | relative_url }}" target="_blank">
    <img src="{{ f.path | relative_url }}" alt="ICPC">
  </a>
{% endfor %}
</div>
