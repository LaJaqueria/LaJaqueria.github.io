---
layout: page
title: Etiquetas
permalink: /etiquetas/
---


### Categorías

<div id="archives">
<ul>
{% for category in site.categories %}
  {% capture category_name %}{{ category | first }}{% endcapture %}
    <li><a href="/category/{{category_name}}">{{ category_name }}</a></li>
    <p></p>
{% endfor %}
</ul>
</div>
