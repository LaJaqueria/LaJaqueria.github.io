---
layout: post

title: Revelado digital de fotografías RAW
description: Podríamos pensar que el proceso de generar el archivo jpg a partir de los datos del sensor CCD de nuestra cámara es un proceso algorítmico con poco margen de maniobra. En este artículo veremos por qué esto no es así.
date: 2024-02-17
author: "Emilio LB"
category: blog
user: La Jaquería
---

# Introducción
A priori podríamos pensar que el proceso de generar el archivo jpg a partir de los datos del sensor CCD de nuestra cámara es un proceso algorítmico con
poco margen de maniobra. En realidad, se trata de un proceso que es una mezcla de ciencia y arte y que con el suficiente entrenamiento, podemos conseguir 
resultados mucho mejores haciéndolo a mano que dejando que la cámara lo haga de forma automática.

Una foto es una imagen bidimensional (un archivo jpg) que representa una escena de un modo similar a cómo lo percibe nuestro sentido de la vista.
El sensor de nuestra cámara funciona de una forma muy distinta a cómo lo hace nuestra vista, es por esto que es necesario realizar un procesamiento 
a los datos recogidos por el sensor para obtener una imagen similar a lo que vemos nosotros. Este proceso lo vamos a realizar con dos herramientas, 
empezaremos abriendo la foto con Raw Therapee, dónde realizaremos el procesado básico que consiste en 3 pasos: Interpolación de píxeles, Ajuste de 
blancos y Reescalado de niveles. Una vez realizados estos tres pasos, pasaremos la foto a GIMP, y realizaremos dos ajustes finales que mejorarán nuestra 
foto, Ecualizado y enfoque. Veamos cada uno de estos pasos en detalle.

# Dedicatoria

Sirva este tutorial de humilde homenaje a mi abuelo Joaquín 
quién me enseñó a disparar en manual y revelar con photoshop

# 1. Interpolación de Píxeles (Demosaicing)
El sensor CCD de nuestra cámara está formado por una cuadrícula de celdas fotosensibles. Si por ejemplo tenemos una cámara de 10 megapíxeles, tendremos 
un sensor formado por diez millones de celdas fotosensibles. Cada una de estas celdas genera una señal eléctrica dependiente de la cantidad de luz que 
haya recibido. Para captar una foto en color, delante de cada una de las celdas se coloca un filtro de UNO SÓLO de los colores primarios (rojo, verde, azul). 
Es decir delante de la primera celda hay un filtro azul, delante de la segunda un filtro verde, etc. Por cada una de éstas celdas, tendremos que generar 
un píxel. Dado que cada celda sólo capta la luz de un determinado color, y un píxel está formado por los tres colores primarios, tenemos que utilizar 
los datos de las celdas adyacentes para calcular los dos componentes que nos faltan para formar cada píxel. Esto se hace utilzando algoritmos que se basan en 
una herramienta matemática llamada interpolación. En casi todas las situaciones el algoritmo que mejor funciona es el llamado AMaZE, aunque tiene una 
limitación: Si nuestra imagen tiene un nivel de ruido alto (lo que ocurre cuándo usamos un ISO alto en nuestra cámara) genera artefactos de color (rectangulitos 
rojos, verdes y azules). Como recomendación general se debe usar siempre que se pueda el nivel ISO más bajo que tenga nuestra cámara. Además de dicho algoritmo, 
también tenemos LMMSE y IGV, que son algoritmos optimizados para imágenes con alto nivel de ruido. Por último tenemos RCD, que está optimizado para imágenes 
con muchas formas circulares. El resto de algoritmos incluídos en Raw Therapee son más antiguos y en general no los usaremos.

Abramos nuestra foto con Raw Therapee ([Aquí puedes descargar la usada de ejemplo](/recursos/2024-02-18/IMGP0001.PEF).) , pongamos un par de lupas 
al 300% de zoom y vayamos a la pestaña Raw. Aquí podemos controlar que algoritmo de interpolación se utiliza y sus posibles parámetros. 
Si estamos ante una foto tomada con bajo ISO, dejaremos AMaZE, si tenemos una foto tomado con un nivel alto de ISO, probaremos con LMMSE ó IGV. 
En el caso de una fotografía en la que predominen las formas circulares, probaremos con RCD. El resto de parámetros de configuración los dejamos por defecto.

![Captura 1](/recursos/2024-02-18/captura_01.png)
