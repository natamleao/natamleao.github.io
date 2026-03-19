---
layout: page
title: Home
---

<h2>Bem-vindo ao site</h2>

<p>Aqui é sua base. Sem firula.</p>

<h3>Últimos posts</h3>

<ul>
  {% for post in site.posts limit:5 %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
