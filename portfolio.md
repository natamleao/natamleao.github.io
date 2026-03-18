---
layout: page
title: Portfolio
---

{% if site.show_excerpts %} {% for post in site.posts %}

{% include meta.html post=post %} {{ post.excerpt }} read more {% endfor %} {% else %} {% capture source %}{% include_relative archive.html title="Posts" %}{% endcapture %} {{ source | split: "---" | last }} {% endif %}
