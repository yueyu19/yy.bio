---
layout: page
permalink: /publications/
title: Publications
description: My peer-reviewed publications.
years: [2024, 2023, 2022, 2021, 2020, 2019]
nav: true
nav_order: 1
scholar:
  last_name: [Badings]
  first_name: [Thom]
---
See also my <a href="https://scholar.google.nl/citations?hl=nl&user=7K6uKqoAAAAJ">Google scholar</a> or my <a href="https://dblp.uni-trier.de/pid/263/6527.html">DBLP page</a>

<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
