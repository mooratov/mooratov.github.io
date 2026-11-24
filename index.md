---
layout: default
title: Sasha Muratov
---

# Sasha Muratov

<p class="subtitle">Data Scientist &mdash; ML Systems, Genomics, Security</p>

<div class="bio">

I'm a Data Scientist at Amazon with 10+ years of experience building end-to-end ML systems across logistics, genomics, and scientific computing. Currently working on multi-agent AI systems for customer data security. Previously led data science at Phase Genomics, where I built cloud-native cancer diagnostics pipelines, and before that worked in computational biology and astrophysics.

I'm interested in applied ML, agent-based systems, and bringing quantitative rigor to high-stakes domains.

</div>

## Selected Projects

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
