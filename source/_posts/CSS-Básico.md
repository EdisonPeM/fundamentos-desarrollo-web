---
title: CSS Básico
categories:
    - Fundamentos
---

# INTRODUCCIÓN

CSS significa **Hojas de estilo en cascada** (Cascading Style Sheets) y es un lenguaje de diseño que nos permite modificar los **estilos** de nuestra página de una forma flexible y genérica.

CSS se creó para cubrir la necesidad de definir un mecanismo que permitiera aplicar diferentes estilos a los documentos. Este lenguaje se impulsó con el crecimiento del lenguaje HTML. 

<!-- more -->

El organismo W3C (**World Wide Web Consortium**), el cual es el encargado de crear los estándares relacionados con programación Web, se le propusieron varias propuestas de hojas de estilo. Las dos propuestas que se tuvieron en cuenta son: CHSS (Cascading HTML Style Sheets) y SSP (Stream-based Style Proposal).  Estas dos propuestas se unieron entre 1994 y 1995 por Håkon Wium Lie y Bert Bos y definieron un lenguaje con lo mejor de cada una este fue llamado CSS (Cascading Style Sheet). 

En 1995, W3C apostó por este lenguaje y lo estandarizó. 

En 1998 se publicó la segunda versión de este lenguaje que fue llamada CSS nivel 2. Es la versión que se utiliza actualmente en los navegadores. Y ese mismo año se empezó con el desarrollo de CSS nivel 3 que continua en desarrollo actualmente.

Sin embargo, ya se han publicado especificaciones de CSS3 como Selectores, Colores, Fuentes, Entre otros.

