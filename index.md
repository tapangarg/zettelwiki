# Welcome to ZettelWiki

Here are my Zettels:

<ul>
  {% for page in site.pages %}
    {% if page.url != '/' and page.title %}
      <li>
        <a href="{{ site.baseurl }}{{ page.url }}">{{ page.title }}</a>
      </li>
    {% endif %}
  {% endfor %}
</ul>
