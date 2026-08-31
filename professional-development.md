---
layout: default
title: Professional Development
description: Categorized Coursera coursework in cloud architecture, data, machine learning, DevOps, and application security.
permalink: /professional-development/
---
{% assign cv = site.data.cv %}
{% assign development = cv.professional_development %}
<section class="cv-section" aria-labelledby="professional-development-title">
  <h2 id="professional-development-title">Professional Development</h2>
  <p class="profile-copy">{{ development.summary.course_count }} Coursera course certificates completed from {{ development.summary.date }} across {{ development.summary.focus_areas.size }} areas.</p>
  <div class="development-groups">
    {% for area in development.summary.focus_areas %}
    {% assign area_items = development.items | where: "area", area.name %}
    <section class="development-group" aria-labelledby="{{ area.name | slugify }}-title">
      <div class="development-group-heading">
        <div class="development-group-heading-content">
          <h3 id="{{ area.name | slugify }}-title">{{ area.name }}</h3>
          <p>{{ area.count }} course certificates</p>
        </div>
      </div>
      <div class="credential-list">
        {% for item in area_items %}
        <article class="credential-entry">
          <p class="entry-meta">{{ item.kind }} · {{ item.date }}</p>
          <div class="credential-detail">
            <h4>{{ item.name }}</h4>
            <p class="credential-issuer">{{ item.issuer }}</p>
          </div>
        </article>
        {% endfor %}
      </div>
    </section>
    {% endfor %}
  </div>
  <a class="text-link" href="{{ '/' | relative_url }}">Back to CV <span aria-hidden="true">→</span></a>
</section>
