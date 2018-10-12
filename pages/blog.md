---
layout: page
permalink: /blog/
---

<div class="posts">
  {% for post in site.posts.post %}
    <article class="post">

      <h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>
      <h4>{{post.user}} - {{ post.date | date: "%B %e, %Y" }}</h4>

      <div class="entry">    
        {% if post.description %}
          {{ post.description }}
        {% else %}
          {{ post.excerpt }}
        {% endif %}
      </div>

      <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More</a>
    </article>
  {% endfor %}
</div>
