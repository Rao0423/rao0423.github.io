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
      {% include writing-item.html post=post %}
    {% endfor %}
  </ul>
</div>
