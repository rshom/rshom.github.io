---
permalink: /work
title: "Work"
layout: default
collection: projects
---

<!-- TODO: make this a layout (portfolio) to be used for play as well -->

<div style="display:flex; justify-content:space-between; flex-wrap:wrap">

{% assign project_list = site.projects | sort:"created" %}
{% for page in project_list reversed %}

<div style="margin-top:1%; margin-bottom:1%">
	<center>
	<a href=".{{ page.url }}">
		<img style="height:320px; width:320px; display:block; margin-left:auto; margin-right:auto;" 
		src="/assets/{{ page.id }}/thumbnail.png"
		alt="{{ page.title }} thumbnail" />
	</a>
	<h4>
		<a href=".{{ page.url }}">
			{{ page.title }}
		</a>
	<!-- </h5><h5> -->
		({{ page.updated | date: "%Y"}}) 
	</h4>
	</center>
	<!-- 
	<p>
		{{ page.excerpt }}
	</p>
	 -->
</div>

{% endfor %}

</div>