[CSS: Cascading Style Sheets](https://developer.mozilla.org/en-US/docs/Web/CSS)

[1.2. Breve historia de CSS (Introducción a CSS)](https://uniwebsidad.com/libros/css/capitulo-1/breve-historia-de-css)

[Cascading Style Sheets Level 2 Revision 2 (CSS 2.2) Specification](https://www.w3.org/TR/CSS22/)

[Cascading Style Sheets](https://www.w3.org/Style/CSS/Overview.en.html)

## Reglas: Selectores y Propiedades

CSS se basa en el uso de **reglas** que permiten afectar los estilos de los elementos html, cada regla tiene 2 secciones:

- **Selectores**: Encargados de especificar los elementos a modificar
- **Declaraciones**: Establece las modificaciones de estilo correspondientes
    - **Propiedad**: Define qué característica se desea modificar
    - **Valor**: Es el valor de la propiedad, cada propiedad acepta un tipo específico de valores según el caso.

![unnamed.png](unnamed.png)

Estructura Básica de una regla CSS

Todas las propiedades deben estar separadas de su valor por **dos puntos ( : )** y deben finalizar siempre con **punto y coma ( ; ).**

# * *COMENTARIOS*

Los simbolos `/* */` definen comentarios en el código, es decir, lo que se encuentre dentro de estos simbolos no afectará en lo absoluto las reglas de estilo de nuestra página.

# Implementación de CSS

## **En Línea**

Podemos agregar estilos particulares a cada elemento de nuestro html por medio del atributo `style`, por lo que todas las etiquetas soportan el uso de este atributo, en este caso, el valor de este atributo serán **declaraciones CSS**.

```html
<tagName style="property_1: value_1;...; property_n: value_n;">
    Content
</tagName>
```

## Interno

Usando la etiqueta `<style>` dentro de la cabecera (`<head>`) del documento como se indica a continuación:

```html
<html>
<head>
   <style>
       /* Reglas CSS */
    </style>
</head>
<body></body>
</html>
```

## Externo

Usando un archivo con extensión **.css** en donde tengamos los estilos, este archivo se agrega a nuestro documento con la etiqueta `<link>` dentro de la cabecera del documento de la siguiente forma:

```html
<html>
<head>
   <link rel="stylesheet" href="filePath">
</head>
<body></body>
</html>
```

Donde `rel="stylesheet"` se refiere a que vamos a agregar una hoja de estilos, y `href="filePath"` hace referencia al archivo .css

### *FilePath*

Se le conoce como **FilePath** a la ubicación de un archivo dentro de un equipo, y existen dos formas de ubicar un archivo, con una “**ruta relativa**” y una “**ruta absoluta**”.

- **Ruta Absoluta**: Es la ubicación exacta de un archivo dentro de un pc
    - en Windows sería: `"C:\\users\Edison\Escritorio\miPaginaWeb\css\estilos.css"`
    - mientras que en Linux podría ser: `"/home/edison/Escritorio/miPaginaWeb/css/estilos.css"`

También se le llama ruta absoluta a las rutas de internet (URL)

- **Ruta Relativa**: Se refiere la ubicación de un archivo respecto a otro, para esto se deben seguir las siguientes reglas:
    - **Carpeta Actual**: usando un punto (`.`) podemos referirnos a la carpeta actual, por ejemplo si deseamos agregar una imagen dentro de nuestro `index.html` podemos usar la ruta: `"./css/estilos.css"`.
    - **Carpeta Superior**: usando punto punto (`..`) Diferente de dos puntos (`:`), podemos referirnos a una carpeta superior y luego ubicar un archivo, por ejemplo si deseamos cargar una imagen desde un documento html que se encuentra en una subcarpeta, se podría usar la ruta `"../css/estilos.css"`

El filepath es **casesensitive,** esto significa que hace distinción entre mayúsculas y minúsculas, siempre se deben indicar el nombre de las carpetas o archivos **exactamente** igual a como a parecen en el explorador de archivos.

# **Selectores**

Un selector es la forma en la que seleccionamos los elementos de nuestro html que deseamos modificar, estos selectores pueden hacer referencia a grupos de elementos o a elementos específicos y se puede escribir de diferentes maneras.

[CSS Selectors](https://www.w3schools.com/css/css_selectors.asp)

[Selectores CSS](https://developer.mozilla.org/es/docs/Web/CSS/Selectores_CSS)

## **Selector Universal**

Si deseamos que todos los elementos compartan estilos, pero no son heredables, se puede utilizar el selector universal ( * ).

Cuando se usa solo:

```css
* {
	width: 100%;
}
```

**TODOS** los elementos html de nuestra página compartirán esos estilos.

## *Nombre de la Etiqueta*

Cuando queremos modificar los estilos de ***TODOS los elementos que compartan la misma etiqueta*** en nuestro documento.

Con este selector solamente se escribe el nombre de la etiqueta, seguido del conjunto de reglas de estilo.

```css
p {
    /* Estilos para todos los parrafos */
}

img {
    /* Estilos para todas las imagenes */
}
```

## *ID del elemento*

Este selector lo usamos cuando queremos aplicar estilos ***unicamente al elemento que tiene este id***, dado que los identificadores son únicos, ningún otro elemento será afectado con estos estilos.

Para este selector se debe iniciar siempre con numeral (#) seguido del identificador del elemento y el conjunto de reglas de estilo.

```css
#p1 {
    /* Estilos para el elemento con id="p1" */
}

#p2 {
    /* Estilos para el elemento con id="p2" */
}

#p3 {
    /* Estilos para el elemento con id="p3" */
}
```

## *Clase del Elemento*

Este selector lo usamos cuando queremos aplicar estilos ***solamente al conjunto de elemento que compartan la misma clase***, de esta forma dejamos a un lado los elementos que no tengan dicha clase así compartan la misma etiqueta.

Para este selector se debe iniciar siempre con punto (.) seguido del nombre de la clase y el conjunto de reglas de estilo.

```css
.contenedor {
    /* Estilos para todos los elementos con class="contenedor" */
}
.contenido {
    /* Estilos para todos los elementos con class="contenido" */
}
```

# Propiedades Comunes

## Fuente

Con CSS también podemos modificar diferentes estilos del texto, el tipo de fuente, el tamaño de la letra, el estilo de letra e incluso la alineación.

[Typography - CSS Reference](https://cssreference.io/typography/)

[CSS Fonts](https://www.w3schools.com/css/css_font.asp)

[CSS Text](https://www.w3schools.com/css/css_text.asp)

### ***Font-Family***

Con la propiedad de `font-family` podemos cambiar el tipo de fuente para nuestro texto, entre las diferentes familias de fuentes posibles tenemos:

- *`Arial`*
- *`Helvetica`*
- *`Verdana`*
- *`Georgia`*
- *`Times New Roman`*
- *`Courier New`*
- *`Lucida console`*

Estas familias por lo general pertenecen a una categoría más grande, la cual es la *generic-family*, por lo que se suele usar esta generic-family en dado caso que el navegador no soporte la fuente que hemos agregado, de esta forma intentará mostrar una fuente similar que pertenezca a esa familia general.

Algunas familias generales son:

- *`serif`*
- *`sans-serif`*
- *`monospace`*

### ***Font-style***

La propiedad de font-style de la fuente puede tener dos valores

- *`normal`*: este es el valor por defecto
- *`italic`*: *este valor nos muestra la letra cursiva*

### ***Font-Weight***

Esta propiedad nos permite cambiar el grosor de la letra, sus posibles varlores son:

- *`normal`*: este es el valor por defecto
- *`bold`*: **este valor nos muestra la letra en negrita**

### *Font-variant*

Con esta propiedad nos permite mostrar la fuente en *"Pequeñas Mayúsculas"* usando el valor `small-caps`.

### ***Font-size***

Esta propiedad nos permite cambar el tamaño de la letra, por defecto la letra viene con un tamaño de *`16px`*;

## Texto

### ***Text-Transform***

La propiedad `text-transform` nos permite transformar un texto, sus posibles valores son:

- *`uppercase`*: Transforma el texto a mayusculas sostenidas.
- *`lowercase`*: Transforma el texto a minusculas sostenidas.
- *`capitalize`*: Transforma el texto a modo capitalize, el cual significa que la primera letra de cada palabra está en mayúsculas y el resto con minúsculas.

### ***Text-Align***

Con la propiedad de text-align podemos cambiar la presentación el texto entre:

- *`left`*: alineado a la izquierda (Valor por defecto)
- *`right`*: alineado a la derecha
- *`center`*: alineado en el centro
- *`justify`*: justificado

### *T**ext-decoration***

La propiedad `text-decoration` nos permite agregar lineas a nuestro texto como subrayados o tachados, sus posibles valores son:

- *`none`*: por defecto para el resto de elementos
- *`underline`*: por defecto para hipervínculos
- *`overline`*: Línea sobre el texto.
- *`line-through`*: línea a través del texto.

Estos últimos 3 se pueden combinar separándolos por espacio.

### ***Spacing***

Podemos también cambiar el espaciado indicando un **tamaño** en pixeles para las siguientes propiedades.

- `letter-spacing`: Espacio entre letras.
- `word-spacing`: Espacio entre palabras.
- `text-indent`: Identación de textos.
- `line-height`: Espacio entre líneas.

### ***Color***

La propiedad `color` nos permite cambiar el color de la letra, se debe especificar un color ya sea por el nombre, el código rgb o código hexadecimal.

## Colores

[CSS Colors](https://www.w3schools.com/css/css_colors.asp)

### **Nombre del color**

CSS tiene un gran diccionario de colores comunes como rojo (red), azul (blue), amarillo (yellow), verde (green), negro (**black**), blanco (white), entre muchos otros.

### **RGB**

El código rgb de un color es una combinación entre rojo, verde y azul, cada uno con un valor mínimo de 0 y máximo de 255, se utiliza con la palabra rgb de la siguiente forma:

```css
body { color: rgb(238, 130, 238); }
```

Algunos editores como Visual Studio Code, posee una herramienta que nos permite seleccionar el color deseado y automáticamente genera el código rgb como el siguiente.

![colors.jpg](colors.jpg)

Herramienta de selección de colores.

**Código Hexadecimal**

El código hexadecimal de un color es el mismo código rgb solo que en base 16, se utilizan los mismos colores base de rojo, verde y azul para generarlo. Para cada color se escribe su intensidad en base 16 y se escribe todo junto después del símbolo numeral ( # ).

Algunos colores son:

- Color Negro: `#000000`
- Color Rojo: `#FF0000`
- Color Verde: `#00FF00`
- Color Azul: `#0000FF`
- Color Amarillo: `#FFFF00`
- Color Blanco: `#FFFFFF`

### ***Transparencia***

Podemos agregar transparencia a un color agregando una cuarta base a nuestro código de color, esto solo funciona con rgb y hexadecimal.

Esta cuarta base se le conoce como alpha, e indica de 0 a 1 cuán transparente es nuestro color, siendo 1 completamente visible y 0 completamente transparente.

Para usarlo con **rgb** se debe cambiar la palabra a **rgba** de la siguiente forma:

```css
p { color: rgba(238, 130, 238, 0.75); }
```

```css
body { background-color: rgba(238, 130, 238, 0.75); }
```

## Fondo

La propiedad de fondo nos permite modificar el fondo de cualquier elemento de nuestro html, esta puede variar desde agregar un color de fondo hasta la forma de agregar imagenes de fondo.

[Backgrounds - CSS Reference](https://cssreference.io/backgrounds/)

[CSS Backgrounds](https://www.w3schools.com/css/css_background.asp)

[background](https://developer.mozilla.org/es/docs/Web/CSS/background)

### ***Background-color***

La propiedad de `background-color` nos permite cambiar el color de fondo de cualquier elemento.

### ***Background-Image***

También podemos agregar una imagen al fondo con la propiedad `background-image`, dando como valor el filePath de ésta dentro de la palabra url() de la siguiente forma.

```css
body { background-image: url(filePath); }
```

No solo el body puede tener una imagen de fondo, cualquier elemento html lo puede tener.

### *Background-size*

Si queremos cambiar el tamaño de la imagen del fondo, podemos usar la propiedad `background-size`, con ésta podemos tener:

- *`auto`*: valor por defecto, la imagen se muestra a su tamaño original
- *`cover`*: ajusta el tamaño de la imagen de fondo para cubrir todo el elemento manteniendo la proporción.
- *`contain`*: ajusta el tamaño de la imagen al tamaño del elemento.

### *Background-repeat*

Con la propiedad de `background-repeat` podemos decidir como repetir la imagen de fondo, pues por defecto no llena todo el espacio de nuestro elemento.

los posibles valores son:

- _`Repeat`: __Valor por defecto.
- *`No-repeat`*: No repetir.
- *`Repeat-x`*: repetir solamente horizontalmente.
- *`Repeat-y`*: repetir solamente verticalmente.

### *Background-position*

Con esta propiedad ajustamos la posición donde se ubicará la imagen de fondo con respecto a nuestro contenedor, sus valores son:

- *`left top`*: Esquina Superior Izquierda
- *`center top`*: Lado Superior Centrado
- *`right top`*: Esquina Superior Derecha
- *`left center`*: Lado Izquierdo Centrado
- *`center`*: Centro
- *`right center`*: Lado Derecho Centrado
- *`left bottom`*: Esquina Inferior Izquierda
- *`center bottom`*: Lado Inferior Centrado
- *`right bottom`*: Esquina Inferior Derecha

### *Background-attachment*

Con la propiedad `background-attachment` podemos cambiar la forma en la que nuestra imagen es fijada al fondo de nuestro elemento:

- *`scroll`*: *valor por defecto*, la imagen se mueve junto con la página, por lo que si sube, la imagen sube, y si baja baja.
- *`fixed`*: la imagen siempre se verá al fondo de nuestra pantalla sin importar si esta sube o baja.

# Referencia Completa de Propiedades CSS

[CSS Reference](https://cssreference.io/)

[CSS Reference - Codrops](http://tympanus.net/codrops/css_reference/)

[Referencia CSS](https://developer.mozilla.org/es/docs/Web/CSS/Referencia_CSS)
