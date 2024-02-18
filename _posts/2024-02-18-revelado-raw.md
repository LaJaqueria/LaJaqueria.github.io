---
layout: post

title: Revelado digital de fotografías RAW
description: Podríamos pensar que el proceso de generar el archivo jpg a partir de los datos del sensor CCD de nuestra cámara es un proceso algorítmico con poco margen de maniobra. En este artículo veremos por qué esto no es así.
date: 2024-02-18
author: "Emilio LB"
category: blog
user: La Jaquería
---

# Introducción
A priori podríamos pensar que el proceso de generar el archivo jpg a partir de los datos del sensor CCD de nuestra cámara es un proceso algorítmico con
poco margen de maniobra. En realidad, se trata de un proceso que es una mezcla de ciencia y arte y que con el suficiente entrenamiento, podemos conseguir 
resultados mucho mejores haciéndolo a mano que dejando que la cámara lo haga de forma automática. En este artículo vamos a usar [Raw Therapee](http://rawtherapee.com/) 
y [GIMP](https://www.gimp.org/). Ambas son herramientas libres disponibles para Linux, Windows y Mac OS. Si estamos usando Linux, usaremos 
nuestro gestor de paquetes habitual para instalarlas desde los repositorios de la distro. Para el caso de Windows, nos iremos a la web de 
cada uno de los dos programas y descargaremos el instalador. Los usuarios de Mac, bueno, que usen el sistema que sea que se use en Mac OS para instalar 
software.

Una foto es una imagen bidimensional (un archivo jpg) que representa una escena de un modo similar a cómo lo percibe nuestro sentido de la vista.
El sensor de nuestra cámara funciona de una forma muy distinta a cómo lo hace nuestra vista, es por esto que es necesario realizar un procesamiento 
a los datos recogidos por el sensor para obtener una imagen similar a lo que vemos nosotros. Este proceso lo vamos a realizar con dos herramientas, 
empezaremos abriendo la foto con Raw Therapee, dónde realizaremos el procesado básico que consiste en 3 pasos: Interpolación de píxeles, Ajuste de 
blancos y Reescalado de niveles. Una vez realizados estos tres pasos, pasaremos la foto a GIMP, y realizaremos dos ajustes finales que mejorarán nuestra 
foto, Ecualizado y enfoque. Veamos cada uno de estos pasos en detalle.

> **Dedicatoria**
>
>*Sirva este artículo de humilde homenaje a mi abuelo Joaquín 
>quién me enseñó a disparar en manual y revelar con photoshop*

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

Abramos nuestra foto con Raw Therapee ([Aquí puedes descargar la usada de ejemplo](/recursos/2024-02-18/IMGP0001.PEF).) , pongamos unas cuantas lupas 
al 300% de zoom y vayamos a la pestaña Raw. Aquí podemos controlar que algoritmo de interpolación se utiliza y sus posibles parámetros. 
Si estamos ante una foto tomada con bajo ISO, dejaremos AMaZE, si tenemos una foto tomado con un nivel alto de ISO, probaremos con LMMSE ó IGV. 
En el caso de una fotografía en la que predominen las formas circulares, probaremos con RCD. El resto de parámetros de configuración los dejamos por defecto.

![Captura 1](/recursos/2024-02-18/captura_01.png)


# 2. Ajuste de blancos (White balance)
El color de los objetos que vemos se ve afectado por el color de la luz que los ilumina. Sin embargo nuestro cerebro tiene un mecanismo de compensación, 
que nos permite que veamos colores similares bajo condiciones de iluminación muy dispares. el objetivo de este paso es imitar este comportamiento. Visto 
desde el punto de vista de la fotografía, cuándo la escena que fotografiamos se encuentra iluminada por una luz que no sea blanca, la foto tomada tendrá 
lo que se conoce como una dominante, parecerá como si la foto estuviese coloreada del color de la fuente de luz. Se trata de contrarrestar este efecto.

Aquí tenemos dos opciones para realizar este ajuste, una semiautomática que consiste en seleccionar dentro de la imagen una zona de color blanco o 
gris, y con ello se calcula el ajuste de blancos, o el ajuste manual.

Empezaremos con el ajuste semiautomático, para ello, en la pestaña color, dentro de White balance activamos la herramienta Pick y pinchamos en 
alguna zona de la imagen que sea de color blanco o gris. El desplegable Size nos permite elegir el tamaño de la muestra. Podemos ir probando 
hasta encontrar una que de buenos resultados. 

![Captura 2](/recursos/2024-02-18/captura_02.png)

Si no encontramos ninguna, o queremos afinar el resultado, pasamos a hacerlo de forma manual.
Para ello, tomaremos como punto de partida el resultado anterior o probamos con alguno de los ajustes preestablecidos del desplegable method. 
Puede ser el calculado por la cámara (Camera) o alguno de los ajustes fijos que incluye, Daylight (día soleado), Cloudy (día nublado), 
Shade (sombra), Tungsten (Bombilla de tungsteno). Escogeremos el que mejor resultado de de esta lista y manualmente lo terminaremos de ajustar. 

![Captura 3](/recursos/2024-02-18/captura_03.png)

Fíjate que cada uno de los tres parámetros que se pueden ajustar (Temperature, Tint, 
Blue red equalizer) tiene una pareja de colores. El primero tiene en un lado azul y en otro amarillo. La forma de ajustar este control es la siguiente, si 
vemos la foto azulada lo deslizaremos suavemente hacia el amarillo, si vemos la foto amarillenta, deslizaremos el control hacia el azul. Lo mismo haremos 
con el siguiente, si vemos la foto verdosa, lo moveremos hacia el magenta, si la vemos rosada, lo moveremos hacia el verde. El último control sirve cómo un 
ajuste fino de los dos anteriores, pero lo manipularemos igual, si vemos la foto azulada, lo moveremos hacia el rojo y si la vemos rojiza, lo moveremos hacia 
el azul.

![Captura 4](/recursos/2024-02-18/captura_04.png)


# 3. Reescalado de niveles (Exposure)

Éste es el paso más importante y que más impacto tendrá en el proceso de generar la imagen, por lo que debemos invertir en el tanto tiempo cómo sea necesario.
Éste paso requiere de cierto entrenamiento, así que no te preocupes si las primeras decenas de fotos no te salen del todo bien.
El sensor de nuestra cámara tiene una respuesta lineal a diferencia de nuestro sentido de la vista que tiene una respuesta logarítmica a los estímulos luminosos.
Este paso consiste en convertir los valores RGB lineales a logarítmicos.
Las herramientas de procesado Raw, por motivos históricos, suelen llamar a ésto "Ajuste de la exposición" o similar, pero este nombre puede llevarnos a confusión, 
ya que aunque haciendo el reescalado se puede corregir la exposición, una foto por muy bien expuesta que esté necesitará necesariamente hacer reescalado 
para pasar de niveles lineales a logarítmicos.
Éste paso es tan importante y delicado que requiere su propio tutorial. Toda la pestaña Exposure está dedicada a este paso, dentro de esta pestaña hay 
numerosas herramientas que hacen cambios sutiles en el reescalado, cada uno con una finalidad. En este tutorial nos vamos a centrar en la herramienta 
fundamental, la curva de niveles (Tone Curves).
Entramos en la pestaña Exposure, y nos vamos a Tone Curve 1. Ésta curva es el control básico del reescalado, básicamente define una función que asigna a cada 
nivel de entrada un nuevo nivel de salida. Al poner aquí una curva en forma de S estamos haciendo el paso de lineal a logarítmico. Modificando sutilmente 
la curva conseguimos cambios drásticos en la imagen. De ahí su delicadeza y dificultad. Pulsando el botón Auto matched tone curve, generamos una curva 
calculada automáticamente, que puede ser un buen punto de partida. Si pulsamos la flechita, eliminamos la curva, lo que permite hacerla desde cero.

![Captura 5](/recursos/2024-02-18/captura_05.png)


# 4. GIMP

Una vez realizados estos pasos, vamos a pasar la foto a GIMP, para hacer los ajustes finales. Para ello pulsamos sobre el botón Enviar a editor externo.

![Captura 6](/recursos/2024-02-18/captura_06.png)

Si no se abriese la imagen con GIMP, tendremos que configurar el editor externo que queremos usar. Para ello abrimos una nueva ventana de Raw Therapee
sin abrir ninguna foto, y en ajustes, pestaña general, tenemos la opción de seleccionar el editor externo que queremos usar.

![Captura 7](/recursos/2024-02-18/captura_07.png)

Una vez en gimp, seleccionamos la herramienta Niveles.

![Captura 8](/recursos/2024-02-18/captura_08.png)

El triángulo de la izquierda controla los tonos oscuros, el de la derecha los tonos claros, y el del centro ajusta el contraste. Deslizaremos sutilmente 
el triángulo de la izquierda hacia la derecha, el de la derecha hacia la izquierda, y el del centro a uno u otro lado según nos agrade el resultado. 
Pulsamos OK cuándo estemos satisfechos con el resultado.

![Captura 9](/recursos/2024-02-18/captura_09.png)

Y por último enfocamos la imagen un poco con la máscara de enfoque.

![Captura 10](/recursos/2024-02-18/captura_10.png)

Los valores por defecto suelen funcionar bien en la mayoría de los casos, no obstante si queremos más o menos enfoque, cambiaremos el valor del Radio.
Ponemos el zoom al menos al 100% para ver los cambios y vemos como queda. Una vez nos guste el resultado, pulsamos OK.

![Captura 11](/recursos/2024-02-18/captura_11.png)

Ya sólo nos queda guardar la imagen. Guardaremos una versión en el formato nativo de GIMP, que usaremos cada vez que queramos imprimir una copia, y otra 
versión en jpg para nuestras redes sociales.

![Captura 12](/recursos/2024-02-18/captura_12.png)

Dejamos las opciones por defecto, nos aseguramos de estar en la carpeta correcta (¡ojo! Raw therapee usa por defecto la carpeta temporal del sistema), le 
ponemos un nombre y guardamos nuestra foto.

![Captura 13](/recursos/2024-02-18/captura_13.png)

Por último la exportamos en JPG

![Captura 14](/recursos/2024-02-18/captura_14.png)

Igual que antes, comprobamos que el nombre y la ruta sean los adecuados y que no machacamos ningún archivo.

![Captura 15](/recursos/2024-02-18/captura_15.png)

Ponemos los ajustes de JPG que consideremos oportunos, al menos un 90% de calidad.

![Captura 16](/recursos/2024-02-18/captura_16.png)

Con esto ya tenemos nuestra foto terminada. En este artículo hemos aprendido el proceso básico para convertir los datos RAW del sensor de 
nuestra cámara a un bonito JPG. Tanto Raw Therapee como GIMP disponen de numerosas herramientas para editar nuestras fotos, aquí nos hemos 
centrado en los ajustes básicos con el objetivo de hacer una introducción a la fotografía RAW. Espero que os haya gustado, cualquier duda, 
comentario o crítica es bienvenida en los canales habituales de La Jaquería.


![Foto terminada](/recursos/2024-02-18/IMGP0001.jpg)
