---
layout: page
title: Algorithms
permalink: /algorithms/
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
    <td><a href="{{post.link}}">Slides</a></td>
</tr>
{% endfor %}
</tbody>
</table>
