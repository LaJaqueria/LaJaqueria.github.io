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

    <div class="col-md-4">
	<h2>Te apuntas?</h2>
	Las sesiones temáticas están destinadas a la puesta en común de un conjunto de herramientas (mentales, digitales, ...) que nos 
	permitan trabajar juntos. La asistencia es libre para socios y estamos abiertos a la participación 
	(exponer proyectos, difundir tecnologías de preferencia, ...) de todas aquellas personas que quieran
	integrarse en nuestra comunidad.
    <h2>Calendario</h2>
    Para que Estes al día, hemos creado un calendario donde publicaremos todas las actividades y puedas ver los próximos eventos.
    [Calendario Actividades La Jaquería](https://calendar.google.com/calendar/embed?src=b9017a8a105cdeb2d9139e741371d808f9daeef9de74a4d8a1be7606c1f5223f%40group.calendar.google.com&ctz=Europe%2FMadrid).
    <iframe src="https://calendar.google.com/calendar/embed?src=b9017a8a105cdeb2d9139e741371d808f9daeef9de74a4d8a1be7606c1f5223f%40group.calendar.google.com&ctz=Europe%2FMadrid" style="border: 0" width="800" height="600" frameborder="0" scrolling="no"></iframe>
    </div>

</div>
