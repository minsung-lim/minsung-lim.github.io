---
layout: default
title: Additional Qualifications
description: Additional qualifications and earlier Microsoft certifications held by Minsung Lim.
permalink: /qualifications/
---
{% assign cv = site.data.cv %}
{% assign qualifications = cv.additional_qualifications %}
<section class="cv-section" aria-labelledby="additional-qualifications-title">
  <h2 id="additional-qualifications-title">Additional Qualifications</h2>
  <div class="credential-list">
    {% for item in qualifications.items %}
    <article class="credential-entry">
      <p class="entry-meta">{{ item.kind }}{% if item.date %} · {{ item.date }}{% endif %}</p>
      <div class="credential-detail">
        <h3>{{ item.name }}</h3>
        <p class="credential-issuer">{{ item.issuer }}</p>
      </div>
    </article>
    {% endfor %}
  </div>
</section>
{% assign earlier_technical_credentials = cv.earlier_technical_credentials %}
{% if earlier_technical_credentials.items.size > 0 %}
<section class="cv-section" aria-labelledby="earlier-technical-credentials-title">
  <h2 id="earlier-technical-credentials-title">Earlier Microsoft Certifications</h2>
  <div class="credential-list">
    {% for item in earlier_technical_credentials.items %}
    <article class="credential-entry">
      <p class="entry-meta">{{ item.kind }} · {{ item.date }}</p>
      <div class="credential-detail">
        <h3>{{ item.name }}</h3>
        <p class="credential-issuer">{{ item.issuer }}</p>
        {% if item.details %}<p class="credential-issuer">{{ item.details }}</p>{% endif %}
      </div>
    </article>
    {% endfor %}
  </div>
</section>
{% endif %}
<a class="text-link" href="{{ '/' | relative_url }}">Back to CV <span aria-hidden="true">→</span></a>
