---
layout: post

title: Cómo ejecutar Windows (o MacOS) y Linux al mismo tiempo
description: Si tenemos un portátil Windows (o MacOS), y no queremos perder la maqueta del disco duro que viene de fábrica, podemos usar VirtualBox para tener un Linux a mano.
date: 2024-11-10
author: "Emilio LB"
category: blog
user: La Jaquería
---

# Introducción

En este artículo vamos a ver como usando la virtualización podemos tener en nuestro portátil Windows y Linux al mismo tiempo, de forma que podemos tener 
a la vez abiertas aplicaciones de Windows, y aplicaciones de Linux. Para ello vamos a utilizar [Virtual Box](https://www.virtualbox.org/)

Éste artículo está centrado en Windows, pero se puede hacer lo mismo con MacOS, ya que 
también existe una versión de Virtual Box para MacOS

Las últimas versiones de Windows incluyen un componente (WSL, Windows Subsystem for Linux) que nos permite hacer algo parecido. Sin embargo no vamos a usarlo, 
puesto que con Virtualbox tenemos alguna opción más.

En primer lugar tenemos que instalar VirtualBox, pero para poder hacerlo previamente debemos instalar Microsoft Visual C++ redistributable. Para ello, entramos en la página de Microsoft,
y buscamos el enlace de descarga. ([Enlace a la descarga Microsoft Visual C++ redistributable](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170#latest-microsoft-visual-c-redistributable-version).)


![Captura 1](/recursos/2024-11-10/captura_01.png)

Seleccionamos la descarga correspondiente a nuestra arquitectura

![Captura 2](/recursos/2024-11-10/captura_02.png)

Lanzamos el instalador

![Captura 3](/recursos/2024-11-10/captura_03.png)

Una vez finalizada la instalación, aparecerá una ventana de confirmación

![Captura 4](/recursos/2024-11-10/captura_04.png)

Entramos en la web de virtualbox y descargamos el instalador

![Captura 5](/recursos/2024-11-10/captura_05.png)

Ejecutamos el instalador de virtual box

![Captura 6](/recursos/2024-11-10/captura_06.png)

Dejamos los parámetros por defecto de instalación

![Captura 7](/recursos/2024-11-10/captura_07.png)

El instalador nos avisa que durante la instalación se interrumpirá la conexión a red. Confirmamos el aviso

![Captura 8](/recursos/2024-11-10/captura_08.png)

Confirmamos que deseamos instalar las dependencias necesarias

![Captura 9](/recursos/2024-11-10/captura_09.png)

Pulsamos aceptar para iniciar la instalación

![Captura 10](/recursos/2024-11-10/captura_10.png)

Una vez finalizada la instalación, aparecerá una ventana de confirmación

![Captura 11](/recursos/2024-11-10/captura_11.png)

Descargamos la imagen de instalación de Linux Debian

![Captura 12](/recursos/2024-11-10/captura_12.png)

Abrimos virtual box, y pulsamos en nuevo

![Captura 13](/recursos/2024-11-10/captura_13.png)

Ponemos un nombre a la máquina virtual, y especificamos la ruta de la imagen ISO del instalador de Debian que hemos descargado antes. IMPORTANTE: Marcamos Omitir instalación desatendida.

![Captura 14](/recursos/2024-11-10/captura_14.png)

Establecemos la cantidad de memoria RAM que queremos dedicar a la máquina virtual, y el número de procesadores. La mitad de la RAM es un buen número, el número de procesadores lo podemos poner en 1 ó en 2, 
nunca más de la mitad de procesadores que tengamos. Ésto lo podemos cambiar después si lo necesitamos.

![Captura 15](/recursos/2024-11-10/captura_15.png)

Aparecerá una ventana de confirmación de la creación de la máquina virtual.

![Captura 16](/recursos/2024-11-10/captura_16.png)

Creamos un disco duro virtual, 20 gigas es un buen tamaño. Ese será el máximo tamaño que ocupará en nuestro disco duro de verdad, al principio ocupará poco e irá creciendo de forma automática conforme lo vayamos necesitando

![Captura 17](/recursos/2024-11-10/captura_17.png)

Pulsamos iniciar para arrancar la máquina virtual y proceder a la instalación del sistema operativo

![Captura 18](/recursos/2024-11-10/captura_18.png)

Aparecerá el arranque del instalador de Debian, y una barra de notificaciones de virtual box en la parte derecha. Podemos 
descartar las notificaciones con el icono de la izquierda. Pinchamos sobre la ventana

![Captura 19](/recursos/2024-11-10/captura_19.png)

Aparece una ventana avisando que el ratón y el teclado van a ser capturados. Pulsamos capturar.

![Captura 20](/recursos/2024-11-10/captura_20.png)

Seleccionamos la opción de Install

![Captura 21](/recursos/2024-11-10/captura_21.png)

Seleccionarmos el idioma 
![Captura 22](/recursos/2024-11-10/captura_22.png)

Seleccionamos el pais
![Captura 23](/recursos/2024-11-10/captura_23.png)

Seleccionamos la configuración del teclado
![Captura 24](/recursos/2024-11-10/captura_24.png)

Introducimos un nombre para la máquina
![Captura 25](/recursos/2024-11-10/captura_25.png)

Si queremos podemos añadir un dominio, pero lo vamos a dejar en blanco
![Captura 26](/recursos/2024-11-10/captura_26.png)

Escribimos una contraseña para el superusuario, y la apuntamos en algún sitio localizable
![Captura 27](/recursos/2024-11-10/captura_27.png)

Repetimos la contraseña para confirmarla
![Captura 28](/recursos/2024-11-10/captura_28.png)

Introducimos el nombre del usuario principal
![Captura 29](/recursos/2024-11-10/captura_29.png)

Introducimos un nombre de usuario, todo minúscula y sin espacios
![Captura 30](/recursos/2024-11-10/captura_30.png)

Escribimos la contraseña del usuario
![Captura 31](/recursos/2024-11-10/captura_31.png)

confirmamos la contraseña del usuario escribiendola de nuevo
![Captura 32](/recursos/2024-11-10/captura_32.png)

Seleccionamos la zona horaria
![Captura 33](/recursos/2024-11-10/captura_33.png)

Seleccionamos particion guiada del disco duro
![Captura 34](/recursos/2024-11-10/captura_34.png)

Seleccionamos el disco duro virtual
![Captura 35](/recursos/2024-11-10/captura_35.png)

Dejamos la opción de todos los archivos en una única partición
![Captura 36](/recursos/2024-11-10/captura_36.png)

Seleccionamos la opción de finalizar el particionado y guardar los cambios en disco
![Captura 37](/recursos/2024-11-10/captura_37.png)

Confirmamos los cambios
![Captura 38](/recursos/2024-11-10/captura_38.png)

Dejamos que el instalador haga su trabajo
![Captura 39](/recursos/2024-11-10/captura_39.png)

En este paso nos pregunta si queremos utilizar algún cd adicional. seleccionamos que no
![Captura 40](/recursos/2024-11-10/captura_40.png)

Seleccionamos el pais del que queremos que se descarguen los archivos de instalación
![Captura 41](/recursos/2024-11-10/captura_41.png)

Seleccionamos un mirror, dejamos el primero.
![Captura 42](/recursos/2024-11-10/captura_42.png)

Dejamos en blanco la opción del proxy
![Captura 43](/recursos/2024-11-10/captura_43.png)

Dejamos que el instalador trabaje
![Captura 44](/recursos/2024-11-10/captura_44.png)

Seleccionamos si queremos participar en la encuesta de paquetes
![Captura 45](/recursos/2024-11-10/captura_45.png)

Marcamos las opciones Entorno de escritorio Debian, XFCE, Utilidades estándar del sistema
![Captura 46](/recursos/2024-11-10/captura_46.png)

Dejamos que el instalador trabaje
![Captura 47](/recursos/2024-11-10/captura_47.png)

Confirmamos la instalación de grub, que es el arranque de linux
![Captura 48](/recursos/2024-11-10/captura_48.png)

Confirmamos el disco en el que queremos instalar grub, que será el único disponible
![Captura 49](/recursos/2024-11-10/captura_49.png)

Una vez finalizada la instalación, el instalador avisa del reinicio del sistema
![Captura 50](/recursos/2024-11-10/captura_50.png)

Iniciamos sesión con el usuario y contraseña que creamos durante la instalación
![Captura 51](/recursos/2024-11-10/captura_51.png)

Vemos la configuración por defecto de xfce, para adaptarlo mejor al uso junto con windows, vamos a quitar la barra inferior y mover la superior a la parte inferior
![Captura 52](/recursos/2024-11-10/captura_52.png)ç

Pulsamos con el botón derecho del ratón sobre la barra inferior, y pulsamos panel, preferencias del panel
![Captura 53](/recursos/2024-11-10/captura_53.png)

Eliminamos el panel 2 con el icono menos
![Captura 54](/recursos/2024-11-10/captura_54.png)

Confirmamos que queremos eliminar el PANEL 2
![Captura 55](/recursos/2024-11-10/captura_55.png)

Arrastramos el panel 1 con el ratón de la parte superior a la inferior
![Captura 56](/recursos/2024-11-10/captura_56.png)

![Captura 57](/recursos/2024-11-10/captura_57.png)

Activamos la opción de bloquear el panel, para evitar cambios accidentales
![Captura 58](/recursos/2024-11-10/captura_58.png)

A continuación vamos a instalar los drivers de virtualbox, lo que nos va a permitir una mayor comodidad a la hora de usar la máquina virtual.
Seleccionamos en virtualbox la opción de insertar el CD con los complementos de invitado
![Captura 59](/recursos/2024-11-10/captura_59.png)

Nos aparecerá el icono de cd en el escritorio. Pulsamos con el botón derecho y seleccionamos montar volumen
![Captura 60](/recursos/2024-11-10/captura_60.png)

Abrimos el terminal
![Captura 61](/recursos/2024-11-10/captura_61.png)

Ejecutamos el instalador de las adiciones de virtual box: sh /media/cdrom/autorun.sh
![Captura 62](/recursos/2024-11-10/captura_62.png)

El instalador nos pedirá la contraseña de root
![Captura 63](/recursos/2024-11-10/captura_63.png)

Dejamos que el instalador trabaje
![Captura 64](/recursos/2024-11-10/captura_64.png)

Expulsamos el cd de la unidad virtual
![Captura 65](/recursos/2024-11-10/captura_65.png)

Nos dará un aviso, forzamos la expulsión. Tras esto vamos a reiniciar la máquina virtual.
![Captura 66](/recursos/2024-11-10/captura_66.png)

Seleccionamos Aplicaciones / Cerrar sesión
![Captura 67](/recursos/2024-11-10/captura_67.png)

PUlsamos el boton de reiniciar
![Captura 68](/recursos/2024-11-10/captura_68.png)

Ahora vamos a configurar que no sea necesario introducir la contraseña cada vez que iniciemos la máquina virtual. 
Abrimos un terminal, escalamos privilegios a super usuario con su - y editamos el archivo /etc/lightdm/lightdm.conf
![Captura 69](/recursos/2024-11-10/captura_69.png)

Cambiamos el valor de autologin-user y le ponemos el nombre del usuario que hemos creado durante la instalación. Eliminamos el cuadradillo del principio.
![Captura 70](/recursos/2024-11-10/captura_70.png)

PUlsamos ESC, :wq para salir y guardar
![Captura 71](/recursos/2024-11-10/captura_71.png)

Reiniciamos la máquina
![Captura 72](/recursos/2024-11-10/captura_72.png)

Ahora vamos a configurar que se pueda acceder a los documentos de windows desde la máquina virtual. Entramos
en Dispositivos, carpetas compartidas, Preferencias de carpetas compartidas
![Captura 73](/recursos/2024-11-10/captura_73.png)

En Carpetas de la máquina, pulsamos en añadir
![Captura 74](/recursos/2024-11-10/captura_74.png)

En ruta de carpeta, ponemos la carpeta de usuario de windows. En nombre de carpeta podemos poner lo que queramos, por ejemplo windows. Marcamos 
automontar y hacer permanente, para que esté siempre disponible.
![Captura 75](/recursos/2024-11-10/captura_75.png)

Pulsamos aceptar
![Captura 76](/recursos/2024-11-10/captura_76.png)

Damos permisos al usuario para acceder a la carpeta compartida. para ello como super usuario ejecutamos usermod -a -G vboxsf emilio (o el usuario creado durante la instalación)
![Captura 77](/recursos/2024-11-10/captura_77.png)

Reiniciamos de nuevo
![Captura 78](/recursos/2024-11-10/captura_78.png)

Si abrimos un explorador de archivos (thunar por ejemplo) y navegamos a /mnt/windows, vemos que tenemos acceso a los documentos de windows
![Captura 79](/recursos/2024-11-10/captura_79.png)

Por último habilitamos el portapapeles bidireccionar para poder copiar en windows y pegar en linux y viceversa.
Seleccionamos Dispositivos / Portapapeles compartido / Bidireccional
![Captura 80](/recursos/2024-11-10/captura_80.png)

Tambien activamos que se puedan mover ficheros arrastrando y soltando, para ello entramos en Dispositivos, Arrastrar y soltar, Bidireccional
![Captura 81](/recursos/2024-11-10/captura_81.png)

En virtual box tenemos distintos modos de ver la máquina virtual, el que hemos estado usando hasta ahora, el modo pantalla completa, y el más interesante, el modo 
"seamless" o híbrido, lo que nos permite ver a la vez los programas de windows junto con los de linux como si de un único sistema se tratase. Tiene una pequeña limitación, al 
tener en foco una ventana de windows, se esconde la barra de inicio de linux, clicando en el icono de virtualbox de la barra de inicio de windows, vuelve a aparecer.
![Captura 82](/recursos/2024-11-10/captura_82.png)

En este modo podemos por ejemplo abrir el bloc de notas de windows y el equivalente en linux, y tener una ventana al lado de la otra.
![Captura 83](/recursos/2024-11-10/captura_83.png)

