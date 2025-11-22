---
layout: default
title: Projects
description: My projects and work
---

{% assign grouped = site.projects | group_by: "category" %}
{% for group in grouped %}
  <h2>{{ group.name }}</h2>
  <ul>
    {% for project in group.items %}
      <li>
        <strong>{{ project.title }}</strong> – {{ project.description }}
        {% if project.link %}
          <a href="{{ project.link }}">View</a>
        {% endif %}
      </li>
    {% endfor %}
  </ul>
{% endfor %}
