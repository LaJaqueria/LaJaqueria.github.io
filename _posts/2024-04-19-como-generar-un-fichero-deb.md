---
layout: post

title: Cómo generar un fichero deb
description: Lo mínimo imprescindible que debes saber para generar un fichero deb usando Makefile
date: 2024-04-19
author: "Pablo Ramos Blánquez"
category: blog
user: La Jaquería
---

# CÓMO GENERAR UN FICHERO DEB

Los archivos .deb o DEB son archivos comprimidos utilizados habitualmente en el sistema operativo Unix. Se suelen usar para llevar a cabo instalaciones en dicho sistema operativo.

Hoy hemos creado el archivo.deb para Perdita, el emulador que estamos usando para el proyecto Durango.

Para ello hemos tenido en cuenta varios requisitos:

* Versión(<strong>VERSION</strong>) -> 1.0.2
* Estructura(<strong>ARCH</strong>) -> amd64

Tanto la versión como la estructura las hemos guardado en una constante llamada <strong>TEMP_DIR</strong>, que a la vez guardamos en otra constante llamada <strong>CONTROL</strong> con la estructura *DEBIAN/control*.

Luego, hemos echo esta estructura:

```shel
make-deb: perdita
    mkdir $(TEMP_DIR)
    mkdir -p $(TEMP_DIR)/usr/local/bin
    mkdir -p $(TEMP_DIR)/DEBIAN

    cp perdita $(TEMP_DIR)/usr/local/bin

    echo "Package: perdita" > $(CONTROL)
    echo "Version: $(VERSION)" >> $(CONTROL)
    echo "Architecture: $(ARCH)" >> $(CONTROL)
    echo "Maintainer: Durango Computer Team" >> $(CONTROL)
    echo "Description: Perdita: Durango computer emulator." >> $(CONTROL)
    echo "Depends: libsdl2-dev (>=2.0.0)" >> $(CONTROL)
    dpkg-deb --build --root-owner-group $(TEMP_DIR)
```

Usamos la estructura */usr/local/bin* ya que es donde se aguardan las aplicaciones que han sido creadas y ejecutadas de forma independiente.

También la guardamos aquí porque es donde hemos especificado que se guarde en el .deb.

Usamos la estructura *DEBIAN/control* para guardar los metadatos del .deb.

Después hemos usado el siguiente comando en el terminal:

```shell
make make-deb
```
Y así generaríamos toda la estructura definida arriba.

Por último, usamos este comando para comprobar que todo ha sido insertado correctamente:

```shell
dpkg --info perdita_1.0.2_amd64.deb
```

* [tutorialDEv](https://www.devdungeon.com/content/debian-package-tutorial-dpkgdeb)

* [repositorioJuanjo](https://github.com/JuanjoSalvador/dog/blob/master/Makefile) 


