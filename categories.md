---
layout: page 
title: Categories
permalink: /categories/
---

Here is a list of all the categories. 

<div class="post-categories">
  {% for post in site.posts %}
  {% if post.categories contains 'cs2150' %}
  <li>{{ post.title }}</li>
  {% endif %}
{% endfor %}

</div>