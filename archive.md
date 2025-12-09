---
layout: page
title: Archive
permalink: /archive/
---

{% assign this_year = site.time | date: "%Y" %}
{% assign last_year = "" %}

{% for post in site.posts %}
  {% assign post_year = post.date | date: "%Y" %}

  {% if post_year == this_year %}
    {% continue %}
  {% endif %}

  {% if post_year != last_year %}
  ### {{ post_year }}
  <ul>
  {% assign last_year = post_year %}
  {% endif %}

    <li>
      {{ post.date | date: "%B %d" }} —
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>

  {% assign next = site.posts[forloop.index0] %}
  {% if next %}
    {% assign next_year = next.date | date: "%Y" %}
    {% if next_year != post_year %}
      </ul>
    {% endif %}
  {% endif %}
{% endfor %}
