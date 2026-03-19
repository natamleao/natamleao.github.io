---
layout: page
title: Portfolio
permalink: /portfolio/
---

<section class="container portfolio">

  <!-- INTRO -->
  <div class="portfolio-intro">
    <h1>Portfolio</h1>
    <p>
      Aqui estão alguns dos projetos que venho desenvolvendo ao longo do tempo.
      Cada um representa uma etapa do processo — ideias testadas, sistemas construídos e aprendizados aplicados.
    </p>
    <p>
      Não é sobre perfeição, é sobre evolução constante.
    </p>
  </div>

  <!-- LISTA DE PROJETOS -->
  {% assign posts = site.posts | where_exp: "post", "post.categories contains 'portfolio'" %}

  <div class="portfolio-list">
    {% for post in posts %}
      <article class="post-card">
        <a href="{{ post.url | relative_url }}" class="post-link-overlay"></a>

        <h2>{{ post.title }}</h2>
        <small>{{ post.date | date: "%d %b %Y" }}</small>
        <p>{{ post.excerpt | strip_html | truncate: 140 }}</p>
      </article>
    {% endfor %}
  </div>

</section>
