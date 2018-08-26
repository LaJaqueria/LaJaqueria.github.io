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
        <p><a style="font-weight: bold;" title="añádeme a tu aplicación de calendario" href="http://bit.ly/calendario-HackLabAl">Subscríbete a nuestro calendario</a> (usando <a style="font-weight: bold;" title="añádeme a tu aplicación de calendario" href="http://bit.ly/calendario-HackLabAl">este enlace</a>) para estar siempre informado de todas las actividades ámbito tecnólogo de Almería.</p>
        <iframe src="https://www.google.com/calendar/embed?showTitle=0&amp;showPrint=0&amp;mode=AGENDA&amp;wkst=2&amp;src=eohual6srvr2l4oqa1ujevad9s%40group.calendar.google.com"  width="100%" height="400" frameborder="0" ></iframe>

    </div>
    <div class="col-md-6">
        <h2>Circular informativa</h2>
        <p>De vez en cuando enviamos un aviso informativo por correo electrónico. Sólo cuando realmente tenemos algo importante que compartiros. Tiene muy muy poco tráfico y puedes darte de baja cuando quieras

        <a style="font-weight: bold;"  href="http://us13.campaign-archive2.com/home/?u=3f216616d53a9b1cbbc71fae9&id=0615a13418" title="View previous campaigns">(ejemplos de envíos anteriores)</a>.</p>
	<div id="mce-responses" class="clear">
		<div class="response" id="mce-error-response" style="display:none"></div>
		<div class="response" id="mce-success-response" style="display:none"></div>
	</div>    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->


        <!-- Begin MailChimp Signup Form -->
<link href="//cdn-images.mailchimp.com/embedcode/slim-10_7.css" rel="stylesheet" type="text/css">
<style type="text/css">
	#mc_embed_signup{background:#fff; clear:left; font:14px Helvetica,Arial,sans-serif; }
	/* Add your own MailChimp form style overrides in your site stylesheet or in this style block.
	   We recommend moving this block and the preceding CSS link to the HEAD of your HTML file. */
</style>
<div id="mc_embed_signup">
<form action="//hacklabalmeria.us13.list-manage.com/subscribe/post?u=3f216616d53a9b1cbbc71fae9&amp;id=0615a13418" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
    <div id="mc_embed_signup_scroll">

	<input type="email" value="" name="EMAIL" class="email" id="mce-EMAIL" placeholder="dirección de correo-e" required>
    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;" aria-hidden="true"><input type="text" name="b_3f216616d53a9b1cbbc71fae9_0615a13418" tabindex="-1" value=""></div>
    <div class="clear"><input type="submit" value="Suscribir" name="subscribe" id="mc-embedded-subscribe" class="button"></div>
    </div>
</form>
</div>

<!--End mc_embed_signup-->

    </div>
</div>
