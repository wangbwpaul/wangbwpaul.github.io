---
layout: page
permalink: /conferences/
title: Conferences
description:
years: [2024, 2023, 2022, 2021, 2020, 2019, 2018]
nav: true
nav_order: 2
---
<!-- _pages/publications.md -->
<div class="publications">
<h1>Conference Papers</h1>
{% assign exclusions = "2019:2018" | split: ":" %}
{%- for y in page.years %}
	{% capture yeartext %}{{ y }}{% endcapture %}
	{% unless exclusions contains yeartext %}
	  <h2 class="year">{{y}}</h2>
	  {% bibliography -f conferences -q @*[year={{y}}]* %}
	{% endunless%}
{% endfor %}

<h1>Invited Talks</h1>
{% assign exclusions = "2024:2023:2022:2019" | split: ":" %}
{%- for y in page.years %}
	{% capture yeartext %}{{ y }}{% endcapture %}
	{% unless exclusions contains yeartext %}
	  <h2 class="year">{{y}}</h2>
	  {% bibliography -f invitedtalks -q @*[year={{y}}]* %}
	{% endunless%}
{% endfor %}

</div>
