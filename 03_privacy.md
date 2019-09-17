---
layout: page
title: Privacy
permalink: /privacy/
order: 3
---
These are the articles I wrote about some privacy parts.

{% for post in site.categories.privacy %}
 <li><span>{{ post.date | date_to_string }}</span> &nbsp; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}