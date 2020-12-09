---
layout: post
#Datos del post
title: "un robot DIY como plataforma educativa"

#Fecha
date: 2020-12-08T18:15

category: proyectos
user: varios
---

## un robot DIY como plataforma educativa

A partir de <a href="https://www.ottodiy.com/#build-your-own-robot">OTTO</a>, un clon libre de Zowi, un robot bipedo humanoide puede ser programado con una adaptación de Scratch. Es barato, simple y vistoso.

...y si lo utilizasemos como base para nuestas acciones de apropiación tecnológica, para todas las edades?

![OTTO como IronMan](/recursos/varios/otto_ironman.jpg)

...
actualizacion 20201208
OTTODIY ya se puede utilizar con un [ESP32](https://github.com/OttoDIY/OttoDIYESP) como cerebro: wifi, bluetooth, mas memoria, mas capacidad...

...aun no existe una placa de expansion IO para ESP32, por lo que habria que integrar algun tipo de breadboard en la "cabeza"
mas informacion del proyecto oficial en [wikifactory](https://wikifactory.com/+OttoDIY/otto-diy).

...
materiales para un taller de robotica como plataforma educativa:
(por participante)

- las piezas sacadas en [impresion 3D](https://wikifactory.com/+OttoDIY/otto-diy/files/3Dprint) (cabeza, cuerpo, 2 pies, 2 piernas). (1€)

- 4x [servo motor ](https://es.aliexpress.com/item/32442393099.html?spm=a2g0s.9042311.0.0.274263c0ImuGT6). (7€)

- arduino [nano](https://es.aliexpress.com/item/32418709242.html?spm=a2g0s.9042311.0.0.274263c0ImuGT6). (3€)

- [placa expansion](https://es.aliexpress.com/item/2044200735.html?spm=a2g0o.productlist.0.0.4abd7e611pzwUZ&algo_pvid=5b97c406-70b8-4fbb-b855-d98154891a62&algo_expid=5b97c406-70b8-4fbb-b855-d98154891a62-7&btsid=2100bb5116074218553922373e0fa5&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_) arduino nano. (2€)

- sensor de [ultrasonidos](https://es.aliexpress.com/item/1859102668.html?spm=a2g0s.9042311.0.0.274263c0ImuGT6). (1€)

- [Max7219](https://es.aliexpress.com/item/4000263982956.html?spm=a2g0o.productlist.0.0.59a73093pqYLL0&algo_pvid=dc222d33-b40c-4b8f-bd5e-bbab487230ec&algo_expid=dc222d33-b40c-4b8f-bd5e-bbab487230ec-8&btsid=2100bdd516074236524446697e3cf8&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_) matriz led 8x8. (2.5€)

- [porta baterias](https://es.aliexpress.com/item/32971481065.html?spm=a2g0o.productlist.0.0.5d0b7cbfyKCHTD&algo_pvid=27b0b28c-ff49-490c-94b8-7c2fa193705b&algo_expid=27b0b28c-ff49-490c-94b8-7c2fa193705b-14&btsid=2100bb4916075060180435326e8a9d&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_) (1.5€)

- 4 pilas AA (2€)

- [interruptor](https://es.aliexpress.com/item/32424649963.html?spm=a2g0o.productlist.0.0.733b1a7bGDjmq9&algo_pvid=d6eb05d0-e7e2-4c5d-ba26-454533e9ac70&algo_expid=d6eb05d0-e7e2-4c5d-ba26-454533e9ac70-11&btsid=2100bb4716075061109487781e9ddb&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_) (1€)

coste total de los componentes: 21€

en caso de utilizar esp32:
- mini [breadboard](https://es.aliexpress.com/item/32914730439.html?spm=a2g0o.productlist.0.0.65c0417cmA1AEd&algo_pvid=50e6fcf6-f347-4932-a5f3-7786cd179959&algo_expid=50e6fcf6-f347-4932-a5f3-7786cd179959-13&btsid=2100bb5116074240403235021e12ac&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_). (0.6€)

- [esp32](https://es.aliexpress.com/item/1005001757645011.html?spm=a2g0o.productlist.0.0.757770c22F1ExH&algo_pvid=77c764db-1042-4c1b-9d55-73b9826bf9c2&algo_expid=77c764db-1042-4c1b-9d55-73b9826bf9c2-3&btsid=2100bdd016074241440817161e292c&ws_ab_test=searchweb0_0,searchweb201602_,searchweb201603_). (3€)



el [kit](https://www.ottodiy.com/store/products/49452), tal y como lo venden en ottodiy son 60€. 


formato para un taller: 

- seria necesario contar con un PC por participante, con el [blocky](https://github.com/OttoDIY/blockly/releases/download/v1.3.0/OttoBlockly-Setup-1.3.0.exe) instalado y funcionando. O en su defecto, acceso a la [web de blocky](https://ottodiy.github.io/blockly/www/).

- duracion 3 horas. 

- los participantes reciben una bolsa con todos los componentes para montar un robot

- primera parte: montaje fisico de los componentes. 

- segunda parte: conexion con blocky,  testeo del robot

- tercera parte: iniciacion a la programacion "con bloques"

- al terminar el taller, cada participante se lleva su robot terminado 

este taller es el esquema basico de varias vias posibles. En la web de [ottoschool](https://ottoschool.com/en/all-courses/) tienen un catalogo de cursos, a 40€ cada uno que cubren, como cursos de iniciacion:

 - montaje del robot
 - programacion con scratch
 - diseño 3D a partir de los modelos 
 - iniciacion a la impresion 3D 
 - iniciacion a la Interligencia Artificial 
 - diseño de Apps para interactuar 
 - iniciacion a la mecanica 
