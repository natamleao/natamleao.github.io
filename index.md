---
layout: page
title: Home
---

<h2>Bem-vindo ao site!</h2>
<p>Essa é a página inicial.</p>

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin-top: 2rem;">
  {% for post in site.posts limit:4 %}
    <a href="{{ post.url | relative_url }}" style="flex:1 1 200px; background: rgba(255,255,255,0.05); padding: 1.5rem; border-radius: 12px; border: 1px solid rgba(255,255,255,0.15); color:#fff; text-decoration:none;">
      <h3>{{ post.title }}</h3>
      <p>{{ post.excerpt | strip_html | truncate: 80 }}</p>
    </a>
  {% endfor %}
</div>
