---
layout: default
title: Home
---

<h1>Welcome</h1>
<ul>
  {% for post in site.posts %}
    <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
