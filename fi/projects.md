---
layout: default
title: Projektit
description: Minun projektini
---

{% assign grouped = site.projects | where: "lang", "fi" | group_by: "category" %}
{% for group in grouped %}
  <h2>{{ group.name }}</h2>
  <ul>
    {% for project in group.items %}
      <li>
        <strong>{{ project.title }}</strong> – {{ project.description }}
        <a href="{{ project.url | relative_url }}">View</a>
      </li>
    {% endfor %}
  </ul>
{% endfor %}

