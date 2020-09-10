---
title: HTML Básico
categories:
    - Fundamentos
---

# Introducción

El *desarrollo web* es un término que se refiere la creación de páginas, sitios y aplicaciones web, éste tiene formas diferentes según la complejidad de un proyecto: desde la creación de páginas web con gestores de contenido como **Wordpress o Wix**, o la creación de páginas web con solamente **HTML y CSS**, hasta la implementación de frameworks de javascript, que permiten crear páginas más rápidas y con un diseño reactivo y basado en componentes.

<!-- more -->

Independientemente del nivel de complejidad de una página, toda la web está basada en **HTML** o **Lenguaje de Marcado de Hipertexto**, el cual fue creado desde 1980 por *Tim Berners-Lee* como la propuesta de "*hipertexto"* (*El hipertexto es texto que contiene enlaces a otros textos*) sobre el que se basaría el programa de la **World Wide Web** (*www*) lanzado en 1991, sistema de distribución de documentos de hipertexto o hipermedia interconectados y accesibles a través de **Internet.** 

[Tim Berners-Lee y el origen de la Web | OpenMind](https://www.bbvaopenmind.com/tecnologia/visionarios/tim-berners-lee-y-el-origen-de-la-web/)

[World Wide Web](https://es.wikipedia.org/wiki/World_Wide_Web#Historia)

[1.2. Breve historia de HTML (Introducción a XHTML)](https://uniwebsidad.com/libros/xhtml/capitulo-1/breve-historia-de-html)

> Con un **navegador web**, un usuario visualiza **sitios web** compuestos de **páginas web** que pueden contener textos, imágenes, vídeos u otros contenidos multimedia, y navega a través de esas páginas usando hipervínculo.

En octubre de 1994, *Tim Berners-Lee* fundó el **World Wide Web Consortium (W3C)**, Organismo encargado de crear todos los estándares relacionados con la web, para así crear una web universal, accesible y fácil de usar para todo el mundo.

Estos estándares se publican en diferentes niveles según su maduración y aceptación:

- Borrador de trabajo (WD)
- Recomendación candidata (CR)
- Recomendación propuesta (PR)
- Recomendación de W3C (REC)

[El proceso de estandarización de la W3C](https://desarrolloweb.com/articulos/proceso-estandarizacion-w3c.html)

[Estándares Web W3C - Qué son, cómo funciona, para qué sirven](https://disenowebakus.net/estandares-web.php)

En Octubre del 2014 tras varias revisiones, se publicó el estándar **HTML5** (HTML versión 5), con el que se agregan nuevas etiquetas y funcionalidades a HTML. La última recomendación de la w3c es HTML 5.2 en Diciembre de 2017.

[HTML5](https://developer.mozilla.org/es/docs/HTML/HTML5)

## Etiquetas

HTML es un lenguaje de marcado que se basa en el uso de etiquetas, con las que un navegador da formato al contenido de las mismas. Según el tipo de etiqueta el navegador podrá mostrar el texto de una determinada forma, crear hipervínculos, o cargar archivos multimedia.

Todas las etiquetas se definen dentro de paréntesis angulares ( < > ) para distinguirlas del contenido de la página misma.

Todos los elementos que existen en una página web, están definidos entre una **etiqueta de apertura** y una **etiqueta de cierre** (la etiqueta de cierre generalmente utiliza el símbolo </ >)

![tagbreakdown.png](tagbreakdown.png)

![html-element-structure.png](html-element-structure.png)

Estructura básica de un elemento HTML

En este ejemplo, la etiqueta `<p>` representa la **etiqueta de apertura** de un párrafo, *“Hello Wold”* es el contenido del párrafo, y la etiqueta `</p>` determina el final de este párrafo siendo la **etiqueta de cierre**.

Algunas pocas etiquetas no utilizan **etiqueta de cierre**, como `<meta>` `<img>` `<br>` y `<hr>`, este tipo de etiquetas se les denomina **self-closing** o **void-elements (***elementos vacíos***)**, porque no almacenan un contenido en sí.

![void_element_breakdown.png](void_element_breakdown.png)

Estructura de un elemento sin etiqueta de cierre.

## Atributos

Todas las etiquetas de HTML soportan el uso de **atributos** que modifican su presentación y configuración dentro de la página.

![Untitled.png](Untitled.png)

Estructura de un elemento HTML con Atributos.

En este ejemplo se muestra un hipervínculo, el cuál utiliza el atributo **href**, en este atributo se indica la url a la que redirecciona dicho hipervínculo.

A la hora de agregar atributos siga estas recomendaciones:

- Todos los atributos se escriben justo después del nombre de la etiqueta y antes del símbolo mayor que **( > )**
- Todos los atributos van separados por un espacio entre sí.
- Cada atributo va acompañado de su respectivo valor después del símbolo igual **( = )**
- Los valores de cualquier atributo deben ir siempre entre comillas dobles **( " " )**
- En las etiquetas de cierre no se escriben atributos

[HTML Attributes](https://www.w3schools.com/html/html_attributes.asp)

## Atributos Globales

Todos los elementos de html comparten ciertos atributos como: **id**, **class**, **style**, **title,** entre otros. Sin embargo otros elementos tienen atributos específicos para cumplir su función, como lo son **src** para cargar imágenes o **href** para especificar la URL de un hipervínculo.

### **Atributo ID**

El atributo *`id`*, nos permite agregar un **identificador único** a cualquier elemento html, lo que significa que cualquier etiqueta podrá tener este atributo, con un *`id`* se podrá diferenciar los elementos entre sí a la hora de agregar manipular el documento con Javascript.

### **Atributo CLASS**

El atributo *`class`* permite crear una **clasificación de elementos**, ya sean un subconjunto del mismo tipo de etiqueta o varios de diferente tipo de etiqueta, cualquier elemento html puede tener una o más clases y lo utilizamos cuando queremos agrupar elementos para que compartan estilos.

### **Atributo TITLE**

El atributo *`title`* se utiliza para generar un elemento informativo sobre cualquier elemento, este atributo se agrega en cualquier elemento seguido de un mensaje que se mostrará cuando el usuario pase el mouse por encima de nuestro elemento.

## **FILE SYSTEM**

El **File System** o sistema de gestión de archivos, es la forma en la que los archivos están organizados dentro de nuestro equipo, todos los archivos se organizan en carpetas, y éstas a su vez pueden tener carpetas dentro.

```bash
Escritorio:
	  Proyecto:
		    - Archivo1
		    Imágenes:
			      - imagen.png
```

El sistema de archivos básico de un proyecto web es similar al siguiente:

```
miPaginaWeb:
    - index.html
    images:
        - userProfile.jpg
        - fondo.png
    css:
        - style.css
    js:
        - script.js
```

# ** COMENTARIOS*

HTML permite agregar comentarios usando las etiquetas `<!-- Esto es un Comentario -->` 
lo que se encuentre dentro de esta etiquetas no será procesado por el navegador.

# **Head y Body**

Una página HTML en blanco tiene la siguiente estructura:

```html
<!DOCTYPE html>
<html>
<head>
    <!-- Meta Datos -->
</head>
<body>
    <!-- Elementos -->
</body>
</html>
```

La etiqueta `<!DOCTYPE html>` nos indica que nuestro archivo es de tipo HTML y que estamos usando el estándar HTML5 mientras que la etiqueta `<html>` da comienzo al documento.

Todo documento web está dividido en dos partes **Head y Body** definidos por la etiqueta `<head>`  y la etiqueta `<body>` respectivamente.

Todo lo que se defina dentro de la **cabecera del documento** (Head) no se mostrará en nuestra página, mientras que en el **cuerpo del documento** (Body) se encuentran todos los elementos visuales de una página web, como párrafos, imágenes, botones y demás.

## **HEAD**

En esta parte del html se definen **meta-datos** como el nombre de la página, el autor, la descripción, el título o incluso el lenguaje.

### **Meta Datos**

Los Meta-datos es información que no se muestra al usuario pero que nos ayudan a configurar y darle una descripción a nuestra página, estos meta datos se agregan en la cabecera del documento.

[¿Qué hay en la cabecera? Metadatos en HTML](https://developer.mozilla.org/es/docs/Learn/HTML/Introduccion_a_HTML/Metados_en)

### ***Lenguaje***

Podemos especificar en qué lenguaje se encuentra el contenido de nuestra página, éste se puede hacer de dos formas, con la etiqueta `<meta>` de la siguiente forma:

```html
<html>
<head>
    <meta http-equiv="Content-Language" content="es">
</head>
<body></body>
</html>
```

o , como atributo en la etiqueta `<html>` con el atributo `lang`.

```html
<html lang="es">
<head></head>
<body></body>
</html>
```

El lenguaje se define por diminutivos, *“es”* significa “español”, “inglés” sería *“en”* (english), y así con los demás idiomas, “francés” sería *“fr”*, “alemán” sería *“de”*, “portugués” sería “pt”, etc.

[HTML Language Code Reference](https://www.w3schools.com/tags/ref_language_codes.asp)

### ***Charset***

El charset define un conjunto de caracteres para manejar en la página, el conjunto de caracteres más común y genérico es el **UTF-8**, con este charset podemos utilizar todos los caracteres conocidos sin ningún problema, como tíldes, tíldes invertidas, diéresis, ñ, entre muchos otros como **ASCII**, **ANSI**, etc, éste se agrega con la etiqueta `<meta>` de la siguiente forma:

```html
<html>
<head>
    <meta charset="UTF-8">
</head>
<body></body>
</html>
```

[HTML Charset](https://www.w3schools.com/html/html_charset.asp)

### ***Metas Descriptivos***

Podemos agregar metadatos sobre el Autor, la Descripción y Palabras Clave para describir nuestra página, estos se indican con la etiqueta `<meta>` de la siguiente forma:

```html
<html>
<head>
    <meta name="author" content="Edison Peñuela">
    <meta name="description" content="mi primera página">
    <meta name="keywords" content="html, tutorial">
</head>
<body></body>
</html>
```

Se pueden agregar más metadatos indicando el nombre del metadato en el atributo `name` y su respectivo valor en el atributo `content`.

### ***Título***

El título del documento es lo que muestra en la parte superior de una pestaña o ventana del navegador, este título se agrega con la etiqueta `<title>`

```html
<html>
<head>
    <title>Document</title>
</head>
<body></body>
</html>
```

En el ejemplo anterior *`Document`* sería el título de nuestra página.

[: The Document Title element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/title)

### ***Favicon***

El favicon es la pequeña imagen que aparece junto al nombre de nuestra página en la pestaña del navegador, para agregar un favicon a nuestro documento basta con agregar un archivo llamado favicon.ico en la misma carpeta que nuestro index.html.

```
miProyecto:
    - index.html
    - favico.ico
```

Nuestro ícono debe tener el formato **ico**, para lo cual existen conversores de *png* o *jpg* a ico, el tamaño del favicon generalmente es de 16x16 píxeles, pero en otros lugares como los marcadores puede tener un tamaño mayor (24x24, 32x32, 48x48 o 64x64).

Si se desea cargar otro formato de imagen, como png o jpg, se debe utilizar la etiqueta `<link>` de la siguiente forma:

```html
<html>
<head>
   <link rel="icon" type="image/x-icon" href="filePath">
</head>
<body></body>
</html>
```

[Favicon](https://www.mclibre.org/consultar/htmlcss/html/html-favicon.html)

### ***Otros Metadatos***

Existen muchos metadatos que nos ayudan a configurar una página web, por ejemplo el *viewport* que nos ayuda a configurar nuestro sitio para ser responsive y se agrega de la siguiente forma:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### ***Estructura inicial***

Para comenzar a crear una página, es recomendable partir de una estructura como la siguiente, en donde los meta-datos son agregados al inicio y así solo nos preocuparemos por el contenido del documento.

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <!-- Metas Suficientes --->
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>

    <!--- Metas Adicionales -->
   <link rel="icon" type="image/png" href="filePath">
    <meta name="author" content="Edison Peñuela">
    <meta name="description" content="mi primera página">
    <meta name="keywords" content="html, tutorial">
</head>
<body>
</body>
</html>
```

## BODY

En el body se escriben todos los elementos que se visualizan en nuestra página, como títulos, párrafos, listas, tablas y demás. Para los ejemplos de este punto en adelante, se asume que están escritos dentro de la etiqueta `<body>`.

## Elementos Comunes

### ***Párrafos***

Aunque bien se puede escribir texto directamente en el `<body>`, se recomienda y se suele utilizar siempre párrafos para separar y manipular estos textos.

Para crear párrafos se utiliza la etiqueta `<p>`  y todo lo que esté escrito entre esta etiqueta se mostrará como un bloque sólido de texto, sin embargo siempre inicia en una línea nueva y genera un salto de línea al final.

```html
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam volutpat nisi massa,sit amet rutrum erat pharetra in. Suspendisse ultrices, turpis et imperdiet maximus, ante metus vehicula dolor, in suscipit nisi sapien a diam. Cras eget nunc tortor. Suspendisse potenti.
</p>
```

### ***Títulos***

Para generar títulos en html existe un conjunto de etiquetas llamadas cabeceras, éstas etiquetas son:

- `<h1>`: Crea un título principal
- `<h2>`: Crea un título secundario
- `<h3>`: Crea un título 3
- `<h4>`: Crea un título 4

    *Este título tiene el mismo tamaño que la letra normal en negrita.*

- `<h5>`: Crea un título 5
- `<h6>`: Crea un título 6

[HTML Paragraphs](https://www.w3schools.com/html/html_paragraphs.asp)

[HTML Headings](https://www.w3schools.com/html/html_headings.asp)

[Fundamentos de texto en HTML](https://developer.mozilla.org/es/docs/Learn/HTML/Introduccion_a_HTML/texto)

### *Modificadores de **Texto***

Existen además, una colección de etiquetas que nos ayudan a dar formato al texto dentro del navegador, estas etiquetas pueden ser usadas dentro de los títulos como dentro de los párrafos.

- `<b>`: Crea un texto en negrita (**bold**).
- `<strong>`: Crea un texto reforzado

    se muestra también en negrita, pero indica que tiene más importancia que los demás

- `<i>`: Crea un texto en cursiva (*italic*).
- `<em>`: Crea un texto enfatizado

    se muestra también en cursiva, pero indica que es relevante

- `<u>`: Crea un texto subrayando (underline).
- `<del>`: Crea un texto tachado (deleted).
- `<small>`: Crea un texto con letra pequeña.
- `<sup>`: Crea un texto en superíndice.
- `<sub>`: Crea un texto en subíndice.
- `<mark>`: Crea un texto resaltado.

[HTML Text Formatting](https://www.w3schools.com/html/html_formatting.asp)

### ***Saltos de Línea***

Se pueden crear saltos de línea con la etiqueta `<br>` justo después de cualquier elemento.

```html
<p>
    Texto Normal<br>
    <b>Texto en negrita</b><br>
    <i>Texto en cursiva</i><br>
    <u>Texto subrayado</u><br>
    <small>Letra pequeña</small><br>
    <del>Texto tachado</del><br>
    <strong>Texto reforzado</strong><br>
    <sup>Texto en superíndice</sup><br>
    <sub>Texto en subíndice</sub><br>
    <mark>Texto resaltado</mark>
</p>
```

### ***Separador con línea horizontal***

Con la etiqueta `<hr>` podemos generar una línea horizontal para separar elementos verticalmente.

```html
 <p>    
		Texto Normal<br>
    <b>Texto en negrita</b><br>
    <i>Texto en cursiva</i><br>
    <u>Texto subrayado</u><br>
    <small>Letra pequeña</small>
</p> 
<hr>
<p>
    <del>Texto tachado</del><br>
    <strong>Texto reforzado</strong><br>
    <sup>Texto en superíndice</sup><br>
    <sub>Texto en subíndice</sub><br>
    <mark>Texto resaltado</mark>
</p>
```

Las etiquetas `<br>` y `<hr>` son **self-closing**, es decir, no usan etiqueta de cierre.

### ***Hipervínculos***

Para agregar hipervínculos a nuestra página, se utiliza la etiqueta `<a>`, esta etiqueta utiliza varios atributos:

- `href`: La dirección URL a donde apunta este hipervínculo.

Podemos indicarle a un link, en dońde abrir su contenido usando el atributo `target`, el valor por defecto es la misma pestaña, sin embargo podemos indicarle que abra en una pestaña nueva con *`_blank`*. Además se agrega el atributo `rel="noopener noreferrer"` para evitar vulnerabilidades causadas por sitios externos.

```html
<a href="https://google.com" target="_blank" rel="noopener noreferrer">
    go to google
</a>
```

El atributo *`title`* se utiliza para generar un elemento informativo sobre cualquier elemento, este atributo indica un mensaje que se mostrará cuando el usuario pase el mouse por encima de nuestro elemento. 

- `title`: Este atributo es genérico para todos los elementos, pero se suele utilizar en los hipervínculos para mostrar a cuál página se redireccionará.

```html
<a href="https://google.com" target="_blank" title="google.com">
    go to google
</a>
```

**Navegación Local**

Otra forma de usar hipervínculos es de forma local, esto es que abran páginas html que estén dentro de nuestro proyecto, o que hagan referencia a elementos dentro de nuestra propia página (como un índice de contenido).

- Para hacer referencia a archivos locales, le indicamos el **filePath** del archivo html.
- Para hacer referencia a elementos dentro de nuestra página usamos los **id**, indicamos el nombre del id justo después del símbolo numeral #**.**

```html
<a href="about.html">
    Alguna página
</a>

<a href="#chapter-2">
    go to links
</a>
```

[https://developer.mozilla.org/es/docs/Learn/HTML/Introduccion_a_HTML/Creating_hyperlinks](https://developer.mozilla.org/es/docs/Learn/HTML/Introduccion_a_HTML/Creating_hyperlinks)

[HTML Links](https://www.w3schools.com/html/html_links.asp)

### *Listas*

Existen dos tipos de listas en html:

- `<ol>`: listas ordenadas
- `<ul>`: listas No ordenadas

Ambos tipos de listas utilizan la etiqueta `<li>` (í*tems de lista*) para mostrar sus elementos.

```html
<p>Lista No Ordenada</p>
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ul>

<p>Lista Ordenada</p>
<ol>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ol>
```

Dentro de los ítems de lista pueden haber más elementos, como títulos, párrafos u otras listas.

```html
<ol>
    <li>Item 1
				<ol>
				    <li>Item 1-1</li>
				    <li>Item 1-2</li>
				    <li>Item 1-3</li>
				</ol>
		</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ol>
```

Sin embargo se puede indicar cuál es el tipo de numeración para cada sub-lista con los siguientes atributos:

- `type`: Define el tipo de numeración a utilizar, sus posibles valores son:
    - *`"1"`, `"i"`, `"I"`, `"a"`, `"A"`*
- `start`: Define el número en el que inicia la numeración.

```html
<ol type="A">
    <li>Item 1
				<ol type="i">
				    <li>Item 1-1</li>
				    <li>Item 1-2</li>
				    <li>Item 1-3</li>
				</ol>
		</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ol>
```

Las listas no deben ir dentro de párrafos o Títulos.

[Lists - HTML Reference](https://htmlreference.io/lists/)

[HTML Lists](https://www.w3schools.com/html/html_lists.asp)

### ***Tablas***

Para generar elementos tipo tabla se utilizan las etiquetas:

- `<table>`: Esta etiqueta genera una tabla
- `<thead>`: Genera el grupo de títulos.
- `<th>`: Describe cada título de la tabla
- `<tbody>`: Genera el grupo de valores.
- `<tr>`: Genera las filas de la tabla.
- `<td>`: Aquí se encuentran los datos mismos.
- `<caption>`: Se utiliza para agregarle un título propio a la tabla.

La estructura básica de una tabla es de la siguiente forma:

```html
<table>
		<caption>Mi Tabla</caption>
    <thead>
        <tr>
            <th>Título 1</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Celda 1</td>
        </tr>
    </tbody>
</table>
```

Podemos agregar el atributo `border="1"` a la etiqueta table, para agregar un borde básico.

La forma de las tablas puede variar usando algunos atributos:

- `rowspan`: Permite extender una celda a lo largo de *`n`* filas.
- `colspan`: Permite extender una celda a lo largo de *`n`* columnas

[Tables - HTML Reference](https://htmlreference.io/tables/)

## **Multimedia**

Todos los archivos multimedia se agregan como referencia al html, es decir, se le indica a las etiquetas la ubicación de los archivos multimedia que queremos cargar a la página web, y el navegador se encargará de mostrarlo en pantalla.

### *FilePath*

Se le conoce como **FilePath** a la ubicación de un archivo dentro de un equipo, y existen dos formas de ubicar un archivo, con una “**ruta relativa**” y una “**ruta absoluta**”.

- **Ruta Absoluta**: Es la ubicación exacta de un archivo dentro de un pc
    - en Windows sería: `"C:\\users\Edison\Escritorio\miPaginaWeb\imagenes\usuario.png"`
    - mientras que en Linux podría ser: `"/home/edison/Escritorio/miPaginaWeb/imagenes/usuario.png"`

También se le llama ruta absoluta a las rutas de internet (URL)

- **Ruta Relativa**: Se refiere la ubicación de un archivo respecto a otro, para esto se deben seguir las siguientes reglas:
    - **Carpeta Actual**: usando un punto (`.`) podemos referirnos a la carpeta actual, por ejemplo si deseamos agregar una imagen dentro de nuestro `index.html` podemos usar la ruta: `"./images/userProfile.jpg"`.
    - **Carpeta Superior**: usando punto punto (`..`) Diferente de dos puntos (`:`), podemos referirnos a una carpeta superior y luego ubicar un archivo, por ejemplo si deseamos cargar una imagen desde un documento html que se encuentra en una subcarpeta, se podría usar la ruta `"../images/userProfile.png"`

El filepath es **case sensitive,** esto significa que hace distinción entre mayúsculas y minúsculas, siempre se deben indicar el nombre de las carpetas o archivos **exactamente** igual a como a parecen en el explorador de archivos.

### Imágenes

Para agregar una imagen a nuestro html, debemos usar la etiqueta `<img>`, esta se debe usar con 2 atributos obligatorios:

- `src`: En este atributo indicamos la dirección del archivo de nuestra imagen.
- `alt`: En este atributo indicamos un texto alternativo en caso que no cargue la imagen.

```html
<img src="filePath" alt="Imagen">
```

En adicional se pueden agregar el alto y el ancho con los atributos:

- `height`: Indica el alto en píxeles
- `width`: Indica el ancho en píxeles

```html
<img src="450_1000.jpg" alt="Imagen Luna" height="100px" width="150px">
```

Se puede indicar un valor para un alto o ancho especifico y el valor complementario se ajustará automáticamente

```html
<img src="450_1000.jpg" alt="Imagen Luna" width="100px">
```

[HTML Images](https://www.w3schools.com/html/html_images.asp)

[: The Image Embed element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)

### *Audios*

Para agregar un audio a nuestra página usamos la etiqueta `<audio>`, esta etiqueta necesita de la etiqueta `<source>` que tendrá la fuente o fuentes de audio.

```html
<audio controls>
    <source src="audioName.mp3" type="audio/mpeg">
    <source src="audioName.ogg" type="audio/ogg">
    Your browser does not support the audio element.
</audio>
```

HTML5 soporta la mayoría de tipos de audios existentes actuales.

Esta etiqueta de audio soporta los siguientes atributos:

- `controls`: Muestra los controles del audio, si no se agrega este atributo no se mostrará el clip de audio.
- `autoplay`: Cuando se tiene este atributo el clip de audio se reproduce solo.
- `loop`: Establece si al terminar el audio se volverá a repetir o no.

Este tipo de Atributos no usa un valor especifico, se les llama **atributos booleanos** ya que el navegador reconocerá si tiene o no tiene dicho atributo para renderizar el elemento.

Si no se muestra el clip, osea, si no se tiene el atributo `controls`, pero tiene `autoplay` y `loop` puede funcionar como sonido de fondo.

La etiqueta `<source>` utiliza dos atributos:

- `src`: Con el que se le indica la dirección del archivo (filePath) del clip de audio.
- `type`: Para indicar el tipo de archivo multimedia que se está cargando, si es audio se debe indicar el valor de: *`audio/[extension]`*.

[: The Embed Audio element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)

[HTML Audio](https://www.w3schools.com/html/html5_audio.asp)

### Videos

Para agregar un video a nuestra página usamos la etiqueta `<video>`, al igual que `<audio>` esta etiqueta necesita de la etiqueta `<source>`, la cuál tendrá la fuente o fuentes de video.

```html
<video controls>
  <source src="videoName.mp4" type="video/mp4">
  <source src="videoName.ogg" type="video/ogg">
  Your browser does not support HTML5 video.
</video>
```

HTML5 soporta la mayoría de tipos de video existentes actuales.

Esta etiqueta de video soporta los mismos atributos que la etiqueta de audio.

Para el caso de la etiqueta `<source>` en video cambia el type, y se debe usar el valor de: *`video/[extension]`.*

[: The Video Embed element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)

[HTML Video](https://www.w3schools.com/html/html5_video.asp)

### ***Embebidos***

Muchas veces queremos agregar parte de otras páginas dentro de la nuestra, como comentarios de **twitter**, videos de **youtube** o publicidad de **google adds**, a estos elementos se les conoce como embebidos.

Al **compartir** un video de youtube podemos generar el código para un elemento **embebido** en nuestro html que muestre el respectivo video

![Untitled1.png](Untitled1.png)

Compartimos un video de youtube.

Opción Incorporar:

![Untitled2.png](Untitled2.png)

![Untitled3.png](Untitled3.png)

```html
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZbZSe6N_BXs" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

Usando embebidos podemos mostrar una página que hayamos creado dentro de otra, usando la etiqueta `<iframe>` y sus atributos `src`, en donde escribiremos la dirección (`filePath`) de nuestro archivo html.

```html
<iframe src="./about.html"></iframe>
```

[: The Inline Frame element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)

[HTML YouTube Videos](https://www.w3schools.com/html/html_youtube.asp)

# Referencia Completa de Etiquetas HTML

[HTML Reference](https://htmlreference.io/)

[Referencia de Elementos HTML](https://developer.mozilla.org/es/docs/Web/HTML/Elemento)

[HTML Reference](https://www.w3schools.com/tags/default.asp)
