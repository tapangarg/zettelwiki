---
layout: default
title: ZettelWiki
paginate: true  # Enable pagination for this page
---

# Welcome to ZettelWiki

Here are my Zettels:

## Recent Zettels (With Valid Dates)

<ul>
  {% for post in paginator.posts %}
    {% if post.date and post.url contains '/' and post.title %}
      <li>
        <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%B %d, %Y | %I:%M %p" }} | Inspiration: {{ post.inspiration }}
      </li>
    {% endif %}
  {% endfor %}
</ul>

## Other Zettels (Without Valid Dates)

<ul>
  {% for post in site.pages %}
    {% if post.date == null and post.url contains '/' and post.title %}
      <li>
        <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a> - Date: Unknown | Inspiration: {{ post.inspiration }}
      </li>
    {% endif %}
  {% endfor %}
</ul>

<!-- Pagination Controls -->
<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path | prepend: site.baseurl }}">&laquo; Previous</a>
  {% endif %}

  {% for page in (1..paginator.total_pages) %}
    {% if page == paginator.page %}
      <span>{{ page }}</span>
    {% else %}
      <a href="{{ paginator.page_path | prepend: site.baseurl | replace: ':num', page }}">{{ page }}</a>
    {% endif %}
  {% endfor %}

  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path | prepend: site.baseurl }}">Next &raquo;</a>
  {% endif %}
</div>


