---
title: Layout
categories:
    - Intermedio
---

# Layout HTML

El Layout es la forma en la que está distribuido el contenido de una página web, este contenido puede estar distribuido en diferentes secciones de una página para un mejor entendimiento de la información que se presenta, visualmente se pueden agrupar o separar según se desee, sin embargo, desde HTML también se puede distribuir el contenido con etiquetas semánticas, que permiten al navegador identificar el tipo de contenido que tiene una página web.

<!-- more -->

## Seccionamiento

- `<main>`: Este elemento representa el **contenido principal** del cuerpo de un documento o aplicación. El área de contenido principal consiste en contenido que está directamente relacionado o se expande sobre el tema central de un documento o la funcionalidad central de una aplicación.

    El contenido del `<main>` de un documento es exclusivo de ese documento y excluye el contenido que se repite en un conjunto de documentos como enlaces de navegación del sitio, información de copyright, logotipos y pancartas o formularios de búsqueda (*a menos que el documento o la función principal de las aplicaciones es el de un formulario de búsqueda*).

    NO se deben incluir más de un elemento `<main>` en un documento.

    No se debe incluir el elemento `<main>` como descendiente de un artículo, aparte, pie de página, encabezado o elemento de navegación.

- `<article>`:  Este elemento representa una composición completa o autónoma en un documento, que en principio, es distribuible o reutilizable independientemente.

    Esto podría ser una **publicación** en un foro, una revista o un artículo de periódico, una **entrada** de blog, un **comentario** enviado por un usuario, un **widget o gadget** interactivo, o cualquier otro elemento de contenido independiente.

    Se pueden tener elementos artículo anidados, donde los elementos internos representan artículos que relacionados con el contenido del artículo externo.

    *Por ejemplo:* una **entrada de blog** en un sitio que acepta comentarios enviados por el usuario podría representar los **comentarios** como artículos anidados dentro del elemento de la entrada de blog (también articulo).

    Cuando el contenido principal de una página es completamente autónomo e independiente dentro de la etiqueta `<main>`, se puede omitir la etiqueta `<article>`.

- `<section>`: Este elemento representa una **sección genérica** de un documento o aplicación. En este contexto, sería una agrupación temática de contenido. El tema de cada sección debe identificarse, generalmente incluyendo un encabezado (elemento h2-h6) como elemento secundario del elemento de sección.

    Ejemplos de secciones serían **capítulos**, las diversas **páginas de un elemento de pestañas** (tabs) o las secciones numeradas de una tesis. La página de inicio de un sitio web se puede dividir en secciones para una introducción, noticias e información de contacto.

    El elemento de sección NO son elementos de tipo contenedor genérico. Cuando se necesita un elemento solo para fines de estilo o como una conveniencia para la creación de componentes, se debe **`<div>`**.

    Una regla general es que el elemento de sección es apropiado solo si el contenido del elemento se enumera explícitamente en el esquema del documento.

- `<aside>`: Este elemento representa una sección de una página cuyo contenido está relacionado tangencialmente con el contenido adyacente y que podría considerarse separado. Tales secciones a menudo se representan como barras laterales en la tipografía impresa

    Se puede utilizar para publicidad u otro contenido que se considere aparte de la temática de la página.

## Secciones Generales

Cualquier sección o subsección de la página web puede contar con alguno de los siguientes grupos.

- `<header>`: Este elemento representa un encabezado o contenido introductorio para la sección actual (*body, main, article, section, aside*). Generalmente contiene un título introductorio o un grupo de navegación.

    Por lo general, un elemento de encabezado debe contener el encabezado de la sección (un elemento h1 – h6), pero esto no es obligatorio

- `<h1> ... <h6>`: Los títulos representan cabeceras de una sección, estas cabeceras tienen un rango dado por el número en su nombre, donde h1 tiene el rango más alto y h6 tiene el rango más bajo, dos elementos con el mismo nombre tienen el mismo rango.

    Los elementos h1 – h6 no deben usarse para marcar subtítulos, títulos alternativos o lemas, a menos que estén destinados a ser el encabezado de una nueva sección o subsección.

