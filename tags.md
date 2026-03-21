---
layout: page
title: "Tags"
---

<div class="section-intro">
  <p>Escolha uma tag para ver todos os posts relacionados:</p>
</div>

<div class="section-list">
  {% assign all_tags = site.posts | map: "tags" | flatten | uniq | sort %}
  {% for tag in all_tags %}
    <article class="post-card tag-card">
      <a href="#{{ tag | slugify }}" class="post-link-overlay"></a>
      <h3>#{{ tag }}</h3>
      <p>Clique para ver todos os posts desta tag.</p>
    </article>
  {% endfor %}
</div>

<hr>

{% for tag in all_tags %}
  <h2 id="{{ tag | slugify }}">#{{ tag }}</h2>
  <div class="section-list">
    {% assign tagged_posts = site.posts | where_exp: "post", "post.tags contains tag" %}
    {% for post in tagged_posts %}
      <article class="post-card">
        <a href="{{ post.url | relative_url }}" class="post-link-overlay"></a>
        <h3>{{ post.title }}</h3>
        <small>{{ post.date | date: "%d %b %Y" }}</small>
        <p>{{ post.excerpt | strip_html | truncate: 140 }}</p>
      </article>
    {% endfor %}
  </div>
{% endfor %}
