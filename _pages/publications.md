---
layout: page
permalink: /publications/
title: Publications
description:
years: [2024, 2023, 2022, 2021, 2020]
nav: true
nav_order: 1
---
<!-- _pages/publications.md -->
<div class="publications">
<h1>Journal Articles</h1>
{% assign exclusions = "2020" | split: ":" %}
{%- for y in page.years %}
	{% capture yeartext %}{{ y }}{% endcapture %}
	{% unless exclusions contains yeartext %}
	  <h2 class="year">{{y}}</h2>
	  {% bibliography -f papers -q @*[year={{y}}]* %}
	{% endunless%}
{% endfor %}
<h1>Book Chapters</h1>
{% assign exclusions = "2024:2022:2020" | split: ":" %}
{%- for y in page.years %}
	{% capture yeartext %}{{ y }}{% endcapture %}
	{% unless exclusions contains yeartext %}
	  <h2 class="year">{{y}}</h2>
	  {% bibliography -f bookchapters -q @*[year={{y}}]* %}
	{% endunless %}
{% endfor %}
<h1>Special Issues</h1>
{% assign exclusions = "2023:2022:2021:2020" | split: ":" %}
{%- for y in page.years %}
	{% capture yeartext %}{{ y }}{% endcapture %}
	{% unless exclusions contains yeartext %}
	  <h2 class="year">{{y}}</h2>
	  {% bibliography -f specialissues -q @*[year={{y}}]* %}
	{% endunless %}
{% endfor %}
<h1>Other Articles</h1>
{% assign exclusions = "2024:2023:2021" | split: ":" %}
{%- for y in page.years %}
	{% capture yeartext %}{{ y }}{% endcapture %}
	{% unless exclusions contains yeartext %}
	  <h2 class="year">{{y}}</h2>
	  {% bibliography -f otherarticles -q @*[year={{y}}]* %}
	{% endunless %}
{% endfor %}
</div>
