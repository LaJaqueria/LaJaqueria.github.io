---
layout: post
#Datos del post
title: "Sensor de CO2"

#Fecha
date: 2020-09-26T18:15

category: proyectos
user: varios
---

## Sensor Dioxido de Carbono

Como uno de los indicadores de la eficiencia de la ventilacion de un lugar cerrado, como un aula, una oficina, la medida del nivel de CO2 es una ayuda posible para las medidas destinadas a limitar la expansion del Covid-19.

Se trata de preparar dos elementos: 
- un prototipo discreto con conectividad para envio de datos via wifi
- un servicio en Home Assistant para centralizar esa informacion

el matiz "discreto" deberia permitir su instalacion en entornos "no seguros", o no gestionados.

De esta forma se puede desplegar un conjunto de sensores para la medicion de nivel de CO2, y su seguimiento desde Home Assistant

---
algunas referencias:

[sensor de calidad del aire](https://cdn-learn.adafruit.com/downloads/pdf/adafruit-ccs811-air-quality-sensor.pdf) que mide la "cantidad equivalente de CO2"
[el mismo sensor, en aliexpress](https://es.aliexpress.com/item/4000848337164.html)

[otro sensor](https://es.aliexpress.com/item/4000854395292.html), que funciona en base a otro efecto, y es mas caro.

[otro sensor mas](https://www.co2meter.com/products/k-30-co2-sensor-module) aun mas caro. En el esta basado esto [instructables](https://www.instructables.com/id/Track-CO2-Carbon-Dioxide-Levels-With-Ardunio-and-C/).
