---
layout: page
title: tags
permalink: /tags/
---
{% capture tags %}
  {% for tag in site.tags %}
    {{ tag[0] }}
  {% endfor %}
{% endcapture %}
{% assign sortedtags = tags | split:' ' | sort %}

{% for tag in sortedtags %}
  <h3 id="{{ tag }}">{{ tag }}</h3>
  <ul>
  {% for post in site.tags[tag] %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
  </ul>
{% endfor %}

## by page
{% capture tags %}
  {% for tag in site.tags %}
    {{ tag[0] }}
  {% endfor %}
{% endcapture %}
{% assign sortedtags = tags | split:' ' | sort %}
{% for tag in sortedtags %}
    <a href="/tags/{{ tag }}/">{{ tag }}</a><br>
{% endfor %}