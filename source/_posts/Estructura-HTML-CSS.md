---
title: Estructura HTML/CSS
categories:
    - Fundamentos
---

# Estructura de Contenedor / Contenido

## Contenedores

Se considera contenedor a cualquier elemento **HTML** que tenga etiqueta de apertura y cierre, sin embargo según la etiqueta se define el modelo de contenido que puede almacenar.

Los **contenedores** son espacios de almacenamiento de código HTML, en donde podemos organizar, estructurar y diseñar nuestra página web.

Existen diversos tipos de contenedores, inicialmente tenemos el contenedor **Raiz** del documento, el cuál se crea con la etiqueta `<html>` y tenemos el contenedor de todos los elementos visuales, el cual se define con la etiqueta `<body>`.

<!-- more -->

### Contenedores Genéricos

Cada etiqueta de html define diferentes tipos de contenedores, pero muchas veces su contenido en muchos casos es específico o limitado (como `<table>` con `<thead>` y `<tbody>` o `<ul>` con `<li>`).

Sin embargo existen etiquetas de HTML que nos permite agrupar contenidos de nuestra página web, y con los que podemos organizar la estructura de nuestra página web de una forma más flexible. Las etiquetas que usamos como contenedores son:

- `<span>`: Generalmente se utiliza para modificar los estilos de un texto en particular.
- `<div>`: Permite crear divisiones en el documento, puede contener cualquier tipo de contenido así como otros elementos div.

Los contenedores en bloque son los más usados para estructurar una página, siendo `<div>` el más habitual de todos, dado que `div` no tiene significado semántico dentro de una página.

### Contenedores Semánticos

En HTML también existen etiquetas que nos permiten organizar el contenido de una página web según su significado semántico dentro de la página como cabeceras, pie de página, barra de navegación, contenido principal, contenido secundario, entre otros.

## Tipo de Contenido

Todos los elementos de HTML tienen definido qué tipo de contenido pueden contener y qué no. Así mismo cada elemento HTML se clasifica en uno o más **modelos de contenido.**

![Untitled.png](Untitled.png)

Modelos de Contenido.

