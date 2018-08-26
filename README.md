# Web de la Jaquería

Este es el repositorio de la web de la Jaquería, que está creada mediante [Jekyll][1], [Markdown][2] y `HTML/CSS`.

### ¿Cómo está construida?

La maquetación principal está hecha con`HTML/CSS`, sin embargo cada página individual está escrita en `markdown` con la idea de simplificar su creación y mantener un estilo uniforme.

Para las tareas de construcción, el encargado será **[Jekyll][1]**.

### ¿Cómo instalar Jekyll?

#### GNU/Linux

En distribuciones basadas en _Debian_ bastará un `apt-get install jekyll`. Como norma general siempre se puede instalar usando las _gems_ de _Ruby_, `gem install jekyll`.

#### Windows

Para instalar [Jekyll][1] en el sistema de Microsoft puedes seguir [este tutorial][3].

#### Mac OS X

Puede instalarse usando las _gems_ de _ruby_, `gem install jekyll`. Requiere las [Command Line Tools de XCode][4].

### ¿Cómo usar Jekyll?

Bastará con ir a la carpeta raíz de la web y ejecutar `jekyll serve`.


### ¿Cómo crear un post?

**Hay dos tipos de elementos en la web, los posts y las actividades**.
* Los posts se van a usar para comunicar noticias/cosas de la Jaquería.
* Las actividades serán actividades que se vayan a hacer en el espacio.

Para crear un nuevo post, debes copiar una de las plantillas (preferiblemente `ejemplo-post.md`) del directorio `_drafts` al directorio `_posts` y nombrarlo siguiendo el esquema fecha+nombre, como el resto. Por ejemplo:

```
2018-08-23-hola-mundo.md
```

Para poder ver el resultado final, deberás ejecutar Jekyll con `jekyll serve`

Una vez hayas terminado el post y quieras _publicarlo_, simplemente sube los cambios al repositorio.

### ¿Cómo crear una actividad?

Si lo que queremos es crear una actividad, debes copiar una de las plantillas (preferiblemente `ejemplo-actividad.md`) del directorio `_drafts` al directorio `_posts` y nombrarlo siguiendo el esquema fecha+nombre, como el resto. Por ejemplo:

```
2018-08-23-hola-mundo.md
```

Para poder ver el resultado final, deberás ejecutar Jekyll con `jekyll serve`

Una vez hayas terminado el post y quieras _publicarlo_, simplemente sube los cambios al repositorio.

### Licencia

© Los respectivos autores, 2015, 2016, 2017, 2018.
Licencia [Attribution 4.0 International (CC BY 4.0)][5]
[![Attribution 4.0 International (CC BY 4.0)](http://i.creativecommons.org/l/by/4.0/88x31.png "Attribution 4.0 International (CC BY 4.0)")][5]

[1]: http://jekyllrb.com
[2]: http://es.wikipedia.org/wiki/Markdown
