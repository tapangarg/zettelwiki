# Welcome to ZettelWiki

Here are my Zettels:

{% for page in site.pages %}
- [{{ page.title }}]({{ page.url }})
{% endfor %}
