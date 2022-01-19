---
layout: page
title: Cybersecurity
permalink: /cybersecurity/
---

<div class="page">
  <p class=message>This is a collection from my Cybersecurity course with Professor Angela Orebaugh at UVA.</p>

<table class="table">
  <thead>
    <tr>
      <th scope="col">Date</th>
      <th scope="col">Title</th>
      <th scope="col">Source</th>
    </tr>
  </thead>
  <tbody>
    {% assign cyber_posts = site.categories.cybersecurity %}
{% for post in cyber_posts %}
<tr>
    <td>{{post.date | date: "%a, %b %d, %y"}}</td>
    <td><a href="{{post.url}}">{{post.title}}</a></td>
    <td><a href="{{post.link}}">Slides</a></td>
</tr>
{% endfor %}
</tbody>
</table>
