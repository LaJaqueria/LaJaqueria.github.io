---
layout: post
#Datos del post
title: "Transparencias charla radioafición"

#Fecha
date: 2018-08-23T19:30

category: post
user: Fran Acién
---

Transparencias de la charla dada por Fran Acién en HackLab Almería el 23 de agosto de 2018.

## RADIOAFICIÓN

### ¿En qué consisten las radiocomunicaciones?
La transmisión de información a través de ondas de radio u hertzianas. Se aprovecha el campo electromagnético para transmitir perturbaciones desde una antena a otra.

### ¿Para qué sirve la radio?

Desde abrir un garaje hasta comunicarse con sondas en el espacio profundo. Desde el punto de vista de la radioafición, se pueden conseguir contactos en fonía con cualquier parte del mundo (según las condiciones atmosféricas y de las instalaciones).

### ¿Qué podemos transmitir?

Técnicamente cualquier forma de información. Con modulaciones analógicas: fonía, morse, imágenes (SSTV)... Con modulaciones digitales cualquier cosa.

---

## Conceptos básicos

### Modelo de canal de comunicaciones: transmisor, medio y receptor

![Foto del Modelo de canal de comunicaciones](/recursos/2018-08-08/init04-pag12.png)

### Análisis en frecuencia de un canal de telecomunicaciones: respuesta en frecuencia del canal H(f)

![Análisis en frecuencia de un canal de telecomunicaciones](/recursos/2018-08-08/analisis_en_frecuencia_radio.png)

### Necesidad de la modulación y la multiplexación (en el dominio de la frecuencia)

> DEFINICIÓN DE MULTIPLEXACIÓN
La transmisión simultánea de varios canales de comunicación sobre un mismo medio de transmisión (radio o cable). Permite compartir un medio de transmisión por parte de varias señales y generar notables ahorros.


[Sólo se explicará la multiplexación por división en el dominio de la frecuencia (FDM)]

Multiplexado FDM. Queremos lograr que haya un número determinado de señales viajando a la vez por el mismo medio físico - guiado o no guiado (cable, radio, ...)-. Para ello, mediante la modulación, asignamos cada una de las señales una frecuencia portadora diferente, elegidas éstas adyacentes para que las señales no se solapen en frecuencia en el canal y viajen en la misma banda de frecuencia.

![Ejemplo gráfico de multiplexación en FDM](/recursos/2018-08-08/multiplexacion.png)

### Espectro radioeléctrico

![Espéctro radioeléctrico](/recursos/2018-08-08/espectroRadioelectrico.png)

---

## Antenas

Convierten las ondas electromagnéticas en corriente eléctrica y viceversa.

### Ancho de banda

Es el margen de frecuencias en el cual los parámetros de la antena cumplen unas determinadas características. Se puede definir un ancho de banda de impedancia, de polarización, de ganancia o de otros parámetros.

El ancho de banda está determinado por las frecuencias superior e inferior fuera de las cuales el nivel de energía en la antena decrece a más de 3dB.

### Directividad

La Directividad (D) de una antena se define como la relación entre la intensidad de radiación de una antena en la dirección del máximo y la intensidad de radiación de una antena isotrópica que radia con la misma potencia total:

$$

D = \frac{U(max)}{U(iso)}

$$

### Ganancia

Se define como la ganancia de potencia en la dirección de máxima radiación. La Ganancia (G) se produce por el efecto de la directividad al concentrarse la potencia en las zonas indicadas en el diagrama de radiación.

![Directividad antena](/recursos/2018-08-08/directividad_antena.jpg)

### Polarización

La **polarización** de una antena es la trayectoria que describe el campo eléctrico cuando se observa en el sentido de propagación de la onda(la onda se aleja del observador).

* Polarización **lineal** (vertical u horizontal): Cuando las variaciones del campo eléctrico están contenidas en una única dirección, sea esta vertical u horizontal respecto al suelo.

* Polarización **circular** (derecha o izquierda): cuando el campo eléctrico describe una trayectoria circular. Si gira en sentido de las agujas del reloj, la polarización es a derechas. Si lo hace en sentido contrario, la polarización es de izquierdas.

### Longitud de onda

La longitud de onda depende de la frecuencia de oscilación y cuanto menor sea la frecuencia de la señal, mayor longitud de onda tendrá la señal emitida. Esto es: a mayor frecuencia, menos longitud de onda y viceversa.

$$

\lambda = \frac{v}{f} = v \cdot T

$$