[Categorías de contenido](https://developer.mozilla.org/es/docs/Web/Guide/HTML/categorias_de_contenido)

[HTML5](https://www.w3.org/TR/2011/WD-html5-20110525/content-models.html)

### Metadata

En este modelo se agrupan los metadatos de la página, estos pueden modificar el comportamiento de la página, así como asociar recursos externos, como hojas de estilo, scripts, favicon, entre otros.

### Flow

A esta categoría pertenece la mayor parte de los elementos HTML, generalmente estos elementos contienen texto o contenido incrustado.

### Sectioning

En esta categoría se encuentran los contenedores de HTML5 que discriminan secciones de una página web.

### Heading

En esta categoría se encuentran las etiquetas de título (*h1...h6*), debe contener únicamente los títulos.

### Phrasing

El contenido de frase define el texto y el marcado (*modificación*) que contiene, por lo que la redacción de esta categoría forma párrafos.

### Embebed

El contenido incrustado importa otro recurso o inserta contenido de otro lenguaje de marcado o espacio de nombres en el documento, como los elementos de multimedia.

### Interactive

Se considera contenido interactivo cuando el usuario puede interactuar con estos elementos, como videos y audios cuando tienen controls, links, botones o inputs.

# Interpretación de **Estilos**

## Cascada y Especifidad

Todos los elementos de HTML tienen valores iniciales para cada una de las propiedades de css, estos valores iniciales son proporcionados por cada navegador y se les conoce como **estilos predeterminados** o "**estilos de usuario-agente**".

La mayoría de las propiedades de css tienen el mismo valor predeterminado en cualquier navegador, pues éstos deben seguir los estándares de la w3c.

Cuando definimos reglas de estilo para nuestro documento (ya sea externo o interno) estamos modificando estos valores iniciales.

El navegador lee las reglas de estilos y los va interpretando en forma de cascada (*de arriba hacia abajo*), por lo que si tenemos dos reglas que cumplen el mismo objetivo se cumplirá la última regla definida. Sin embargo, si se define una regla con mayor importancia (*Especifidad*) que otra, se tendrá en cuenta, así se escriba antes.

**Selectores de ID** tienen mayor importancia que **Selectores de Clase**, y éstos a su vez tienen mayor importancia que **Selectores de etiqueta**.

## Herencia

**Algunas** propiedades de css tienen la característica de que son heredables, esto significa que los elementos que son descendientes de un contenedor con estilos heredables, también compartiran estos estilos.

La mayoría de propiedades heredables son:

- [Fuentes](https://www.notion.so/CSS-B-sico-969b70e895db4d99baa516e7ba21241a#2dd6b10ed16a41a1be03c2d78d40ef14)
- [Texto](https://www.notion.so/CSS-B-sico-969b70e895db4d99baa516e7ba21241a#e3218efd0f5147bb93e59626ae4ee8a1)
- [Color de Texto](https://www.notion.so/CSS-B-sico-969b70e895db4d99baa516e7ba21241a#dff73345f0d8459d976bde706e410475)
- Estilos de Listas (Numeración)
- Estilos de Tablas (Border-Collapse)

Sin embargo, la mayoría de las propiedades NO son heredables, como

- [Fondos](https://www.notion.so/CSS-B-sico-969b70e895db4d99baa516e7ba21241a#27a0b5c145164fd1a312acc95c8f4c6d)
- Tamaños (Modelo de Cajas)

[Cascading Style Sheets (CSS) Snapshot 2010](https://www.w3.org/TR/css-2010/#properties)

## Control de la Herencia

Como no todas las propiedades son heredables en css, se puede usar el valor `inherit` para definir explícitamente la herencia de dichas propiedades.

Por el contrario, cuando tenemos propiedades heredadas, pero queremos cancelar dicha herencia, podemos usar el valor `initial` para que el elemento use los valores iniciales según la etiqueta.

[Herencia](https://developer.mozilla.org/es/docs/Web/CSS/inheritance)

[CSS - Herencia y cascada](https://mosaic.uoc.edu/ac/le/es/m6/ud2/)

[Cascada y herencia](https://developer.mozilla.org/es/docs/Learn/CSS/Building_blocks/Cascada_y_herencia)

# Renderización Web

## DOM

Cuando escribimos HTML y abrimos un archivo de este tipo desde un navegador, el navegador se encarga de transformar el código en el **Modelo de Objetos del Documento** (*Document Object Model* - DOM).

Éste se trata de una estructura jerárquica padre-hijo (*contenedor-contenido*) de todos los elementos que componen la página web. En esta estructura, cualquier elemento (*etiqueta html*) que se encuentre como contenido de otro elemento será considerado como un *"**hijo**"* del primero y el primero será considerado como el "***padre**"* del segundo.

Podemos visualizar el **DOM** como una estructura de árbol de la siguiente forma:

![Untitled1.png](Untitled1.png)

Esta estructura la podemos visualizar con las **herramientas de desarrollador** (Consola) de los navegadores.

También podemos manipular el DOM desde código JavaScript, con ésto podemos generar páginas dinámicas.

[Qué es el DOM](https://desarrolloweb.com/articulos/que-es-el-dom.html)

[Qu es el Modelo de Objetos del Documento?](http://html.conclase.net/w3c/dom1-es/introduction.html)

## CSSOM

Mientras que el DOM captura los elementos y relaciones de HTML, el CSSOM captura el aspecto que debe tener cada elemento al representarse en el navegador.

Al interpretar los estilos de la página, el navegador comienza por la regla aplicable más general para cualquier nodo, por ejemplo, aplica primero las reglas definidas para el body en todos los elementos hijos (en el caso que sea una propiedad Heredable), luego irá descendiendo hacia las más específicas, es decir, las reglas se ordenan en cascada de forma "descendente".

![Untitled2.png](Untitled2.png)

[Construcción del modelo de objetos | Web | Google Developers](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/constructing-the-object-model?hl=es)

[CSSOM](https://varvy.com/performance/cssom.html)

[Construcción, diseño y pintura del árbol de representación | Web](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-tree-construction?hl=es)

[User agent](https://developer.mozilla.org/en-US/docs/Glossary/user_agent)
