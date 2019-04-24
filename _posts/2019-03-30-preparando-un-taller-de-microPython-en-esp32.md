---
layout: post
#Datos del post
title: "Preparando un taller de MicroPython en ESP32"

#Fecha
date: 2019-03-30T18:15

category: proyectos
user: varios
---

# Taller de MicroPython Del día 27 de Abril

La revolución Ardunio se expande con estos módulos programables en Python. En esta página se encontrarán apuntes y ayuda para el taller del día 27 de Abril de 2019. Celebrado en el [Colegio Liceo Erasmus](https://lajaqueria.org/actividades/2019/04/27/introduccion-a-micropython.html).

Contenido del tema:

1. Instalación del entorno
2. ESP32 o ESP8266 
3. Flashear la placa (AKA. Instalar MicroPython en ella)
4. Primeros pasos en MicroPython
5. Botones con Micropython
6. Proyecto Final: Medidor de Temperatura y Humedad

## 1  Instalación del Entorno

En primer lugar, vamos a preparar nuestro entorno para poder programar los microcontroladores ESP8266 o ESP32. Para ello necesitaremos instalar los siguientes programas antes de poder instalar todo nuestro entorno:

* [Python 3.4 o superior](https://www.python.org/downloads/release/python-373/)

**NOTA**: Es importante añadir al Path cuando nos lo pida el instalador de Python.

* [UPyCraft](https://github.com/DFRobot/uPyCraft)

UPyCraft es un editor de texto orientado para MicroPython que no requiere instalación y consume muy pocos recursos; solo necesita tener instalado Python 3.4 o superior.

Para instalarlo simplemente descargar la version 1.0 del sistema operativo que necesitemos.

**NOTA para Linux:** Quizas sea necesario dar permisos de ejecución al fichero que descarguemos ```chmod +x <nombrefichero>```.

Una vez todo configurado, ya podremos utilizarlo.

![UPyCraft](/recursos/2019-04-27/upycraft.PNG)

**NOTA**: QUizas os salga un aviso de que debéis instalar una fuente. Podéis darle a OK.

Una vez tenemos configurado nuestro entorno, vamos a pasar a ver nuestras placas.

## 2 ESP32 o ESP8266

Los microcontroladores ESP32 o ESP8266, son placas programables que tienen una cracterística principalmente; cuentan con conectividad Wifi y son de muy bajo coste.

Estas placas permiten ser programadas con una variedad de lenguajes; como puede ser Arduino, Lua, C, Node.js y por supuesto Python. Estas placas son muy sencillas de utilizar ya que tienen una gran comunidad detras lo cual hace que tenga mucha documentación.

Tanto la ESP8266 y la ESP32, permiten ser programadas con Python; más concretamente con su implementación MicroPython.

Cuando nos referimos a estos dos modelos, hablamos concretamente de los chips que tienen internamente; ya que existen gran variedad de modelos de distintos fabricantes.

La principales diferencias entre la ESP8266 y la ESP32 son:

* La ESP32 tiene doble nucleo
* La ESP32 tiene soporte para BlueTooth
* La ESP32 tiene mejor conectividad.

Para ver mejor las caracteristicas que tienen estas placas, dejamos aquí 2 enlaces con la información de cada una de ellas.

* [ESP8266](https://en.wikipedia.org/wiki/ESP8266)
* [ESP32](https://en.wikipedia.org/wiki/ESP32)

Seguidamente vamos a dejar el PinOut de las 2 placas (este puede cambiar según el fabricante); en este caso nos basamos en placas del fabricante NodeMCU.

![NodeMCU](/recursos/2019-04-27/nodemcu.png)

**NOTA**: Consultar el fabricante para poder saber el pinout.

