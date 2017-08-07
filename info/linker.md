---
permalink: /
---

{% assign dict = site.pages | group_by_exp:"item", "item.url | remove_first: '/' | split: '/' | first" %}

{% for item in dict %}
  {% if item.name == 'info' %}
    {% for items in item.items %}
      {% if items.name != '\_linker.md' %}
{% include_relative {{ items.name }} %}
      {% endif %}
    {% endfor %}
  {% endif %}
{% endfor %}
