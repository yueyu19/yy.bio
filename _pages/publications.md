---
layout: page
permalink: /publications/
title: Publications
description: 
years: [2023, 2022, 2021, 2020, 2019, 2018, 2016]
nav: true
nav_order: 1
scholar:
  last_name: [Yu]
  first_name: [Yue]
---

See also my <a href="https://scholar.google.com/citations?user=bwhxFnEAAAAJ&hl=en">Google scholar</a> 

<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
