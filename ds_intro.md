---
layout: page
title: Data Science Intro
permalink: /ds_intro/
---

<div class="page">
  <p class=message>This is a collection from my Intro to Data Science course at UVA.</p>

<table class="table">
  <thead>
    <tr>
      <th scope="col">Date</th>
      <th scope="col">Title</th>
      <th scope="col">Source</th>
    </tr>
  </thead>
  <tbody>
    {% assign ds_posts = site.categories.ds_intro %}
{% for post in ds_posts %}
<tr>
    <td>{{post.date | date: "%a, %b %d, %y"}}</td>
    <td><a href="{{post.url}}">{{post.title}}</a></td>
    <td><a href="{{post.link}}">Slides</a></td>
</tr>
{% endfor %}
</tbody>
</table>
