---
layout: page
title: Notes
permalink: /notes/
---

{% for post in site.posts %}
  {% if post.categories contains "notes" %}
    {% include meta.html post=post %}
    {{ post.excerpt }} <a href="{{ post.url }}">read more</a>
  {% endif %}
{% endfor %}
