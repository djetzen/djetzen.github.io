---
layout: page
title: Programming
permalink: /programming/
order: 1
---

Here is the list of articles, which I wrote about programming.

{% for post in site.categories.programming %}
 <li><span>{{ post.date | date_to_string }}</span> &nbsp; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
