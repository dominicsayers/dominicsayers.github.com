---
title: Archive
permalink: /archive/
---

All posts, newest first.

{% for post in site.posts %}
{% assign year = post.date | date: '%Y' %}
{% if year != current_year %}
{% unless forloop.first %}
</ul>
{% endunless %}

## {{ year }}

<ul>
{% assign current_year = year %}
{% endif %}
  <li><a href="{{ post.url }}">{{ post.title }}</a> <small>{{ post.date | date: '%-d %b' }}</small></li>
{% if forloop.last %}
</ul>
{% endif %}
{% endfor %}
