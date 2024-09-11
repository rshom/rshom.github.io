---
permalink: /archive
layout: page
title: Archive
---


<!-- TODO: split into two float columns, have blog on   -->

<!-- 
<div style="display:flex; justify-content:start; flex-wrap:wrap; flex-direction:row">
<div style="width:325px; margin-right:10px">
<h2>Blog</h2>

<ul>
  {% for post in site.posts %}
    <li> {{ post.date | date: "%Y-%m-%d"}}
      <a href=".{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

</div>
 -->
<div style="width:325px; margin-right:10px">

<h2>Projects</h2>

<ul>
  {% for page in site.projects reversed%}
    <li> {{ page.updated | date: "%Y"}}
      <a href=".{{ page.url }}">{{ page.title }}</a> 
	  <!-- - {{ page.excerpt }} -->
    </li>
  {% endfor %}
</ul>

</div>


