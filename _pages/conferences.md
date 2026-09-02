---
layout: page
permalink: /conferences/
title: Conferences
description:
years: [2027, 2026, 2025, 2024, 2023, 2022, 2021, 2020, 2019, 2018]
nav: true
nav_order: 2
---
<!-- _pages/publications.md -->

<style>
  .publications h1[id] { scroll-margin-top: 80px; }
  .publications-toc-sidebar {
    position: fixed;
    top: 120px;
    left: 30px;
    width: 200px;
    font-size: 0.85rem;
    z-index: 10;
  }
  .publications-toc-sidebar ul {
    list-style: none;
    padding-left: 0;
    margin: 0;
    border-left: 1px solid var(--global-divider-color, #e8e8e8);
  }
  .publications-toc-sidebar li { margin: 0; }
  .publications-toc-sidebar a {
    display: block;
    padding: 0.25rem 0 0.25rem 0.75rem;
    margin-left: -1px;
    color: var(--global-text-color-light, #828282);
    border-left: 2px solid transparent;
    line-height: 1.3;
  }
  .publications-toc-sidebar a:hover,
  .publications-toc-sidebar a.active {
    color: var(--global-theme-color, #b509ac);
    border-left-color: var(--global-theme-color, #b509ac);
    text-decoration: none;
  }
  @media (max-width: 1400px) {
    .publications-toc-sidebar { display: none; }
  }
</style>

<nav class="publications-toc-sidebar">
  <ul>
    <li><a href="#conference-papers">Conference Papers</a></li>
    <li><a href="#symposiums-invited-talk">Symposiums &amp; Invited Talks</a></li>
  </ul>
</nav>

<div class="publications">
<h1 id="conference-papers">Conference Papers</h1>
{% assign exclusions = "2019:2018" | split: ":" %}
{%- for y in page.years %}
	{% capture yeartext %}{{ y }}{% endcapture %}
	{% unless exclusions contains yeartext %}
	  <h2 class="year">{{y}}</h2>
	  {% bibliography -f conferences -q @*[year={{y}}]* %}
	{% endunless%}
{% endfor %}

<h1 id="symposiums-invited-talk">Symposiums & Invited Talks</h1>
{% assign exclusions = "2027:2024:2019" | split: ":" %}
{%- for y in page.years %}
	{% capture yeartext %}{{ y }}{% endcapture %}
	{% unless exclusions contains yeartext %}
	  <h2 class="year">{{y}}</h2>
	  {% bibliography -f invitedtalks -q @*[year={{y}}]* %}
	{% endunless%}
{% endfor %}

</div>

<script>
  (function () {
    var links = Array.prototype.slice.call(
      document.querySelectorAll('.publications-toc-sidebar a')
    );
    if (!links.length) return;
    var sections = links.map(function (a) {
      return document.getElementById(a.getAttribute('href').slice(1));
    });
    function onScroll() {
      var pos = window.scrollY + 100;
      var current = 0;
      for (var i = 0; i < sections.length; i++) {
        if (sections[i] && sections[i].offsetTop <= pos) current = i;
      }
      links.forEach(function (a, i) {
        a.classList.toggle('active', i === current);
      });
    }
    window.addEventListener('scroll', onScroll, { passive: true });
    onScroll();
  })();
</script>
