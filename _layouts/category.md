---
layout: default
---

<div class="blog list">
    <h2>Publicaciones sobre {{ page.tag }}</h1>

    <ul>
    {% for post in site.categories[page.tag] %}
      <li>{{ post.date | date_to_string }} - <a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></li>
      <p></p>
    {% endfor %}
</div>
