---
layout: default
title: ZettelWiki
---

# Welcome to ZettelWiki

Here are my Zettels:

## Recent Zettels (With Valid Dates)

<ul>
  {% assign dated_pages = site.pages | sort: 'date' | reverse %}
  {% for page in dated_pages %}
    {% if page.date and page.url contains '/' and page.title %}
      <li>
        <a href="{{ site.baseurl }}{{ page.url }}">{{ page.title }}</a> - {{ page.date | date: "%B %d, %Y" }} | Inspiration: {{ page.inspiration }}
      </li>
    {% endif %}
  {% endfor %}
</ul>

## Other Zettels (Without Valid Dates)

<ul>
  {% for page in site.pages %}
    {% if page.date == null and page.url contains '/' and page.title %}
      <li>
        <a href="{{ site.baseurl }}{{ page.url }}">{{ page.title }}</a> - Date: Unknown | Inspiration: {{ page.inspiration }}
      </li>
    {% endif %}
  {% endfor %}
</ul>

