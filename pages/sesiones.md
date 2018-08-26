---
layout: page
title: Sesiones
permalink: /sesiones/
---

<div class="row">
    <div class="col-md-6">

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

    <div class="col-md-6">
        <h2>Calendario de actividades</h2>
        <p><a style="font-weight: bold;" title="añádeme a tu aplicación de calendario" href="{{site.info-asociacion.link_calendario}}">Subscríbete a nuestro calendario</a> (usando <a style="font-weight: bold;" title="añádeme a tu aplicación de calendario" href="{{site.info-asociacion.link_calendario}}">este enlace</a>) para estar siempre informado de todas las actividades de la Jaquería</p>
        <iframe src="{{site.info-asociacion.iframe_calendario}}"  width="100%" height="400" frameborder="0" ></iframe>

    </div>
</div>
