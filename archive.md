---
layout: page
title: Archive
permalink: /archive/
---

<h1>Archive</h1>

{% assign this_year = site.time | date: "%Y" %}
{% assign last_year = "" %}

{% for post in site.posts %}
  {% assign post_year = post.date | date: "%Y" %}

  {%- comment -%}
  Skip posts from the current year
  {%- endcomment -%}
  {% if post_year == this_year %}
    {% continue %}
  {% endif %}

  {%- comment -%}
  Print year heading when year changes
  {%- endcomment -%}
  {% if post_year != last_year %}
  <h2>{{ post_year }}</h2>
  {% assign last_year = post_year %}
  <ul>
  {% endif %}

      <li>
        {{ post.date | date: "%B %d" }} —
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </li>

  {%- comment -%}
  Close list when next year starts
  {%- endcomment -%}

  {% assign next_post = site.posts[forloop.index0] %}
  {% if next_post %}
    {% assign next_year = next_post.date | date: "%Y" %}
    {% if next_year != post_year %}
      </ul>
    {% endif %}
  {% endif %}

{% endfor %}

