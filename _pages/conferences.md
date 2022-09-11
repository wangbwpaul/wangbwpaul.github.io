---
layout: page
permalink: /conferences/
title: Conferences
description:
years: [2022, 2021, 2020]
nav: true
nav_order: 2
---
<!-- _pages/publications.md -->
<div class="publications">
<h1>Conference Papers</h1>
{%- for y in page.years %}
  <h2 class="year"></h2>
  {% bibliography -f conferences -q @*[year={{y}}]* %}
{% endfor %}

<h1>Invited Talks</h1>
{%- for y in page.years %}
  <h2 class="year"></h2>
  {% bibliography -f invitedtalks -q @*[year={{y}}]* %}
{% endfor %}



</div>
