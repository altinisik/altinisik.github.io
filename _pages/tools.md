---
layout: page
title: tools
permalink: /tools/
description: Databases, web applications and software.
nav: true
nav_order: 5
---

{% assign categories = "Databases,Web applications,Software" | split: "," %}

{% for category in categories %}
{% assign items = site.data.tools | where: "category", category %}
{% if items.size > 0 %}

<h2 class="category mt-4">{{ category }}</h2>

<div class="row row-cols-1 row-cols-md-2">
  {% for tool in items %}
  <div class="col mb-4">
    <div class="card h-100 hoverable">
      <div class="card-body">
        <h3 class="card-title" style="font-size: 1.2rem">{{ tool.name }}</h3>
        <p class="card-text">{{ tool.description }}</p>
        {% if tool.tags %}
        <p class="card-text">
          {% for tag in tool.tags %}<span class="badge badge-light mr-1" style="font-weight: 400">{{ tag }}</span>{% endfor %}
        </p>
        {% endif %}
        <div class="links">
          {% if tool.launch %}<a href="{{ tool.launch }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener"><i class="fa-solid fa-arrow-up-right-from-square"></i> Open</a>{% endif %}
          {% if tool.code %}<a href="{{ tool.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener"><i class="fa-brands fa-github"></i> Code</a>{% endif %}
          {% if tool.data %}<a href="{{ tool.data }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener"><i class="fa-solid fa-database"></i> Data</a>{% endif %}
          {% if tool.paper %}<a href="{{ tool.paper | relative_url }}" class="btn btn-sm z-depth-0" role="button"><i class="fa-solid fa-file-lines"></i> Paper</a>{% endif %}
        </div>
      </div>
    </div>
  </div>
  {% endfor %}
</div>

{% endif %}
{% endfor %}
