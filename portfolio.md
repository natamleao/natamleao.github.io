---
layout: page
title: Portfolio
---

<!-- INTRO -->
<div class="section-intro portfolio-intro">
  <p>
    Estes são alguns projetos em que venho trabalhando. Cada um representa um estágio do aprendizado e da experimentação — da ideia à execução.
  </p>
  <p> 
    Não busco perfeição, busco evolução constante.
  </p>
</div>

<!-- LISTA DE PROJETOS -->
{% assign posts = site.posts | where_exp: "post", "post.categories contains 'portfolio'" %}

<div class="section-list portfolio-list">
  {% for post in posts %}
    <article class="post-card portfolio-card">
      <a href="{{ post.url | relative_url }}" class="post-link-overlay"></a>
      
      <div class="post-card-content">
        <h2>{{ post.title }}</h2>
        <small>{{ post.date | date: "%d %b %Y" }}</small>
        <p>{{ post.excerpt | strip_html | truncate: 140 }}</p>
      </div>
    </article>
  {% endfor %}
</div>
