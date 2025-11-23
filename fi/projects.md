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
          <strong>{{ project.title }}</strong> – {{ project.description }}
        </a>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
