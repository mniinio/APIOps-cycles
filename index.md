---
title: APIOps&reg; Cycles table of contents
---

{% for item in site.data.toc %}
<h3>{{ item.title }}</h3>
  <ul>
    {% for entry in item.subfolderitems %}
       <li><a href="{{ entry.url }}">{{ entry.page }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}

