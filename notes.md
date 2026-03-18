---
layout: page
title: Notes
permalink: /notes/
---

{% for post in site.posts %}
  {% if post.categories contains "notes" %}
    <article>
      {% include meta.html post=post %}
      {{ post.excerpt }}
      <footer class="button">
        <a href="{{ post.url | relative_url }}">read more</a>
      </footer>
    </article>
  {% endif %}
{% endfor %}
