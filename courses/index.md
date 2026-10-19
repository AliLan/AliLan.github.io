---
layout: default
title: Master Course Projects
permalink: /courses/
---

<div class="courses-page">
  <h1>🎓 Master Course Projects</h1>
  <p class="courses-lead">Projects, papers, and study tools from my master's courses.</p>

  <div class="course-grid">
    {% for c in site.data.courses %}
    <a class="course-card" href="{{ '/courses/' | append: c.slug | append: '/' | relative_url }}">
      <span class="course-emoji">{{ c.emoji }}</span>
      <span class="course-name">{{ c.name }}</span>
      <span class="course-count">{% if c.items.size > 0 %}{{ c.items.size }} item{% if c.items.size > 1 %}s{% endif %}{% else %}Coming soon{% endif %}</span>
    </a>
    {% endfor %}
  </div>
</div>

<style>
.courses-page { max-width: 1100px; margin: 0 auto; padding: 2rem 0 3rem; }
.courses-lead { color: #555; margin-bottom: 2rem; }
.course-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(260px, 1fr)); gap: 1.2rem; }
.course-card { display: flex; flex-direction: column; gap: 0.4rem; padding: 1.5rem; border-radius: 1.2rem; color: #fff; text-decoration: none; background: linear-gradient(120deg, #ff6b9d 0%, #5ac8fa 100%); box-shadow: 0 4px 24px rgba(0,0,0,0.08); transition: transform 0.2s, box-shadow 0.2s; }
.course-card:nth-child(3n+2) { background: linear-gradient(120deg, #5ac8fa 0%, #00c9a7 100%); }
.course-card:nth-child(3n) { background: linear-gradient(120deg, #ffb347 0%, #ff6b9d 100%); }
.course-card:hover { transform: translateY(-3px); box-shadow: 0 8px 30px rgba(0,0,0,0.14); color: #fff; text-decoration: none; }
.course-emoji { font-size: 2.2rem; }
.course-name { font-size: 1.25rem; font-weight: 700; }
.course-count { font-size: 0.9rem; opacity: 0.9; }
</style>
