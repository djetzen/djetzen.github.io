---
layout: page
title: Programming
permalink: /programming/
order: 2
---

Here is the list of articles, which I wrote about programming.

{% for post in site.categories.Programming %}
 <li><span>{{ post.date | date_to_string }}</span> &nbsp; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}