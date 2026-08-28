---
layout: page
title: Essays
permalink: /essays/
---

<div class="rao-index-page">
  <p class="rao-index-intro">Longer pieces on games, philosophy, art, and whatever else stays in my head long enough to become an essay.</p>

  {% assign essays = site.posts | where_exp: 'post', "post.kind != 'note' and post.hidden != true" %}
  <ul class="rao-writing-list">
    {% for post in essays %}
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
</div>
