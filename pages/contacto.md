---
layout: page
title: Contacto
permalink: /contacto/
---
<div class="containter">
  <div class="row">
    <div class="col">
    asdfasdf
    </div>
    <div class="col-4">

      <h4>Redes sociales</h4>
      {% include svg-icons.html %}

      <h4>Información de contacto</h4>

      <div class="row">
        <div class="col-xs">
        <i class="svg-icon-contact location"></i>
        </div>
        <div class="col-lg">
        {{site.info-asociacion.calle}} {{site.info-asociacion.codigo-postal}}
        </div>
      </div>

      <div class="row">
        <div class="col-xs">
        <i class="svg-icon-contact calendar"></i>
        </div>
        <div class="col-lg">
          {{site.info-asociacion.horario}}
        </div>
      </div>

      <div class="row">
        <div class="col-xs">
        <i class="svg-icon-contact mail"></i>
        </div>
        <div class="col-lg">
          {{site.footer-links.email}}
        </div>
      </div>

      <div class="row">
        <div class="col-xs">
        <i class="svg-icon-contact phone"></i>
        </div>
        <div class="col-lg">
          {{site.info-asociacion.telefono}}
        </div>
      </div>
    </div>
 </div>
</div>
