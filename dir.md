---
layout: page
permalink: /dir/
title: Categories
---

<div id="archives">
<!-- TODO: Add TOC -->
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <div id="#{{ category_name | slugize }}"></div>
    <p></p>
    <!-- ADD CUSOTM REPLACEMENTS FOR CATEGORY TITLES HERE -->
    <h3 class="category-head">{{ category_name | replace: 'cs2150', 'Data Structures and Algorithms'| replace: 'happiness', 'Happiness' | 
    replace: 'ml', 'ML'
    }}</h3>
    <a name="{{ category_name | slugize }}"></a>
    {% assign cat = site.categories[category_name] | sort: 'title' %}
    {% for post in cat %}
      {% if category_name != 'ml' %}
      <article class="archive-item">
        <h4><a href="{{ post.url }}">{{post.title}}</a></h4>
      </article>
      {% else %}
     <article class="archive-item">
        <h4><a href="{{ post.link }}">{{post.title}}</a></h4>
      </article>
      {% endif %}

    {% endfor %}
  </div>
{% endfor %}
</div>