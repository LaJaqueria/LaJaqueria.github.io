---
layout: page
permalink: /blog/
---

# Blog

Aquí puedes encontrar noticias y artículos relacionados con las temáticas que trabajamos en la jaquería.

<div class="posts">
  {% for post in site.categories.blog %}
    <article class="post">

      <h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>
      <div class="entry">    
        {% if post.description %}
          {{ post.description }}
        {% else %}
          {{ post.content | strip_html | truncatewords: 100 }}
        {% endif %}
      </div>

      <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Leer más</a>
    </article>
  {% endfor %}
</div>
