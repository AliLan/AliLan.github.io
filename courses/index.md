---
layout: default
title: Master Course Projects
permalink: /courses/
---
<div class="container">
  <header class="page-head">
    <h1 class="page-title">Master Course Projects</h1>
    <p class="page-sub">Projects, papers, and study tools from my M.S. in Computer Science at California State University, Long Beach.</p>
  </header>
  <div class="grid-3">
    {%- for c in site.data.courses %}
    {% include course-card.html c=c %}
    {%- endfor %}
  </div>
</div>
