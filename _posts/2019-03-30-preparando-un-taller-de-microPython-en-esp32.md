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

## 3. Flashear la placa

Una vez tenemos ya preparado nuestro entorno y nuestra placa, vamos a pasar a instalar microPython en ella. Normalmente estos microcontroladores vienen con LUA instalado; pero nosotros vamos a instalar MicroPython para poder utilizarlo en nuestros desarrollos.

Para este apartado necesitaremos un cable USB (MicroUSB) que necesitaremos conectar a nuestro Portatil.

En primer lugar, vamos a descargar la última versión de MicroPython que podemos encontrar en los siguientes enlaces (Dependiendo del modelo de nuestra placa):

* [ESP8266](https://micropython.org/download#esp8266)
* [ESP32](https://micropython.org/download#esp32)

Una dez descargado vamos a utilizar UPyCraft para instalar la imagen de MicroPython en nuestra placa.

Para flashear nuestra placa desde UPyCraft usaremos el menu de _Tools->BurnFirmWare_.

![BurnFirmware](/recursos/2019-04-27/burnfirmware.PNG)

Como podemos ver en la anterior figura, tenemos que tener en cuenta los siguientes casos:

* **board**: Modelo de la placa (ESP32 o ESP8266).
* **burn_addr**: Indica la dirección desde la cual se empezara a flashear. Para la ESP8266 dejar en 0x0 pero es muy importante que para la **ESP32 se debe dejar en la dirección 0x1000**.
* **erase_flash**: Indica si se debe borrar antes la memoria de la placa. La primera vez que lo hagamos le indicaremos que si.
* **com**: Indica el puerto a utilizar. Pondremos el que tiene la placa asignado.

En el apartado _Firmware Choose_ Se pondra la versión Users y se pondrá la ruta donde se encuentra la imagen que hemos descargado.

**NOTA 1:** Se puede usar la implementación de UPyCraft.

**NOTA 2:** En caso de ser necesario se dejan aquí los pasos para flashear la placa de forma manual.

1. Abrir una terminal
2. Instalar el siguiente modulo de Python (Requiere Pip):

```bash
 pip install esptool
```
3. Ejecutar el siguiente comando para borrar la memoria

```bash
esptool.py --port COM3 erase_flash
```

**NOTA 3:** En el anterior comando cambiar COM3 por el puerto que corresponda en nuestro equipo. Esto puede cambiar dependiendo del equipo y del sistema operativo.

4. Ejecutar el siguiente comando para flashear la placa

```bash
esptool.py --port COM3 --baud 115200 write_flash --flash_size=detect 0 <imagendescargada>
```

**NOTA 4:** < Imagen descargada> se refiere a la ruta donde tengamos la imagen que hemos descargado de MicroPython.

Una vez hecho esto, ya podemos utilizar nuestra placa usando MicroPython a través de UPyCraft; para ello usaremos el menú _Tools->port_; observaremos en la parte inferior el simbolo _>>>_ esto quiere decir que la consola esta lista y esperando ordenes.
