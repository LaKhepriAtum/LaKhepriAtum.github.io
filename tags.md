---
layout: page
title: 태그
permalink: /tags/
---

{% assign sorted_tags = site.tags | sort %}
{% for tag in sorted_tags %}
<h2 id="{{ tag[0] | slugify }}">{{ tag[0] }} ({{ tag[1].size }})</h2>
<ul>
  {% for post in tag[1] %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
    <span class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</span>
  </li>
  {% endfor %}
</ul>
{% endfor %}
