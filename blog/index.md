---
layout: default
title: Blog
permalink: /blog/
---
<div class="container">
  <header class="page-head">
    <h1 class="page-title">Blog</h1>
    <p class="page-sub">Notes on software engineering, AI, VR, and grad school.</p>
  </header>
  <p class="count">{{ site.posts.size }} posts</p>
  <div class="grid-3">
    {%- for post in site.posts %}
    {% include post-card.html post=post %}
    {%- endfor %}
  </div>
</div>
