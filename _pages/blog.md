---
title: Blog
layout: single
permalink: /blog/
classes: wide
author_profile: true
---

<!-- Use this page to highlight recent writing. Cards pull metadata directly from
local posts (in `_posts/`) and external entries listed in
`_data/external_posts.yml`. Add `header.teaser` (or `image`) to a post's front
matter to display an image on the card. -->

<div class="projects-grid blog-grid">
  {% assign posts = site.posts | default: [] %}
  {% assign external_posts = site.data.external_posts.posts | default: [] %}

  {% for post in posts %}
    <article class="project-card project-card--blog">
      {% assign teaser = post.header.image | default: post.header.teaser | default: post.image %}
      {% if teaser %}
        <figure class="project-card__image">
          <img src="{{ teaser | relative_url }}" alt="{{ post.title }}">
        </figure>
      {% endif %}
      <header class="project-card__header">
        <p class="project-card__timeframe">{{ post.date | date: "%B %d, %Y" }}</p>
        <h2 class="project-card__title">
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </h2>
      </header>
      {% if post.excerpt %}
        <p class="project-card__description">{{ post.excerpt | strip_html | truncate: 160 }}</p>
      {% endif %}
      {% if post.tags %}
        <ul class="project-card__tags">
          {% for tag in post.tags %}
            <li>{{ tag }}</li>
          {% endfor %}
        </ul>
      {% endif %}
      <a class="project-card__cta" href="{{ post.url | relative_url }}">Read more →</a>
    </article>
  {% endfor %}

  {% for ext in external_posts %}
    <article class="project-card project-card--blog">
      {% if ext.image %}
        <figure class="project-card__image">
          <img src="{{ ext.image | relative_url }}" alt="{{ ext.title }}">
        </figure>
      {% endif %}
      <header class="project-card__header">
        <p class="project-card__timeframe">{{ ext.date | date: "%B %d, %Y" }}</p>
        <h2 class="project-card__title">
          <a href="{{ ext.url }}" target="_blank" rel="noopener">{{ ext.title }}</a>
        </h2>
      </header>
      {% if ext.description %}
        <p class="project-card__description">{{ ext.description }}</p>
      {% endif %}
      {% if ext.tags %}
        <ul class="project-card__tags">
          {% for tag in ext.tags %}
            <li>{{ tag }}</li>
          {% endfor %}
        </ul>
      {% endif %}
      <a class="project-card__cta" href="{{ ext.url }}" target="_blank" rel="noopener">
        Read on Medium →
      </a>
    </article>
  {% endfor %}
</div>
