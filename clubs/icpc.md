---
layout: default
title: "WSUK ICPC coding club"
permalink: /clubs/icpc/
---

# 🧑‍💻 WSUK ICPC

Welcome to the WSUK ICPC coding club! Here are some highlights:

<div style="text-align:center;">
{% assign fotos = site.static_files | where_exp:"f","f.path contains '/assets/foto/'" %}
{% for f in fotos %}
  <img src="{{ f.path | relative_url }}" alt="ICPC" style="max-width:30%; margin:5px; border-radius:10px;">
{% endfor %}
</div>
