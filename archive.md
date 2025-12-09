---
layout: page
title: Archive
permalink: /archive/
---

{% assign this_year = site.time | date: "%Y" %}
{% assign last_year = nil %}

{% for post in site.posts %}
{% assign post_year = post.date | date: "%Y" %}

{% if post_year == this_year %}
{% continue %}
{% endif %}

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
  <a href="{{ post.url }}">{{ post.title }}</a>
</li>

{% endfor %}

{% if last_year != nil %}
</ul>
{% endif %}