- `<nav>`: El elemento de navegación representa **una sección con enlaces de navegación**.

    No todos los grupos de enlaces en una página deben estar en un elemento de navegación; el elemento está destinado principalmente a secciones que consisten en bloques de navegación principales.

En los casos en que el contenido de un elemento de navegación representa una lista de elementos, utilice el marcado de la lista para ayudar a la comprensión y la navegación.

- `<footer>`: Este elemento representa un pie de página para la sección actual (*body, main, article, section, aside*). Un pie de página generalmente contiene información sobre su sección, como quién lo escribió, enlaces a documentos relacionados, datos de copyright y similares.

## Divisiones Generales

- `<div>`: El elemento div no tiene ningún significado especial en absoluto. Se utiliza para agrupar contenido. Se puede usar con los atributos de clase, idioma y título para agregar estilos y semántica común de un grupo de elementos consecutivos.

## Ejemplo

![frame.jpg](frame.jpg)

```html
<body>
    <header class="main-header">
	<!-- Cabecera de la Página -->
	    <nav class="navbar">
	        <ul>
	            <li><a href="index.html">Home</a></li>
	            <li><a href="about.html">About</a></li>
	            <li><a href="contact.html">Contact</a></li>
	        </ul>
	    </nav>
	</header>
	<main class="main-content">
		<!-- 
			!Cuando el contenido principal de una página es completamente autónomo 
			se puede omitir el uso de la etiqueta <article>.
		-->
		<article class="post">
			<h2>noticia 1</h2>
			<seccion class="chapter">
				<h3>Primera Parte</h3>
			</seccion>
			<seccion class="chapter">
				<h3>Segunda Parte</h3>
				<div class="photos">
					<img src="..." alt="...">
					<img src="..." alt="...">
					<img src="..." alt="...">
				</div>
			</seccion>

			<footer class="author">
					Información del Autor
			</footer>
		</article>
		<article class="post">
				<h2>noticia 2</h2>
				<seccion class="chapter">
						<h3>Capítulo 1</h3>
				</seccion>
				<seccion class="chapter">
						<h3>Capítulo 2</h3>
				</seccion>
				<article class="comments">
						<h3>Comentarios</h3>
						<p> Lorem... </p>
				</article>
				<footer class="author">
						Información del Autor
				</footer>
		</article>
		<aside>
            <!-- Contenido relacionado (Recomendados) -->
        </aside>
    </main>
    <aside>
        <!-- Contenido COMPLETAMENTE Fuera de contexto (publicidad) -->
    </aside>
    <footer class="main-footer">
        Copyright © 2020
    </footer>
</body>
```

