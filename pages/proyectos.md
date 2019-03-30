---
layout: page
permalink: /proyectos/
---
En estas páginas se recoge el cuaderno de bitacora de cada uno de los proyectos en los que estamos trabajando. 

<div class="posts">
  {% for post in site.categories.proyectos %}
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
