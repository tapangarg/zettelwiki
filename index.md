---
layout: default
title: ZettelWiki
pagination: true
---

# Welcome to ZettelWiki

Here are my Zettels:

## Recent Zettels (With Valid Dates)

<ul>
  {% assign dated_pages = paginator.posts | sort: 'date' | reverse %}
  {% for page in dated_pages %}
    {% if page.date and page.url contains '/' and page.title %}
      <li>
        <a href="{{ site.baseurl }}{{ page.url }}">{{ page.title }}</a> - {{ page.date | date: "%B %d, %Y | %I:%M %p" }} | Inspiration: {{ page.inspiration }}
      </li>
    {% endif %}
  {% endfor %}
</ul>

## Other Zettels (Without Valid Dates)

<ul>
  {% for page in paginator.posts %}
    {% if page.date == null and page.url contains '/' and page.title %}
      <li>
        <a href="{{ site.baseurl }}{{ page.url }}">{{ page.title }}</a> - Date: Unknown | Inspiration: {{ page.inspiration }}
      </li>
    {% endif %}
  {% endfor %}
</ul>

<!-- Pagination Links -->
<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path }}" class="btn">Previous</a>
  {% endif %}
  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path }}" class="btn">Next</a>
  {% endif %}
</div>


