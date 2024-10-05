---
layout: default
title: ZettelWiki
---

# Welcome to ZettelWiki

Here are my Zettels (Most Recent First):

<ul>
  {% assign sorted_pages = site.pages | sort: 'date' | reverse %}
  {% for page in sorted_pages %}
    {% if page.url contains '.md' and page.title %}
      <li>
        <a href="{{ page.url }}">{{ page.title }}</a> - {{ page.date | date: "%B %d, %Y" }}
      </li>
    {% endif %}
  {% endfor %}
</ul>
