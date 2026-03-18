---
layout: page
title: Notes
permalink: /notes/
---

{% assign posts = site.posts | where_exp: "post", "post.categories contains 'notes'" %}

{% for post in posts %}
  <article class="post-card">
    <a href="{{ post.url | relative_url }}" class="post-link-overlay"></a>

    <h2>{{ post.title }}</h2>
    
    <small>{{ post.date | date: "%d %b %Y" }}</small>
    
    <p>{{ post.excerpt | strip_html | truncate: 140 }}</p>
  </article>
{% endfor %}
