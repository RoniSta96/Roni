---
layout: default
title: Projects
description: My projects and work
---

{% assign grouped = site.projects | where: "lang", "en" | group_by: "category" %}
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

<h2>Small Projects</h2>
<ul class="projects-list">
  {% for project in site.data.smallprojects %}
    <li>
      <a href="{{ project.link }}" class="project-card" target="_blank">
        <strong>{{ project.title }}</strong>
        <p>{{ project.description }}</p>
      </a>
    </li>
  {% endfor %}
</ul>