Siendo \\(v\\) la velocidad, \\(f\\) la frecuencia y \\(T\\) el periodo.


![Longitud de onda](/recursos/2018-08-08/longitud_de_onda.png)

Cada antena, dependiendo de su construcción estarán pensadas para una banda un otra de radiafición dependiendo de su longitud de onda.

### Diferentes antenas

![Diferentes antenas](/recursos/2018-08-08/antenas-sats.jpg)

---

## Modulación

>Modulación: traslación en frecuencia de una señal a transmitir mediante una portadora. Se emplea para poder enviar la señal a las frecuencias de trabajo del canal.

![Imagen de bloques de cómo funciona una radio](/recursos/2018-08-08/modulacion.png)

* **Señal moduladora**: señal con la información que se desea transmitir, que va a modificar (modular) alguna de las carácterísticas de la señal portadora (amplitud, frecuencia, o fase). Puede ser una señal analógica o digital.
* **Señal portadora**: señal que va a transportar en el canal a la señal moduladora. Su frecuencia debe estar dentro del rango de frecuencias de trabajo del canal. Siempre es una señal analógica.
* **Señal modulada**: combinación de la señal moduladora y portadora de acuerdo a determinado tipo de modulación. Siempre consiste en la traslación de la señal moduladora a la frecuencia portadora, independientemente del tipo de modulación.
* **Modulador**: proceso electrónico consistente en combinar la señal moduladora con la portadora para su transmisión. También puede realizarse mediante software “radio definida por software SDR”.
* **Demodulador**: proceso electrónico consistente en extraer la señal moduladora de la señal modulada recibida. También puede realizarse mediante SDR.

### Diferentes modulaciones

Las modulaciones son las diferentes formas de variar una señal. Las más frecuentes AM, FM, SSB, ASK, etc.

<img src="/recursos/2018-08-08/fm_am.gif" width="100%">

---

## Propagación

Hay muchas formas de propagación, la más común sería por vía directa. Otras más interesantes son la propagación ionosférica (la más utilizada en radioafición) y el rebote lunar.

![Progración ionosfera](/recursos/2018-08-08/propagacion.jpg)

---

## Radioafición

### Bandas (grupos de frecuencias)

Se suele utilizar este término para referirse a un rango de frecuencias. Las bandas toman el nombre de la longitud de onda media (aprox.) de las frecuencias comprendidas. La banda ciudadana por ejemplo, se llama "11 metros" ya que es la longitud de onda correspondiente a 27MHz. Otras bandas comunes son 20m (14MHz) o VHF/2m (144Mhz).

