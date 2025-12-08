---
layout: page
title: Archive
permalink: /archive/
---

# Archive

{% for post in site.posts %}
  {% capture year %}{{ post.date | date: "%Y" }}{% endcapture %}
  {% if year != current_year %}
  {% assign current_year = year %}
  
  ## {{ current_year }}
  {% endif %}

- {{ post.date | date: "%B %d" }} — <a href="{{ post.url }}">{{ post.title }}</a>
{% endfor %}
