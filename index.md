---
layout: default
title: ZettelWiki
---

# Welcome to ZettelWiki

Here are my Zettels:

<ul>
  {% for page in site.pages %}
    {% if page.url != '/' %}
      <li>
        <a href="{{ page.url }}">{{ page.title }}</a>
      </li>
    {% endif %}
  {% endfor %}
</ul>
