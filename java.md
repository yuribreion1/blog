---
layout: page
permalink: /java/
title: java
description: 2018 foi um ano de muito aprendizado, e foi assim que eu me preparei para as provas
---

<ul class="post-list">
{% for poem in site.java reversed %}
    <li>
        <h2><a class="poem-title" href="{{ poem.url | prepend: site.baseurl }}">{{ poem.title }}</a></h2>
        <p class="post-meta">{{ poem.date | date: '%B %-d, %Y — %H:%M' }}</p>
      </li>
{% endfor %}
</ul>