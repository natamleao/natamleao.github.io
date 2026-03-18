---
layout: page
title: Portfolio
permalink: /portfolio/
---

{% if site.show_excerpts %}
  {% for post in site.posts %}
    {% if post.categories contains "portfolio" %}
      <article>
        {% include meta.html post=post %}
        {{ post.excerpt }}
        <footer class="button">
          <a href="{{ post.url | relative_url }}">read more</a>
        </footer>
      </article>
    {% endif %}
  {% endfor %}
{% else %}
  {% for post in site.posts %}
    {% if post.categories contains "portfolio" %}
      <div>
        <time datetime="{{ post.date | date_to_xmlschema }}">
          {{ post.date | date: "%Y-%m-%d" }}
        </time>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </div>
    {% endif %}
  {% endfor %}
{% endif %}
