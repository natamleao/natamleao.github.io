---
layout: page
title: Tags
---

<h2>Tags</h2>

<ul>
{% assign all_tags = site.posts | map: "tags" | flatten | uniq | sort %}
{% for tag in all_tags %}
  <li><a href="#{{ tag | slugify }}">{{ tag }}</a></li>
{% endfor %}
</ul>

<hr>

{% for tag in all_tags %}
  <h3 id="{{ tag | slugify }}">{{ tag }}</h3>
  <ul>
    {% assign tagged_posts = site.posts | where_exp: "post", "post.tags contains tag" %}
    {% for post in tagged_posts %}
      <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
