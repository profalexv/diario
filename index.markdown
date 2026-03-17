---
layout: default
title: Início
---

{% for post in paginator.posts %}
## [{{ post.title }}]({{ post.url }})
<small>{{ post.date | date: "%d/%m/%Y" }} {% if post.categories.size > 0 %} · {{ post.categories | join: ", " }}{% endif %}</small>

{{ post.excerpt }}

---
{% endfor %}

{% if paginator.total_pages > 1 %}
<div>
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path }}">← Mais recentes</a>
  {% endif %}
  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path }}">Mais antigas →</a>
  {% endif %}
</div>
{% endif %}
