---
layout: page
title: Notes
permalink: /notes/
---

<div class="rao-index-page">
  <p class="rao-index-intro">Shorter notes, fragments, and things worth keeping without turning them into a full essay.</p>

  {% assign notes = site.posts | where: 'kind', 'note' | where_exp: 'post', 'post.hidden != true' %}
  {% if notes.size > 0 %}
    <ul class="rao-writing-list">
      {% for post in notes %}
        <li class="rao-writing-item">
          <a href="{{ post.url | relative_url }}">
            <time class="rao-writing-date" datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: '%Y.%m.%d' }}</time>
            <div>
              <h2 class="rao-writing-title">{{ post.title }}</h2>
              <p class="rao-writing-description">
                {% if post.description %}
                  {{ post.description }}
                {% else %}
                  {{ post.excerpt | strip_html | strip_newlines | truncate: 140 }}
                {% endif %}
              </p>
            </div>
          </a>
        </li>
      {% endfor %}
    </ul>
  {% else %}
    <p class="rao-empty-note">Nothing here yet. This will be the lighter, less formal side of the site.</p>
  {% endif %}
</div>
