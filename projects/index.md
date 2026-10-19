---
layout: default
title: Projects
permalink: /projects/
---

<div class="projects-page">
  <h1>🛠️ Projects</h1>
  <p class="projects-lead">A few things I've built, from VR experiences to course projects. Demo videos are on the way.</p>

  <div class="project-grid">
    {% for p in site.data.projects %}
    <article class="project-card">
      <div class="project-media">
        {% if p.video and p.video != "" %}
          {% if p.video contains "youtube.com" or p.video contains "youtu.be" or p.video contains "vimeo.com" %}
          <iframe src="{{ p.video }}" title="{{ p.title }} demo video" allowfullscreen loading="lazy"></iframe>
          {% else %}
          <video src="{{ p.video | relative_url }}" controls preload="metadata"></video>
          {% endif %}
        {% else %}
          <div class="project-placeholder">
            <span class="project-emoji">{{ p.emoji }}</span>
            <span class="project-soon">Video coming soon</span>
          </div>
        {% endif %}
      </div>
      <div class="project-body">
        <h2>{{ p.title }} <span class="project-year">{{ p.year }}</span></h2>
        <p>{{ p.summary }}</p>
        <ul class="project-tags">
          {% for t in p.tags %}<li>{{ t }}</li>{% endfor %}
        </ul>
        <div class="project-links">
          {% if p.link %}<a href="{{ p.link | relative_url }}">Open →</a>{% endif %}
          {% if p.repo and p.repo != "" %}<a href="{{ p.repo }}">Code →</a>{% endif %}
        </div>
      </div>
    </article>
    {% endfor %}
  </div>
</div>

<style>
.projects-page { max-width: 1100px; margin: 0 auto; padding: 2rem 0 3rem; }
.projects-page h1 { margin-bottom: 0.3rem; }
.projects-lead { color: #555; margin-bottom: 2rem; }
.project-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(300px, 1fr)); gap: 1.5rem; }
.project-card { background: #fff; border-radius: 1.2rem; overflow: hidden; box-shadow: 0 4px 24px rgba(0,0,0,0.08); display: flex; flex-direction: column; }
.project-media { aspect-ratio: 16 / 9; background: linear-gradient(120deg, #ff6b9d 0%, #5ac8fa 100%); }
.project-media iframe, .project-media video { width: 100%; height: 100%; border: 0; display: block; background: #000; }
.project-placeholder { height: 100%; display: flex; flex-direction: column; align-items: center; justify-content: center; color: #fff; gap: 0.4rem; }
.project-emoji { font-size: 3rem; }
.project-soon { font-size: 0.95rem; opacity: 0.9; }
.project-body { padding: 1.2rem 1.4rem 1.4rem; display: flex; flex-direction: column; flex: 1; }
.project-body h2 { font-size: 1.3rem; margin: 0 0 0.5rem; }
.project-year { font-size: 0.9rem; font-weight: 400; color: #888; margin-left: 0.4rem; }
.project-body p { margin: 0 0 0.8rem; color: #444; }
.project-tags { list-style: none; padding: 0; margin: 0 0 0.8rem; display: flex; flex-wrap: wrap; gap: 0.4rem; }
.project-tags li { font-size: 0.8rem; background: #eaf6ff; color: #2a7fb8; padding: 0.2rem 0.6rem; border-radius: 999px; }
.project-links { margin-top: auto; display: flex; gap: 1rem; }
.project-links a { font-weight: 600; color: #ff6b9d; text-decoration: none; }
</style>
