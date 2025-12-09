---
layout: page
title: Archive
permalink: /archive/
---

{% comment %}
  Archive page: show only posts not from the current year,
  group by year, and ensure each <ul> is properly opened & closed.
{% endcomment %}

{% assign this_year = site.time | date: "%Y" %}
{% assign last_year = nil %}

{% for post in site.posts %}
  {% assign post_year = post.date | date: "%Y" %}

  {%- comment -%}
  Skip posts from the current year
  {%- endcomment -%}
  {% if post_year == this_year %}
    {% continue %}
  {% endif %}

  {%- comment -%}
  If year changed: close previous <ul> (if any), print new year heading and open new <ul>
  {%- endcomment -%}
  {% if last_year != post_year %}
    {% if last_year != nil %}
      </ul>
    {% endif %}
    <h2>{{ post_year }}</h2>
    <ul>
    {% assign last_year = post_year %}
  {% endif %}

  <li>
    {{ post.date | date: "%B %d" }} —
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
  </li>

{% endfor %}

{%- comment -%}
Make sure we close the final <ul> if we opened one
{%- endcomment -%}
{% if last_year != nil %}
  </ul>
{% endif %}
