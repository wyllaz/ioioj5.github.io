---
layout: cayman
keywords:  web,php,CentOS,Go,Python
description: 关注后端技术、互联网技术。
---

<div id="posts">
  <h2>Blog Posts</h2>
  <ul>
    {% for post in site.posts %}
      <li><span>{{ post.date | date:"%F" }}</span>   <a href="{{ post.url }}"  target="_blank">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
</div>

<div id="pages">
  <h2>Pages</h2>
  <ul>
    {% for page in site.pages %}
      {% if page.title %}
        <li><a href="{{ page.url }}" target="_blank">{{ page.title }}</a></li>
      {% endif %}
    {% endfor %}
  </ul>
</div>