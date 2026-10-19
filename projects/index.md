---
layout: default
title: Projects
permalink: /projects/
---
<div class="container">
  <header class="page-head">
    <h1 class="page-title">Projects</h1>
    <p class="page-sub">A collection of things I've built, from VR experiences at the CSULB XR Lab to AI and data projects.</p>
  </header>

  <div class="toolbar">
    <input class="search" type="search" placeholder="Search projects..." aria-label="Search projects">
  </div>
  {%- assign all_tags = site.data.projects | map: "tags" | join: "|" | split: "|" | uniq | sort_natural %}
  <div class="chips" id="tag-filter">
    {%- for t in all_tags %}<button class="chip" type="button" data-tag="{{ t | escape }}">{{ t }}</button>{% endfor %}
  </div>

  <p class="count"><span id="project-count">{{ site.data.projects.size }}</span> projects</p>
  <div class="grid-2" id="project-grid">
    {%- for p in site.data.projects %}
    {% include project-card.html p=p %}
    {%- endfor %}
  </div>
  <div class="empty" id="no-results" hidden>No projects match your filters.</div>
</div>

<script>
(function () {
  var search = document.querySelector('.search');
  var chips = document.querySelectorAll('#tag-filter .chip');
  var cards = document.querySelectorAll('#project-grid .card');
  var count = document.getElementById('project-count');
  var empty = document.getElementById('no-results');
  var selected = [];
  function apply() {
    var q = search.value.trim().toLowerCase();
    var shown = 0;
    cards.forEach(function (c) {
      var tags = c.dataset.tags.split('|');
      var ok = (!q || c.dataset.text.indexOf(q) !== -1) &&
        selected.every(function (t) { return tags.indexOf(t) !== -1; });
      c.hidden = !ok;
      if (ok) shown++;
    });
    count.textContent = shown;
    empty.hidden = shown !== 0;
  }
  chips.forEach(function (chip) {
    chip.addEventListener('click', function () {
      var t = chip.dataset.tag;
      var i = selected.indexOf(t);
      if (i === -1) selected.push(t); else selected.splice(i, 1);
      chip.classList.toggle('active', i === -1);
      apply();
    });
  });
  search.addEventListener('input', apply);
})();
</script>
