---
layout: page
title: Portfolio
permalink: /portfolio/
---

{% assign posts = site.posts | where_exp: "post", "post.categories contains 'portfolio'" %}

{% for post in posts %}
  <article>
    <h2>{{ post.title }}</h2>
    
    <small>{{ post.date | date: "%d %b %Y" }}</small>
    
    <p>{{ post.excerpt }}</p>
  
    <footer>
      <a href="{{ post.url | relative_url }}">Read more →</a>
    </footer>
  </article>
{% endfor %}