[Bandas de radioaficionados según la URE](https://www.ure.es/bandas-atribuidas/)

#### Frecuencias interesantes (en MHz)

* **433.920** Se utiliza para para la mayoría de mandos (coches, garajes, interruptores...).
* **868** Similar a la anterior.
* **287** Similar a las anteriores.
* **144.800** [APRS](http://www.aprs.org/).
* **145.500** Llamada en FM en la banda VHF.
* **433.500** LLamada en FM en la banda UHF.
* **14.230** SSTV en la banda de 20m.

### QSL

![](/recursos/2018-08-08/qsl_1.jpg)

![](/recursos/2018-08-08/qsl_2.jpg)

---

## SDR

Radio definida por software. Ya no es necesario fabricar un circuito para recibir/emitir en una banda concreta y para una modulación. Podemos variar los parámetros de un receptor/emisor directamente por software. Esto reduce mucho los costes y agiliza cualquier proceso. Está destinada a pruebas, por el momento no iguala en potencia y calidad a un equipo específico, especialmente a la hora de emitir. Algunos ejemplos: RTL-SDR, HackRF, BladeRF, AirSpy...

*Demo*

### Web-SDR

Sólo necesitas un navegador y acceso a internet:

*Demo*

Para seguir: decodificando SSTV con **qsstv**. Freq. **14.230MHz**

[twente WebSDR](http://websdr.ewi.utwente.nl:8901/)

---

## Codificaciones útiles para satélites (y no solo satélites)

### APRS

Automatic Packet Reporting System (APRS) es un sistema en tiempo real de comunicaciones digitales de información relevante en el área local. Dentro del paquete APRS se incluyen información cómo coordenadas GPS, telemetría de estado meteorológico, mensajes de texto, etc. APRS puede ser visualizado en un mapa, en el que las estaciones puede trazar por donde pasan los aparatos que emiten aprs, ejemplo APRS fi.

[APRS fi](https://es.aprs.fi)

### SSTV

Televisión de barrido lento (Slow ScanTV, SSTV) es un método de transmisión de imágenes utilizado principalmente por radioaficionados para transmitir y recibir imágenes estáticas.

[Ejemplo de transmisión en SSTV](https://www.youtube.com/watch?v=BKlpueYWvKc)

Para decodificar emisiones de SSTV, se puede utilizar software cómo **qsstv**.

---

## Picosatélites

![Sample pisosat](/recursos/2018-08-08/picosatelite.jpg)
https://www.itu.int/dms_pub/itu-r/md/12/itur.manta/c/R12-ITUR.MANTA-C-0014!!PDF-S.pdf

### ¿Cuantos satélites hay en órbita a la tierra? ¿Cómo determinar su posición?

Cada satélite tiene un TLE (two-line element set), que contiene información de su posición, su velocidad, cómo se mueve, etc. Para sabe la posición de un satélite dentro de un día, tenemos que propagar esta ecuación y así sabremos donde está.

>NOAA 19 [+]             
1 33591U 09005A   18227.93417742  .00000089  00000-0  73509-4 0  9997
2 33591  99.1466 207.1621 0014326 155.1757 205.0106 14.12300459490347

La mayoría de los satélites tiene los TLE's publicados en **celestrak**: [Página de celestrak](https://celestrak.com/NORAD/elements/)

Hay una herramienta súper útil que nos proporciona diagramas polares, área de radiación de un satélite, posición de los satélites, información de los transpondedores, **incluso puede programar para mover las antenas a la par que el pase de un satélite**. Se llama **gpredict**:

[Gpredict](http://gpredict.oz9aec.net/)

![Gpredict](/recursos/2018-08-08/gpredict.png)

### ¿Cómo me conecto a un satélite de radioaficionado?

Lo usual es que esta información esté pública y nos informen la frecuencia de subida, la frecuencia de bajada, la modulación, y que codificación van a seguir. Toda esta información está recopilada gracias a los radioaficionados en esta base de datos:

[SatNOGS](https://db.satnogs.org/)


### Ejemplo de recepción de un satélite NOAA

[Video de ejemplo de recepción de un satélite NOAA](https://www.youtube.com/watch?v=OARj5wguj6M)

---

## GranaSAT Dashboard

[GranaSAT Dashboard](https://github.com/granasat/GranaSATDashboard)

---

## Radioclub ETSIT UPM EA4RCT

![](/recursos/2018-08-08/antena-HF.jpg)

![](/recursos/2018-08-08/radioclub_1.jpg)

![](/recursos/2018-08-08/radioclub_2.jpg)

![](/recursos/2018-08-08/radioclub_3.jpg)

![](/recursos/2018-08-08/radioclub_4.jpg)

---

## GranaSAT

![](/recursos/2018-08-08/granasat_1.jpg)

![](/recursos/2018-08-08/granasat_2.jpg)

![](/recursos/2018-08-08/granasat_3.jpg)

![](/recursos/2018-08-08/granasat_4.jpg)

![](/recursos/2018-08-08/granasat_5.jpg)

![](/recursos/2018-08-08/granasat_6.jpg)

[Página web de Granasat UGR](http://granasat.ugr.es/)

## Herramientas útiles para radio/satélites

* [Gqrx](http://gqrx.dk/)
* [qsstv](http://users.telenet.be/on4qz/)
* [gnuradio](https://www.gnuradio.org/)
* [gpredict](http://gpredict.oz9aec.net/)
* [celestrak](https://celestrak.com/NORAD/elements/)
* [SatNOGS](https://db.satnogs.org/)
* [WebSDR](http://www.websdr.org/)
* [¿Quién llama?](https://qrz.com/)
* [Aprs fi](https://es.aprs.fi)

## Links interesantes

* [Video bastante ilustrativo de cómo funciona AM y FM](https://youtu.be/JTkKr-5TMfE)
* [Inhibidor casero](https://www.youtube.com/watch?v=ayn1Wa1dfqI)
* [OpenSesame](https://samy.pl/opensesame/)
* [fourier](https://es.wikipedia.org/wiki/Transformada_de_Fourier)

## Referencias

* [Charla del hacklab de la brecha digital dada por M0wer](https://git.digitales.cslabrecha.org/La_Brecha_Digital/charlas-y-talleres/src/branch/master/20170621-radio/radio-intro.md)
* Diapositivas de la asignatura de INIT de la ETSIT-UPM 2017/2018
* Libro de examen de radioaficionados

amil101@debian:~$ EXIT
