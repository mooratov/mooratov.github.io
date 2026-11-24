---
layout: default
title: Projects
---

# Projects

<div class="project-list">
{% for project in site.projects %}
<a href="{{ project.url | relative_url }}" class="project-card">
  <h3>{{ project.title }}</h3>
  <p>{{ project.summary }}</p>
  {% if project.tags %}
  <div class="tags">
    {% for tag in project.tags %}
    <span class="tag">{{ tag }}</span>
    {% endfor %}
  </div>
  {% endif %}
</a>
{% endfor %}
</div>
