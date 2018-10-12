---
layout: page
title: Sesiones
permalink: /sesiones/
---

<div class="row">
    <div class="col-md-8">

        <h2>Próximos eventos</h2>
        {% assign curDate = site.time | date: "%Y-%m-%d" %}

        <ul>
            {% for post in site.categories.actividades reversed %}
            {% assign date = post.date | date: "%Y-%m-%d" %}
            {% if date >= curDate %}
            <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
            {% endif %}
            {% endfor %}
        </ul>

        <h2>Anteriores eventos</h2>
        <ul>
            {% for post in site.categories.actividades %}
            {% assign date = post.date | date: "%Y-%m-%d" %}
            {% if date < curDate %}
            <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
            {% endif %}
            {% endfor %}
        </ul>
    </div>

</div>
