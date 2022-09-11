---
layout: page
permalink: /publications/
title: Publications
description:
years: [2022, 2021, 2020]
nav: true
nav_order: 1
---
<!-- _pages/publications.md -->
<div class="publications">
<h1>Journal Articles</h1>
{%- for y in page.years %}
  <h2 class="year"></h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}
<h1>Book Chapters</h1>
{%- for y in page.years %}
  <h2 class="year"></h2>
  {% bibliography -f bookchapters -q @*[year={{y}}]* %}
{% endfor %}
<h1>Other Articles</h1>
{%- for y in page.years %}
  <h2 class="year"></h2>
  {% bibliography -f otherarticles -q @*[year={{y}}]* %}
{% endfor %}


</div>
