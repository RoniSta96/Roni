---
layout: default
title: Projects
description: My projects and work
lang: en
smallprojects_data: smallprojects
---

{% assign grouped = site.projects | where: "lang", "en" | group_by: "category" %}
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

<h2>{% if page.lang == "fi" %}Pienet projektit{% else %}Small Projects{% endif %}</h2>
<ul class="projects-list">
  {% assign datafile = site.data[page.smallprojects_data] %}
  {% for project in datafile %}
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
          <a href="{{ project.link }}" target="_blank" class="btn">
            {% if page.lang == "fi" %}Avaa selaimessa{% else %}Open in Browser{% endif %}
          </a>
        </div>
      </div>
    </li>
  {% endfor %}
</ul>

