---
layout: post

title: Guía rápida VI
description: Vi es el editor de texto universal en sistemas GNU/Linux
date: 2024-02-18
author: "Emilio LB"
category: blog
user: La Jaquería
---

# Introducción
El editor VI, odiado por algunos, amado por otros es el editor de texto más sencillo disponible en sistemas GNU/Linux, tiene la ventaja de que sea 
cual sea el sistema en el que estamos, un servidor, un router, un sistema embebido, lo vamos a tener disponible. Su uso puede parecer difícil al principio 
pero no porque sea intrínsecamente difícul de usar, sino porque es muy distinto a lo que estamos acostumbrados.

# Modos de VI
Vi trabaja en dos modos, modo navegación y modo edición. Para entrar en el modo edición, pulsamos la tecla i y para salir del modo edición y volver 
al modo navegación, pulsamos ESC. En el modo navegación, nos podemos mover por el texto usando las flechas del teclado o usando j (jota) para bajar, k (ka) para subir 
h (hache) para ir a la izquierda y l (ele) para ir a la derecha.

# Comandos básicos
* Para salir sin guardar, pulsamos :q! (dos puntos, qu, admiración)
* Para guardar, pulsamos :w (dos puntos, uve doble)
* Para guardar y salir, pulsamos :wq (dos puntos, uve doble, qu)
* Para buscar una palabra, en el modo navegación pulsamos / (barra) y escribimos el texto a buscar. Para ir pasando al siguiente usamos n (ene) y para ir 
al anterior, N (n mayúscula)
* Para insertar una línea vacía debajo del cursor, en el modo navegación pulsamos o. Se insertará una nueva línea y pasaremos al modo edición
* Para eliminar una línea, en el modo navegación pulsamos :d (dos puntos de). Seguiremos en el modo navegación después de éste comando.
* Para eliminar varias líneas, en el modo navegación pulsamos :d seguido del número de líneas, por ejemplo 
para borrar diez líneas :d10 (dos puntos, de, uno, cero)
* Para ir al final del documento, en el modo navegación pulsaremos G (g mayúscula)
* Para ir al inicio del documento, en el modo navegación pulsamos gg (g dos veces)
