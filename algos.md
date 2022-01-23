---
layout: page
title: Algorithms
permalink: /algos/
---

<div class="page">
  <p class=message>This is a collection from my Algorithms course with Professor Robbie Hott.</p>

<table class="table">
  <thead>
    <tr>
      <th scope="col">Date</th>
      <th scope="col">Title</th>
      <th scope="col">Source</th>
    </tr>
  </thead>
  <tbody>
    {% assign algo_posts = site.categories.algorithms %}
{% for post in algo_posts %}
<tr>
    <td>{{post.date | date: "%a, %b %d, %y"}}</td>
    <td><a href="{{post.url}}">{{post.title}}</a></td>
    {% if post.link %}
    <td><a href="{{post.link}}">Slides</a></td>
    {% endif %}
</tr>
{% endfor %}
</tbody>
</table>
