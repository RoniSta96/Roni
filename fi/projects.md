---
layout: default
title: Projektit
description: Minun projektini
---

{% assign grouped = site.projects | where: "lang", "fi" | group_by: "category" %}
{% for group in grouped %}
  <h2>{{ group.name }}</h2>
  <ul class="projects-list">
    {% for project in group.items %}
      <li>
        <a href="{{ project.url | relative_url }}" class="project-card">
          <strong>{{ project.title }}</strong>   {{ project.description }}
        </a>
      </li>
    {% endfor %}
  </ul>
{% endfor %}

<h2>Pienet projektit</h2>
<ul class="projects-list">
  {% for project in site.data.smallprojects.fi %}
    <li class="project-card">
      <div class="project-content">
        <strong>{{ project.title }}</strong>
        <p>{{ project.description }}</p>

        {% if project.embed %}
          <div class="project-embed">
            <iframe src="{{ project.embed }}" allowfullscreen></iframe>
          </div>
        {% endif %}

        <div class="project-actions">
          <a href="{{ project.link }}" target="_blank" class="btn">Avaa selaimessa</a>
        </div>
      </div>
    </li>
  {% endfor %}
</ul>

