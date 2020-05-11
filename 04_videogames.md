---
layout: page
title: Videogames
permalink: /videogames/
order: 4
---

Schon seit meiner Jugend begleiten mich Videospiele. Angefangen hat alles mit dem originalen Gameboy, bald folgten jedoch schon der Super Nintendo, die Playstation und anschließend die Playstation 2 sowie der Gamecube.

Da ich mich auch sehr für die Videospielkultur interessiere, habe ich mir überlegt ab und an über verschiedene Spiele zu schreiben, die vielleicht auch schon etwas älter sein können.

Hier ist eine Liste mit Artikeln zum Thema Videospiele zu finden, die ich bisher verfasst habe:

{% for post in site.categories.videogames %}
 <li><span>{{ post.date | date_to_string }}</span> &nbsp; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
