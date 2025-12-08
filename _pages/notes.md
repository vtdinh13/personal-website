---
title: Notes
layout: single
permalink: /notes/
classes: wide
author_profile: true
---

Below is an automatically generated list of note entries from the `_notes/`
collection. Create Markdown files inside that folder with YAML front matter
(`title`, `date`, optional `tags`) and the page will stay up to date.

<div class="projects-grid blog-grid">
  {% assign notes = site.notes | sort: "date" | reverse %}
  {% if notes.size == 0 %}
    <p>Add your first note by creating a Markdown file inside <code>_notes/</code>.</p>
  {% endif %}
  {% for note in notes %}
    <article class="project-card project-card--blog">
      <header class="project-card__header">
        {% if note.date %}
          <p class="project-card__timeframe">{{ note.date | date: "%B %d, %Y" }}</p>
        {% endif %}
        <h2 class="project-card__title">
          <a href="{{ note.url | relative_url }}">{{ note.title }}</a>
        </h2>
      </header>
      {% if note.excerpt %}
        <p class="project-card__description">{{ note.excerpt | strip_html | truncate: 200 }}</p>
      {% endif %}
      {% if note.tags %}
        <ul class="project-card__tags">
          {% for tag in note.tags %}
            <li>{{ tag }}</li>
          {% endfor %}
        </ul>
      {% endif %}
      <a class="project-card__cta" href="{{ note.url | relative_url }}">Open note →</a>
    </article>
  {% endfor %}
</div>
