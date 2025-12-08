---
layout: page
title: Archive
permalink: /archive/
---

# Archive

A chronological list of all posts.

<ul>
  {% for post in site.posts %}
    <li>
      <span>{{ post.date | date: "%B %d, %Y" }}</span> —
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
