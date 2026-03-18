---
layout: page
title: Portfolio
permalink: /portfolio/
---

{% for post in site.posts %}
  {% if post.categories contains "portfolio" %}
    {% include meta.html post=post %}
    {{ post.excerpt }} <a href="{{ post.url }}">read more</a>
  {% endif %}
{% endfor %}
