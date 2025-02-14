---
layout: post

title: Archivando datos digitales con Dvdisaster
description: Aunque la moda sea usar la nube, los medios ópticos tienen algunas ventajas que no debemos olvidar.
date: 2024-12-22
author: "Emilio LB"
category: blog
user: La Jaquería
---

# Introducción

Si bien la moda actual es usar la nube de almacenamiento secundario o de copia de seguridad, no podemos olvidar aquel dicho "La nube es el ordenador de otro". 
Si bien esto es una simplificación, si que es cierto el espíritu de la frase, que viene a decir que estás a expensas de la buena fe de dicho servicio. No 
sería la primera vez que una empresa que ofrece servicios en la nube desaparece de un día para otro, o lo más habitual, que una gran empresa borre datos tuyos 
bajo sospecha de infracción de copyright, sin juez ni orden judicial de por medio. Es bajo esta premisa que no podemos olvidar los medios que tenemos a nuestro 
alcance para hacer archivado seguro de datos a un coste razonable. 

Los CDs y DVDs aun con su limitada capacidad, nos ofrecen una forma razonable de guardar cantidades moderadas de datos a buen recaudo. A diferencia de un pendrive 
o de disco SSD, los discos ópticos son de sólo lectura (Nunca jamás bajo ningún concepto compreis un cd o dvd regrabable. Es fácil que algún día grabéis 
algo importante en él por error y se acabe desvaneciendo....) lo cuál es una muralla de defensa ante ataques tipo ransomware (esos virus que te encriptan tus datos 
y te piden un rescate por la clave privada que seguramente no tengan) y ante borrados accidentales. Una vez nuestros datos están en un CD o DVD están razonablemente 
a salvo.

Lamentablemente los discos ópticos tienen una debilidad, son algo frágiles. Afortunadamente es algo que se puede mitigar, y aquí es donde aparece el software dvdisaster.
Dvdisaster es una utilidad que sirve para añadir redundancia a un disco óptico (CD, DVD o Blue Ray). Esto es en vez de hacer un paquete de datos de la capacidad del disco, 
hacemos un paquete de datos de algo menos que tres cuartas partes del disco, y mediante esta utilidad, lo vamos a completar con información redundante, que puede ser usada 
en un futuro en caso de que parte del disco se vuelva ilegible por cualquier motivo. Si a esto añadimos la técnica habitual de hacer dos copias, una que guardemos en casa 
y otra que dejemos en otro espacio, bien sea en casa de un familiar, en el trabajo, etc, tenemos un sistema muy robusto para guardar nuestra información más preciada. 
Pongamos el caso de unas fotos familiares. ¿Quién no ha perdido fotos digitales por no haber hecho una gestión adecuada?

Manos a la obra, ¿Cómo se utiliza Dvdisaster? Necesitamos prefrentemente un ordenador con Linux, si usamos windows, [podemos usar una máquina virtual](../11//10/windows-y-linux.html).
En primer lugar, copiamos a un directorio temporal los archivos que queremos guardar en el disco para tenerlos agrupados. Si ya los tenemos en un directorio, 
no es necesario copiarlos. En este ejemplo vamos a usar /tmp/dvd como directorio temporal con los datos que queremos guardar


Primero creamos una imagen del directorio que hemos preparado, para ello usamos el comando:

```bash
xorriso -as mkisofs -v -J -r -V DATOS -o /tmp/dvd.iso /tmp/dvd/
```

Donde DATOS es la etiqueta que le queremos poner al disco, /tmp/dvd.iso es el fichero con la imagen que vamos a generar y /tmp/dvd es el directorio del que se van 
a tomar los datos para hacer la imagen. En la captura se ha usado ./dvd03 como directorio origen en lugar de /tmp/dvd porque los datos a guardar los tenía ya preparados en dicho dierctorio.

![Captura 1](/recursos/2024-12-22/captura_01.png)

Si no tenemos instalado xorriso, lo instalamos con el comando

```bash
apt-get -y install xorriso
```


![Captura 2](/recursos/2024-12-22/captura_02.png)

Una vez creada la imagen, le aplicamos la protección de dvdisaster

Si no tenemos instalado dvdisaster, lo instalaremos con el comando

```bash
apt-get install dvdisaster
```

o el comando similar para nuestra distribución.

![Captura 3](/recursos/2024-12-22/captura_03.png)

Usaremos el comando dvdisaster para ampliar la imagen que creamos anteriormente con información de redundancia, para ello:

```bash
dvdisaster -i /tmp/dvd.iso -mRS02 -n DVD -c
```

Si en lugar de un DVD tenemos otro tipo de disco óptico, usaremos el parámetro n adecuado:
CD para cd, DVD9 para dvd de doble capa, BD para BlueDisc y BD2 para BlueDisc de doble capa.

![Captura 4](/recursos/2024-12-22/captura_04.png)

Una vez terminado el proceso de añadir redundancia, grabaremos el disco con el comando wodin

```bash
wodim -v -dao speed=8 -eject dev=/dev/sr0 /tmp/dvd.iso
```

![Captura 5](/recursos/2024-12-22/captura_05.png)

Una vez finalizada la grabación, insertaremos el disco recién grabado y verificaremos que su checksum coincide con el de la imagen creada. En la captura se haceo dos veces porque 
he grabado dos copias, una con la primera copia, y luego insertando la segunda copia.

```bash
md5sum /tmp/dvd.iso
md5sum /dev/sr0
```

![Captura 6](/recursos/2024-12-22/captura_06.png)


Comprobamos que el checksum del disco coincide con el de la imagen, le ponemos una etiqueta al disco con un rotulador permanente, y lo guardamos preferentemente en un cajón o armario 
para protegerlo de la luz solar.

