---
layout: page
title: Archive
permalink: /archive/
---

<h1>Archive</h1>

{% assign this_year = site.time | date: "%Y" %}
{% assign current_year = "" %}

{% for post in site.posts %}
  {% assign post_year = post.date | date: "%Y" %}

  {%- comment -%}
  Skip posts from the current year (2025)
  {%- endcomment -%}
  {% if post_year == this_year %}
    {% continue %}
  {% endif %}

  {% if post_year != current_year %}
    {% unless current_year == "" %}
    {% endunless %}
  <h2>{{ post_year }}</h2>
    {% assign current_year = post_year %}
  {% endif %}

  <ul>
    <li>
      {{ post.date | date: "%B %d" }} — 
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  </ul>
{% endfor %}
