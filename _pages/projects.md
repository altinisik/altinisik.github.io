---
layout: page
title: research
permalink: /research/
description: My research uses ancient genomes to study the human past, from the first farming villages of Southwest Asia to the communities of the Roman world.
nav: true
nav_order: 3
horizontal: true
---

<!-- pages/projects.md -->
<div class="projects">
{% assign sorted_projects = site.projects | sort: "importance" %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
</div>
