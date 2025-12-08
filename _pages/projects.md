---
title: Projects
layout: single
permalink: /projects/
classes: wide
author_profile: true
---

Below is a starter grid you can duplicate for each project. Update the entries
in `_data/projects.yml` to control the cards. Each project includes a name,
timeframe, short description, stack tags, and a call-to-action link.

<div class="projects-grid projects-grid--two">
  {% assign projects = site.data.projects.projects | default: [] %}
  {% for project in projects %}
    <article class="project-card">
      {% if project.images %}
        <div class="project-card__gallery">
          {% for media in project.images %}
            {% if media.src %}
              <figure class="project-card__image">
                <img src="{{ media.src | relative_url }}" alt="{{ media.alt | default: project.name }}">
              </figure>
            {% endif %}
          {% endfor %}
        </div>
      {% elsif project.image %}
        <figure class="project-card__image">
          <img src="{{ project.image | relative_url }}" alt="{{ project.image_alt | default: project.name }}">
        </figure>
      {% endif %}
      <header class="project-card__header">
        <p class="project-card__timeframe">{{ project.timeframe }}</p>
        <h2 class="project-card__title">{{ project.name }}</h2>
      </header>
      <p class="project-card__description">{{ project.description }}</p>
      {% if project.tech %}
        <ul class="project-card__tags">
          {% for tag in project.tech %}
            <li>{{ tag }}</li>
          {% endfor %}
        </ul>
      {% endif %}
      {% if project.ctas %}
        <div class="project-card__cta-group">
          {% for cta in project.ctas %}
            {% if cta.url %}
              <a href="{{ cta.url }}" class="project-card__cta" target="_blank" rel="noopener">
                {{ cta.label | default: "Learn more" }}
              </a>
            {% endif %}
          {% endfor %}
        </div>
      {% elsif project.cta_url %}
        <a href="{{ project.cta_url }}" class="project-card__cta" target="_blank" rel="noopener">
          {{ project.cta_label | default: "Learn more" }}
        </a>
      {% endif %}
    </article>
  {% endfor %}
</div>
