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

Una vez hecho esto, ya podemos utilizar nuestra placa usando MicroPython a través de UPyCraft; para ello usaremos el menú _Tools->port_; observaremos en la parte inferior el simbolo ```>>>``` esto quiere decir que la consola esta lista y esperando ordenes.

## 4.  Primeros pasos con MicroPython

MicroPython es una implementación del lenguaje de programación python, que esta orientada a dispositivos con muy pocos recursos; como pueden ser microcontroladores.

Micropython se compone de un compilador y un interprete en tiempo de ejecución que funciona en el hardware de un microcontrolador.

Desde que apareció a través de un KickStater por 2013, se ha podido exportar a distintas plataformas y arquitecturas basadas en ARM. Como puede ser Arduino, ESP8266, ESP32 y otras placas como la llamada [Microbit](https://microbit.org/es/) de la BBC.

Tras haber instalado MicroPython en nuestra placa, vamos a utilizar UPyCraft para poder comunicarnos con el interprete de MicroPython.

![upycraftrepl](/recursos/2019-04-27/upycraftrepl.PNG)

Como podemos ver en la anterior figura, en la parte inferior, tenemos el interprete Python en el cual podemos escribir en tiempo de ejecución para que nuestra placa lo ejecute.

También podemos ver los ficheros que tenemos en local y en nuestra placa. Esto lo podemos ver en la parte izquierda donde en la carpeta _workspace_ podemos ver los ficheros locales (tendremos que definir una carpeta donde estara el workspace); y en la carpeta _device_ podemos ver los ficheros que hay en nuestra placa.

**NOTA:** En caso de no ver ningún fichero seleccionar la opción del menú _File-> Reflush Directory_.

En la parte derecha también podemos ver una barra de herramientas con todo lo necesario para trabajar con MicroPython; como puede ser el ejecutar un fichero, guardar,etc...

Una vez nos hemos familiarizado con el entorno, vamos a crear nuestro primer fichero python para MicroPython. Para ello creamos un nuevo fichero; que llamaremos _hola.py_ pulsando el menú _File->new_ o el botón de la derecha.

Escribimos el siguiente código:

```python

from machine import Pin
from time import sleep
#El Pin del led es el 2 que corresponde al GPIO2

ledpin=2
pin = Pin(ledpin, Pin.OUT)
while True:
  pin.value(1)
  sleep(1)
  pin.value(0)
  sleep(1)
```

Una vez que hemos terminado y guardado nuestro fichero, vamos a subirlo a la placa; pulsando en el menú _Tools->DownloadAndRun_ o en la opción de la barra de herramientas (También es la tecla F5).

Observaremos como el led que trae la propia placa parpadea. Esto quiere decir que nuestro programa se esta ejecutando en MicroPython. Para parar el programa, pulsar ctrl+C.

Hemos podido ver que en el anterior código se usaba la clase ```Pin``` la cual nos permite tanto dar un valor como leer un pin como entrada o como salida. 

La función ```sleep``` para la ejecución tantos segundos como se especifica.

Una vez nos hemos familiarizado con MicroPython, vamos a hacer nuestro primer cirtuito; donde crearemos 2 leds que parpadean con distinta intensidad.

Por lo que necesitaremos:

* Placa ESP32 o ESP8266.
* 2 BreadBoard.
* 2 Resistencias de 220Ohmios minimo.
* 2 Leds
* Cables


Seguidamente mostramos el montaje:

![esquema1](/recursos/2019-04-27/esquema1.png)

Y este es el código que permite que los 2 leds parpadeen:

```python

from machine import Pin
from time import sleep

ledpin=2
ledpin2=4
pin = Pin(ledpin, Pin.OUT)
pin2 = Pin(ledpin2, Pin.OUT)
while True:
  pin.value(1)
  pin2.value(1)
  sleep(1)
  pin.value(0)
  pin2.value(0)
  sleep(1)

```
## 5. Botones con MicroPython

Tras ver como utilizar la salida a través de los leds; vamos a tratar de utilizar pulsadores para poder utilizar las entradas del microcontrolador. En este caso también utilizaremos la clase ```Pin```pero en este caso configuraremos cada puerto en modo IN.

Seguidamente mostramos un nuevo montaje:

![montaje2](https://raw.githubusercontent.com/pythoncanarias/upython/master/imagenes/button.png)

y Aquí se muestra el Código:

```python
from machine import Pin
import time

button=Pin(2,Pin.IN)
led=Pin(16,Pin.OUT)

while True:
    state=button.value()
    led.value(state)
    time.sleep(0.5)
```

Tras ver este ejercicio, aquí teneís otro montaje:

![montaje2](/recursos/2019-04-27/montaje2.png)

El código tendréis que hacerlo vosotros...

## 6. Proyecto Final: Medidor de Temperatura y Humedad

Tras habernos familiarizado con MicroPython, vamos a crear un pequeño medidor de Temperatura y Humedad; usando el componente DHT el cual permite medir temperatura y humedad de forma sencilla.

Para este proyecto necesitaremos:

* 1 Placa ESP32 o ESP8266.
* 2 BreadBoard
* 1 DHT11 o DHT22.
* 1 Resistencia 220Ohmios
* 1 Led
* cables

Seguidamente se muestra el Montaje:

![montaje3](/recursos/2019-04-27/montaje3.png)

Como podeis ver, en este montaje usaremos el led para indicar que la humedad o temperatura ha subido.

Aquí esta el código fuente de este proyecto:

```python
import dht
from machine import Pin

pindht = Pin(0)
ledpin = Pin(2, Pin.OUT)
dht11 = dht.DHT11(pindht)

while True:
  temp = dht11.temperature()
  hum = dht11. humidity()
  if temp > 24 or hum > 55:
    ledpin.value(1)
  else:
    ledpin.value(0)

```

## Referencias

* [Python Canarias](https://github.com/pythoncanarias/upython)
* [Documentacion MicroPython](https://docs.micropython.org/en/latest/index.html)
* [UPyCraft](https://github.com/DFRobot/uPyCraft)