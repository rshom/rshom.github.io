---
permalink: /work
title: Work
layout: page
---

{%- assign project_list = site.projects | sort: "date" | reverse %}
<div class="work-grid">
{%- for p in project_list %}
  {%- assign thumb = p.thumbnail | default: p.images[0].src %}
  <a class="work-card" href="{{ p.url | relative_url }}">
    {%- if thumb %}<img src="{{ thumb | relative_url }}" alt="" loading="lazy">{% else %}<div class="work-noimg">{{ p.title }}</div>{% endif %}
    <span class="work-title">{{ p.title }}</span>
    <span class="project-note">{{ p.date | date: "%Y" }}</span>
  </a>
{%- endfor %}
</div>
