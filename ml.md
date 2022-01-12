---
layout: page
title: ML Projects
permalink: /ml/
---

<div class="page">
  <p class=message>This is a collection of my machine leaning projects. Most of the content are Jupyter notebooks, with a few exceptions for video courses for math-related content.</p>
  {% assign ml_projects = site.categories.ml | sort: 'title' %}
  {% for project in ml_projects %}
    {% if project.title and project.link and project.image %}
        <a href="{{project.link}}">{{project.title}}</a>
        <img src="{{project.image}}">
    {% endif %}
  {% endfor %}
</div>

