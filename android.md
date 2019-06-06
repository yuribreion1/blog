---
layout: page
permalink: /android/
title: android
description: Conteúdo que foi considerado para o ano
---

<ul class="post-list">
{% for poem in site.android reversed %}
    <li>
        <h2><a class="poem-title" href="{{ poem.url | prepend: site.baseurl }}">{{ poem.title }}</a></h2>
        <p class="post-meta">{{ poem.date | date: '%B %-d, %Y — %H:%M' }}</p>
      </li>
{% endfor %}
</ul>