[HTML Layout Elements and Techniques](https://www.w3schools.com/html/html_layout.asp)

[HTML Semantic Elements](https://www.w3schools.com/html/html5_semantic_elements.asp)

[Secciones y esquema de un documento HTML5](https://developer.mozilla.org/es/docs/Sections_and_Outlines_of_an_HTML5_document)

[Learn About HTML5 Semantic Tags: Semantic Markup of HTML5 Elements](https://www.bitdegree.org/learn/html5-semantic-tags)

# Layout en CSS

Para aplicar los diseños de los layouts a la página es importante implementar CSS, para ello existen varias estrategias, entre ellas el diseño unidimensional (filas y columnas) y el diseño bidimensional (cuadrículas).

## Filas y Columnas

El diseño de filas y columnas unidimensional, se refiere al diseño de **filas independientes** donde cada fila tiene un sistema diferente de columnas, que permite acomodar los elementos lado a lado, este sistema se implementa mayormente cuando se desean agrupar y organizar componentes secuencialmente.

Existen diferentes estrategias para organizar columnas dentro de filas:

### Columnas Uniformes

Una forma sencilla de crear un sistema de filas y columnas, es creando columnas uniformes para cada fila, el módulo de diseño flexbox permite generar un sistema dinámico de columnas uniformes dentro de cada fila

**Flex-box:** Para generar columnas uniformes de forma dinámica con flexbox debemos tener distinción entre el contenedor (fila) y los ítems (columnas)

```css
* {
  box-sizing: border-box;  
}

.fila-flex {
	display: flex;
	flex-wrap: wrap;

	/* Espacio entre Filas */
	padding: 10px 10px;
}

.columna-flex {
	flex: 1;
	
	/* Espacio entre columnas */
	padding: 0 10px;
}
```

```html
<div class="fila-flex">
  <div class="columna-flex">
		<!-- Componentes -->
	</div>
  <div class="columna-flex">
		<!-- Componentes -->
	</div>
  <div class="columna-flex">
		<!-- Componentes -->
	</div>
  <div class="columna-flex">
		<!-- Componentes -->
	</div>
</div>
```

Con este sistema, la cantidad de columnas puede ser variable y su ancho siempre será uniforme,

### Columnas Proporcionales

El diseño de columnas proporcionales se utiliza cuando queremos que un componente sea más ancho que el anterior, en este caso se sugiere trabajar con una clase adicional para cada columna según el ancho que se desee.

```css
* {
  box-sizing: border-box;  
}

.fila-flex {
	display: flex;
	flex-wrap: wrap;

	/* Espacio entre Filas*/
	padding: 10px;
}

.columna-flex {
	flex: 1;
	
	/* Espacio entre columnas */
	padding: 0 10px;
}

.columna-50p {
	flex-basis: 50%;

	/* Espacio entre columnas */
	padding: 0 10px;
}

.columna-25p {
	flex-basis: 25%;

	/* Espacio entre columnas */
	padding: 0 10px;
}
```

```html
<div class="fila-flex">
  <div class="columna-50p">
		<!-- Componentes -->
	</div>
  <div class="columna-25p">
		<!-- Componentes -->
	</div>
  <div class="columna-25p">
		<!-- Componentes -->
	</div>
</div>
```

### 12 Columnas

Un sistema muy utilizado en el mundo del desarrollo web son los sistemas de columnas predefinidas, existen sistemas de 12, 16, 18 o 24 columnas. El más recomendado de trabajar es de 12 pues nos permite realizar particiones entre 1, 2, 3 y 4 columnas de forma equitativa, pero también nos permite trabajar de forma proporcional a la cantidad de columnas totales.

Estos sistemas los podemos crear igualmente con flexbox, creando clases correspondientes a cada cantidad de columnas a usar.

```css
* {
  box-sizing: border-box;  
}

.fila-flex {
	display: flex;
	flex-wrap: wrap;

	/* Espacio entre Filas */
	padding: 10px;
}

.columnas-12, .columnas-11, .columnas-10, .columnas-9, .columnas-8, .columnas-7, .columnas-6, .columnas-5, .columnas-4, .columnas-3, .columnas-2, .columnas-1 {
	/* Espacio entre columnas */
	padding: 0 10px;
}

.columnas-12 {
	flex-basis: 100%;
}

.columnas-11 {
	flex-basis: 91.66%;
}

.columnas-10 {
	flex-basis: 83.33%;
}

.columnas-9 {
	flex-basis: 75%;
}

.columnas-8 {
	flex-basis: 66.66%;
}

.columnas-7 {
	flex-basis: 58.33%;
}

.columnas-6 {
	flex-basis: 50%;
}

.columnas-5 {
	flex-basis: 41.66%;
}

.columnas-4 {
	flex-basis: 33.33%;
}

.columnas-3 {
	flex-basis: 25%;
}

.columnas-2 {
	flex-basis: 16.66%;
}

.columnas-1 {
	flex-basis: 8.33%;
}
```

```html
<div class="fila-flex">
  <div class="columnas-6">
		<!-- Componentes -->
	</div>
  <div class="columnas-3">
		<!-- Componentes -->
	</div>
  <div class="columnas-3">
		<!-- Componentes -->
	</div>
</div>
```

[A Complete Guide to Flexbox | CSS-Tricks](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

## Cuadrícula

El diseño de cuadrículas se refiere a un diseño bidimensional de filas y columnas, donde en este caso, todas las filas comparten la misma distribución de columnas, este diseño es útil para generar galerías usando css grid

[Basic concepts of grid layout](https://developer.mozilla.org/es/docs/Web/CSS/CSS_Grid_Layout/Conceptos_B%C3%A1sicos_del_Posicionamiento_con_Rejillas)

### Cuadrícula Básica

Diseño de una cuadrícula de 4 columnas:

```css
.grid {
	display: grid;
	grid-template-columns: repeat(4, 1fr);
	gap: 20px;
	padding: 20px;
}
```

Sin embargo, en este diseño se pueden destacar elementos extendiéndolo a lo largo de filas y columnas:

```css
.big-grid-item {
	grid-column: span 2;
	grid-row: span 2;

	/* short hand */
	/* 
		grid-area: span 2 / span 2;
	*/
}
```

```html
<div class="grid">
  <div class="big-grid-item">
    <!-- componentes -->
  </div>
	<div class="grid-item">
	  <!-- componentes -->
	</div>
	<div class="grid-item">
	  <!-- componentes -->
	</div>
  <div class="grid-item">
    <!-- componentes -->
  </div>
  <div class="grid-item">
    <!-- componentes -->
  </div>
</div>
```

### Macro Layout

Generalmente css-grid permite diseñar fácilmente la estructura del layout de una página web a nivel general, se podría indicar a cada elemento cuántas filas y columnas debería ocupar, sin embargo, esto se puede diseñar diseñando **grid áreas.**

Css Grid permmite definir una cuadrícula como plantilla y hacer referencia **áreas** dentro de dicha  cuadrícula donde se acomodarán los elementos según el área que se especifique con la propiedad **`grid-area`** de cada uno.

![dddgrid-template-areas.svg](dddgrid-template-areas.svg)

Para implementar las áreas se debe utilizar la propiedad **`grid-template-areas`** seguido de una secuencia de nombres de áreas por fila, Repetir el nombre de un área hace que el contenido (*que tenga relacionada dicha área*) abarque esas celdas. Un punto significa una celda vacía. Las áreas deben ser rectangulares!

```css
* {
  box-sizing: border-box;
}

/* Contenedor */
.grid-layout {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-template-areas: 
    "header header header header"
    "main   main   .      sidebar"
    "footer footer footer footer";
}

/* items de la cuadricula */
.grid-header {
  grid-area: header;
}
.grid-main {
  grid-area: main;
}
.grid-sidebar {
  grid-area: sidebar;
}
.grid-footer {
  grid-area: footer;
}
```

```html
<div class="grid-layout">
  <div class="grid-header">
		<!-- Componentes -->	
	</div>
  <div class="grid-main">
		<!-- Componentes -->
	</div>
  <div class="grid-aside">
		<!-- Componentes -->
	</div>
  <div class="grid-footer">
		<!-- Componentes -->
	</div>
</div>
```

### Sistema de 12 columnas

También se puede ajustar el tamaño de las secciones de la página según el diseño predefinido de 12 columnas teniendo en cuenta la plantilla de las columnas. Para este caso lo que se utiliza son las unidades de **fr** para completar una suma de 12.

```css
.grid-layout {
  display: grid;
  grid-template-columns: 2fr 7fr 3fr;
  grid-template-areas: 
    "header header header"
    "nav    main   sidebar"
    "footer footer footer";
}
```

Ni el nombre de la clase, ni el tipo de etiqueta determina el área al que pertenece cada elemento.

> El diseño de Flexbox es el más apropiado para los componentes de una aplicación y layouts de pequeña escala, mientras que CSS-Grid está diseñado para layouts de mayor escala.

[grid-template-areas](https://developer.mozilla.org/es/docs/Web/CSS/grid-template-areas)

[A Complete Guide to Grid | CSS-Tricks](https://css-tricks.com/snippets/css/complete-guide-grid/)
