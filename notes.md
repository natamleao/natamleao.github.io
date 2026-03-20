--- 
layout: page
title: Notes
---
 
<!-- INTRO -->
<div class="section-intro"> 
  <p> 
    Um espaço para registrar ideias, reflexões e aprendizados ao longo do caminho.
  </p>
  <p>
    Nem tudo aqui está finalizado — muitas coisas estão sendo pensadas, testadas ou apenas exploradas.
  </p>
</div> 

<!-- LISTA -->
{% assign posts = site.posts | where_exp: "post", "post.categories contains 'notes'" %}

<div class="section-list">
  {% for post in posts %}
    <article class="post-card">
      <a href="{{ post.url | relative_url }}" class="post-link-overlay"></a>

      <h2>{{ post.title }}</h2>
      <small>
        {{ post.date | date: "%d %b %Y" }}
        {% if post.categories %}
          • {{ post.categories | join: ", " }}
        {% endif %}
      </small>
      <p>{{ post.excerpt | strip_html | truncate: 140 }}</p>
    </article>
  {% endfor %}
</div>
