---
title: Estilos Avanzados
categories:
    - Intermedio
---

Algunas propiedades de css que se pueden utilizar para agregar estilos más avanzados son

<!-- more -->

## Contenedores / Elementos

### Desbordamiento

Cuando un elemento tiene un tamaño fijo, y su contenido es más grande que dicho tamaño, se genera un desbordamiento y el contenido se muestra por fuera del contenedor.

Si no es posible ajustar el tamaño del contenido para que se ajuste al contenedor, se puede usar la propiedad `overflow` y cambiar este comportamiento.

- `hidden` con este valor, el contenido que se desborda no se muestra.
- `scroll` con este valor, se agregan barras de desplazamiento en el contenedor, y el contenido desbordado se oculta.
- `auto` con este valor se agregan barras de desplazamiento según sean necesarias.

[overflow - CSS Reference](https://cssreference.io/property/overflow/)

[CSS Overflow](https://www.w3schools.com/css/css_overflow.asp)

### **Sombra**

Se pueden agregar sombras a cualquier elemento utilizando la propiedad `box-shadow` con los siguientes valores:

- Posición de la sombra
- Desplazamiento a la Derecha
- Desplazamiento hacia abajo
- Radio de Difuminación
- Radio de Propagación
- Opacidad
- Color

[box-shadow - CSS Reference](https://cssreference.io/property/box-shadow/)

Para agregar sombras pueden usar generadores de sombras online.

[Box Shadow CSS Generator](https://html-css-js.com/css/generator/box-shadow/)

### Opacity

La propiedad opacity nos permite convertir un elemento y **TODO** su contenido en un elemento con transparencia, de esta forma opaca un poco el elemento.
Su valor es un número ente 0 y 1, donde 0 lo convierte completamente transparente y 1 es completamente visible.

[opacity - CSS Reference](https://cssreference.io/property/opacity/)

[opacity](https://developer.mozilla.org/es/docs/Web/CSS/opacity)

**visibility**

La propiedad visibility permite convertir un elemento y su contenido completamente transparente con el valor `hidden`. Es similar a usar `opacity: 0;`

## Fuentes y Texto

[Typography - CSS Reference](https://cssreference.io/typography/)

### **Spacing**

Se puede cambiar el espacio del texto en diferentes formas:

- `letter-spacing`: Espacio entre letras.
- `word-spacing`: Espacio entre palabras.
- `text-indent`: Identación de textos.
- `line-height`: Espacio entre lineas.

### Fuentes Adicionales

Se pueden añadir fuentes a una página web importando los archivos de fuentes (ttf, otf, woff) usando la regla `@font-face`.

[@font-face | Codrops](https://tympanus.net/codrops/css_reference/font-face/)

O importando la fuente desde internet con la regla `@import(*url*)`

[Google Fonts](https://fonts.google.com/)

### Columnas de Texto

Usando las propiedades `column-*` se pueden generar columnas de texto.

[CSS Multiple Columns](https://www.w3schools.com/css/css3_multiple_columns.asp)

[Online CSS Multi Column Generator](https://html-css-js.com/css/generator/column/)

### Desbordamiento de Texto

En algunos casos el texto es muy grande para un contenedor, por lo que pues desbordarse, en ese tipo de situaciones se pueden adoptar diferentes estrategias:

- `overflow-wrap: break-word`; Permite romper las palabras largas para evitar desbordamiento de texto.

[overflow-wrap](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap)

[CSS word-wrap property](https://www.w3schools.com/cssref/css3_pr_word-wrap.asp)

[CSS word-break property](https://www.w3schools.com/cssref/css3_pr_word-break.asp)

- `text-overflow: ellipsis;` Permite agregar puntos suspensivos y ocultar el texto que se está desbordando. En este caso se debe forzar a no admitir más lineas de texto de la siguiente forma:

```css
.ver-mas {
  width: 300px;
  display: inline-block;
  overflow: hidden;
	white-space: nowrap;
	text-overflow: ellipsis;
}
```

[text-overflow](https://developer.mozilla.org/es/docs/Web/CSS/text-overflow)

`white-space`:

[](https://developer.mozilla.org/es/docs/Web/CSS/white-space)

### Sombra en el Texto

Se pueden agregar sombras al texto utilizando la propiedad `text-shadow`, esta propiedad utiliza diferentes valores:

- Desplazamiento a la Derecha
- Desplazamiento hacia abajo
- Difuminación
- Opacidad
- Color

Existen varias páginas en internet que nos permiten generar sombras fácilmente.

[Online Text Shadow CSS Generator](https://html-css-js.com/css/generator/text-shadow/)

## Listas

Los estilos de una lista se pueden definir  con las propiedades **`list-style-*`**

- **list-style-type**
- **list-style-image**
- **list-style-position.**

[CSS Lists](https://www.w3schools.com/css/css_list.asp)

[list-style - CSS Reference](https://cssreference.io/property/list-style/)

### Counters

Los counters con contadores que se pueden agregan a cualquier elemento con el pseudo-elemento ::before, con estos counter podemos agregar numeración a diferentes elementos, como secciones, titulos o para agregar una sub-numeración en listas anidadas.

```css
ol.nested-list,
ol.nested-list ol {
  counter-reset: nivel;
  list-style: none;
}

ol.nested-list li::before {
  counter-increment: nivel;
  content: counters(nivel,".") " ";
}
```

[Custom List Number Styling | CSS-Tricks](https://css-tricks.com/custom-list-number-styling/)

[counter-increment | CSS-Tricks](https://css-tricks.com/almanac/properties/c/counter-increment/)

[CSS Counters](https://www.w3schools.com/css/css_counters.asp)

### Striped Style

Se pueden usar las pseudoclases :nth-child(odd) y :nth-child(even) para agregar un estilo de interlineado en las listas.

```css
.striped-list li:nth-child(odd){
	background-color: #cffff2;
}

.striped-list li:nth-child(even){
	background-color: #ffa3a3;
}
```

## Tablas

### Layout

Inicialmente las tablas ajustan su tamaño y el tamaño de sus columnas a su contenido, con la propiedad `table-layout: fixed;` todas las columnas ocupan el mismo ancho, para tal fin deben tener un ancho (`width`) específico.

### Filas y Columnas Extendidas

Se pueden extender las celdas de una tabla a lo largo de varias filas y/o varias columnas son atrbutos de html.

Para extender una celda a lo largo de *`n`* filas usamos el atributo `rowspan`, indicando la cantidad de filas a extender.

- Dado que la celda se extiende, las siguientes filas deberán tener una celda menos.

Podemos extender una celda a lo largo de *`n`* columnas con el atributo `colspan`, indicando la cantidad de columnas a extender.

- Dado que la celda se extiende, en la misma fila se deberán reducir las celdas.

```html
<table class="borde-celdas">
  <thead>
    <tr>
      <th></th>
      <th>Title 1</th>
      <th>Title 2</th>
      <th>Title 3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>title row</th>
      <td rowspan="2">Lorem, ipsum dolor.</td>
      <td>Deserunt, ut doloribus?</td>
      <td>Ullam, tempore dignissimos?</td>
    </tr>
    <tr>
      <th>title row</th>
      <td>Magni, ratione error!</td>
      <td>Veniam, amet et.</td>
    </tr>
    <tr>
      <th>title row</th>
      <td>Maiores, quod nostrum.</td>
      <td colspan="2">Libero, fuga commodi?</td>
    </tr>
  </tbody>
</table>
```

[Tutorial HTML: Tablas con Colspan y Rowspan](http://www.usabilidad.tv/tutoriales_html/colspan_y_rowspan.asp)

[HTML colspan Attribute](https://www.w3schools.com/tags/att_td_colspan.asp)

[HTML rowspan Attribute](https://www.w3schools.com/tags/att_td_rowspan.asp)

### **Bordes**

Desde html:5 las tablas no tienen el atributo de borde, por lo que para agregar bordes a una tabla se debe hacer por medio de estilos. Para ésto existen diferentes propiedades que nos permiten modificar los estilos de las tablas

- `Border-collapse`  separación entre los bordes de las celdas, por defecto estas están separadas, modificando esta propiedad podemos **unir** los bordes de cada celda.
- `Border-spacing` Cuando nuestro borde está separado, podemos personalizar la distancia con la que se separan las celdas con la propiedad `border-spacing`, indicando el tamaño de esta distancia:

```css
.borde-contorno {
	border: 1px solid;
}

.borde-filas,
.borde-filas tr {
	border-collapse: collapse;
	border: 1px solid;
}

.borde-celdas,
.borde-celdas th,
.borde-celdas td {
	border-collapse: collapse;
	border: 1px solid;
}
```

[A Complete Guide to the Table Element | CSS-Tricks](https://css-tricks.com/complete-guide-table-element/)

[HTML Tables](https://www.w3schools.com/html/html_tables.asp)

### Striped Tables

Se pueden usar las pseudoclases :nth-child(odd) y :nth-child(even) para agregar un estilo de interlineado en las tablas.

```css
.striped-table tr:nth-child(even) {
	background-color: #f2f2f2;
}
```

### Generador de Tablas

[HTML Table Styler 📅 CSS Generator](https://divtable.com/table-styler/)

## Hipervinculos

Para cambiar los estilos de los links, se pueden cambiar las propiedades `text-decoration` y `color`, en cada uno de sus estados.

```css
.normal-link {
	text-decoration: none;
	color: inherit;
}

.normal-link:link {
	text-decoration: none;
	color: inherit;
}

.normal-link:visited {
	text-decoration: none;
	color: inherit;
}
```

[cursor](https://developer.mozilla.org/es/docs/Web/CSS/cursor)

### Hipervinculos con contenido

Los hipervinculos son utilizados en muchas partes de una página web, ya sea para hacer referencia a enlaces externos o recursos internos, se pueden configurar los hipervinculos para que cualquier elemento sea comporte como un hipervinculo, solamente se deben agregar dichos  elementos dentro de la etiqueta a. Adicionalmente se puede configurar los estilos de los links para cambiar su apariencia.

```html
<a href="#" title="">
	<div>
		<!-- Algún elemento -->
	</div>
</a>
```

```css
a {
  text-decoration: none;
  color: #000;
  display: inline-block;
}
```

### Hipervinculos Externos

Cuando se agrega un hipervinculo que hace referencia a un recurso de la web, se suele configurar para que abra en una nueva pestaña, en este caso se deben agregar los atributos de html:

```html
<a href="https://google.com" target="_blank" rel="noopener noreferrer nofollow">
    go to google
</a>
```

### Go-to-top

Go to top es un recurso para agregar un botón que devuelve una página a la parte superior.

```html
<a href="#" class="go-top">
	Go to Top
</a>
```

```css
html {
	/* Permite que el desplazamiento de una página sea suave */
	scroll-behavior: smooth;
}

.go-top {
	/* Styling as a go top button */
}
```

### Cursor

Css permite cambiar el tipo de cursor (*figura del mouse*) que se muestra cuando el mouse está sobre un elemento usando la propiedad `cursor`

- *`pointer`*: Muestra el mouse con el simbolo de elemento clickeable (usualmente una mano)
- *`help`*: Muestra el simbolo de ayuda
- *`progress`*: Muestra el mouse con el simbolo de cargando.
- *`wait`*: Muestra el simbolo de espera.
- *`none`*: No muestra mouse.

[cursor - CSS Reference](https://cssreference.io/property/cursor/)

La propiedad cursor se puede agregar a cualquier elemento.

## Imagenes

[CSS Styling Images](https://www.w3schools.com/css/css3_images.asp)

[6 simple CSS tricks for images - GoDaddy Blog](https://www.godaddy.com/garage/6-simple-css-tricks-for-images/)

### Tamaños

Las imagenes tienen por defecto el tamaño en pixeles de la imagen que se está cargando a la página, este tamaño lo podemos cambiar usando las propiedades `width` y `height`. 

Sin embargo, si no se mantiene la proporción de la magen, ésta se estira o se encoje según los nuevos valores, para evitar esta perdida de proporcion se sugiere:

- Definir un tamaño de alto (*height*) automático, en las páginas web generalmente se limita más el ancho de los elementos que el alto, pues el ancho de la pantalla es generalmente fijo mientras que el alto se puede alargar y realizar scroll vertical.

*Se considera mala practica generar scroll horizontal. a excepción de que se utilice para cambiar de recurso, como un carrusel de imagenes.*

- Si el tamaño debe ser fijo según el diseño, se puede ajustar la proporcion de la imagen con la propiedad `object-fit`:
    - `cover` con este valor la imagen se recortará lo necesario con la finalidad de ocupar el tamaño establecido y manteniendo la relación del aspecto de la imagen misma.
    - `contain` con este valor la imagen mantiene su relación de aspecto **dentro** del tamaño establecido, en este caso se agrega un espacio vacio donde sea necesario con el color de fondo del elemento.

En cualquier caso, se puede reacomodar la imagen dentro del tamaño especificado usando la propiedad `object-position`

[CSS object-fit Property](https://www.w3schools.com/css/css3_object-fit.asp)

[object-fit | CSS-Tricks](https://css-tricks.com/almanac/properties/o/object-fit/)

[CSS Styling Images](https://www.w3schools.com/css/css3_images.asp)

**Desbordamiento**

En caso de que una imagen se desborde por su tamaño, se puede agregar un limite de ancho que permita a la imagen escalar según el tamaño de la pantalla.

```css
img {
	max-width: 100%;
}
```

### Thumnails

Se pueden diseñar miniaturas de imagenes agregando paddings y un borde suave 

```css
img {
	background-color: white;
  border: 1px solid #ddd;
  border-radius: 4px;
  padding: 5px;
  width: 150px;
}
```

### Imagenes y links

Se suelen usar imagenes como hipervinculos, ya sea usando iconos de redes sociales, logotipos de empresas, fotos de productos, etc, para ello basta con agregar la imagen como contenido del hipervinculo.

Por otra parte, se puede configurar un hipervinculo con referencia a una imagen para visualizarla en el navegador.

```html
<a href="./images/myImage.jpg" title="my Image">
	<img src="./image/myImage.jpg" alt="my Image">
</a>
```

### Filtros

Usando css se pueden agregar filtros a imagenes para lograr diversos efectos visuales, estos se agregan usando la propiedad `filter:` y cada filtro corresponde a una función en particular donde su valor varía según el caso.

- `blur(5px)`: Se utiliza para desenfocar una imagen, usualmente admite tamaños diferentes a porcentaje.
- `grayscale(50%)`: Se utiliza para convertir una imagen a escala de grises, admite porcentajes, donde 100% es completamente en escala de grises.
- `opacity(80%):` Aplica transparencia a las muestras, admite porcentajes donde 0% es completamente transparente. Este filtro es similar a aplicar la propiedad **opacity**, sin embargo algunos navegadores proporcionan aceleración de hardware para un mejor rendimiento.

Esta propiedad admite diferentes filtros separados por espacio.

[filter | CSS-Tricks](https://css-tricks.com/almanac/properties/f/filter/)

[filter](https://developer.mozilla.org/es/docs/Web/CSS/filter)

### Texto sorbre imagenes

Se pueden utilizar las imagenes (*etiquetas img*) como fondo y escribir texto sobre la imagen, combinando las propiedades de position relative-absolute y flexbox.

```html
<div class="banner">
	<img class="imagen-banner" alt="fondo banner">
	<div class="texto-banner">
		<!-- Contenido -->
	</div>
</div>
```

```css
.banner {
	width: 100%;
	/* height: 400px; */
  position: relative;
	display: flex;
	justify-content: center;
	align-items: center;
}

.imagen-banner { 
  width: 100%;
  height: 100%;
	object-fit: cover;
  filter: opacity(70%) blur(2px);
}

.texto-banner {
	background-color: rgba(0, 0, 0, 0.8);
  color: white;
	padding: 1em 2em;
  border-radius: 5px;
  position: absolute;
	left: 40px;
}
```

## Fondos

### Parallax Efect

Usando css puro se puede generar un efecto parallax, usando las siguientes propiedades de background en el contenedor donde se desea aplicar este efecto.

```css
.parallax {
	/* The image used */
  background-image: url(filepath);

  /* Create the parallax scrolling effect */
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}
```

Estos estilos se le pueden aplicar a cualquier elemento html, usualmente a un contenedor que ocupe todo el ancho de la pantalla (viewport)

[](https://www.w3schools.com/howto/tryhow_css_parallax_demo.htm)

### Colores Translucidos

Todos los elementos de HTML tienen fondos transparentes, ésto les permite mostrar el fondo que tenga sus contenedores.

Si se desea agregar colores translucidos usando el sistema rgba. Lo cual es una combinación del código **rgb** de colores y un ***a**lpha* de transparencia, el cuál es un porcentaje donde 100% o 1 es completamente visible y 0% o 0 es completamente transparente.

```html
.fondo-translucido {
	background-color: rgba(125, 240, 60, 0.4);
}
```

### Gradiantes

Con las propiedades de background-image, es posible generar un fondo con distintos colores en forma de gradiante.

[linear-gradient](https://developer.mozilla.org/es/docs/Web/CSS/linear-gradient)

[Online Gradient CSS Generator](https://html-css-js.com/css/generator/gradient/)

### Filtro de Fondo

Usualmente se puede usar los grandiantes junto con las imagnes para agregar una capa de colores sobre la imagen del fondo, para este caso en el gradiante se utilizan colores translucidos para no tapar por completo la imagen.

```css
.fondo-filtro {
	background-image: linear-gradiant(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), 
											url("filepath");
}
```

## img vs background-image

Para agregar una imagen de fondo se puede usar la propiedad `background-image` o usar la etiqueta `<img>` dentro de un contenedor y combinar las propiedades de position. Para determinar cuál opción usar, se puede tener en cuenta los siguientes criterios:

### <img>

- La imagen se podrá ver cuando un  usuario desee impirmir la página.
- Cuando la imagen tiene un importante significado semántico, tal como un icono de advertencia. (Usar `alt`)
- Cuando desea que la imagen sea accesible para los usuarios.
- Tiene más capacidad de filtros usando la propiedad `filter`, así mismo mejora el rendimiento al momento de crear animaciones sobre el fondo.
- Permite la implementacion de carga lenta (*laizy load*) para mejorar el rendimiento de la página cuando hay muchas imagenes.

### background-image

- La imagen no se mostrará si el usuario impirme la página.
- Cuando la imagen es meramente decorativa y no tiene significado dentro de la página.
- Se desea agregar un efecto parallax dentro de la página.
- Permite crear efectos de fondo cambiante fácilmente usando animaciones, sin embargo no tienen un buen rendimiento al usar filtros.
- Si es necesario mejorar los tiempos de descarga. **(1)**

***(1)** Los archivos* *las imagenes pueden pasar por un proceso de optimización (reducción y compresión) para mejorar el rendimiento de carga.*

[¿Cuándo se debería usar img y cuando background-image?](https://es.stackoverflow.com/questions/24511/cu%C3%A1ndo-se-deber%C3%ADa-usar-img-y-cuando-background-image)

# Calculos en CSS

Css permite realizar calculos matemáticos entre diferentes unidades de medida para poder establecer un tamaño, estos calculos pueden ser resueltos usando la función `calc()`, cada tamaño que se vaya a operar debe ir acompañado de su unidad de medida.

```css
.contenedor {
	width: calc(100% - 40px);
}
```

[A Complete Guide to calc() in CSS | CSS-Tricks](https://css-tricks.com/a-complete-guide-to-calc-in-css/)

[calc](https://developer.mozilla.org/es/docs/Web/CSS/calc)

# Variables

Css permite el uso de variables dentro de las hojas de estilos, estas variables pueden almacenar cualquier tipo de valor, sin embargo de debe tener cuidado de implementarlas en los lugares adecuados.

El uso de variables de css permite crear un sistema de diseño dentro de css, con lo cual, si se toman desciciones de diseño como el sistema de colores o de tamaños, se podrán modificar los valores de estas variables, y automaticamente toda la página adoptará estos nuevos valores.

## Creación de variables

Las variables de css pueden utilizarse a nivel global de todo el documento, o a nivel local de algunos selectores con alcance a los descendientes de estos.

Para crear una variable de css se deben definir dentro de la pseudoclase `:root` y se deben nombrar comenzando por `—nombre-variable`

```css
:root {
	--bg-color: #e3e3e3;
	--color-primary: #389fff;
	--color-secondary: #8fb588;
	--font-size: 22px;
	--title-font: Arial, Helvetica, sans-serif;
}
```

## Implementacion de variables

Para usar las variables en alguna propiedad, se debe utilizar la función `var(--nombre-variable)`

```css
body {
	background-color: var(--bg-color);
	font-size: var(--font-size);
}

h1, h2, h3 {
	font-family: var(--title-font);
}
```

[Uso de propiedades personalizadas CSS (variables)](https://developer.mozilla.org/es/docs/Web/CSS/Using_CSS_custom_properties)

[CSS Variables](https://www.w3schools.com/css/css3_variables.asp)
