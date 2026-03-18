---
layout: page
title: Portfolio
permalink: /portfolio/
---

{% assign posts = site.posts | where_exp: "post", "post.categories contains 'portfolio'" %}

{% for post in posts %}
  <article class="post-card">
    <a href="{{ post.url | relative_url }}" class="post-link-overlay"></a>

    <h2>{{ post.title }}</h2>
    
    <small>{{ post.date | date: "%d %b %Y" }}</small>
    
    <p>{{ post.excerpt | strip_html | truncate: 140 }}</p>
  </article>
{% endfor %}
