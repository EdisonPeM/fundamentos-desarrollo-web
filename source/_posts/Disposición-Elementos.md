---
title: Disposición de Elementos
categories:
    - Intermedio
---

# **Float**

La propiedad `float` permite sacar a un elemento del flujo normal del documento y empujarlo hacia el lado izquierdo o derecho de su contenedor, cuando un elemento "flota" los elementos de texto y *en línea* aparecerán a su alrededor.

![Untitled.png](Untitled.png)

<!-- more -->

Para que un elemento flote, debemos indicarle en a qué lado debería flotar: izquierda o derecha:

```css
.flotar-izquierda {
    float: left;
}

.flotar-derecha {
    float: right;
}
```

Un elemento que flota es automáticamente display: block; aunque no tenga comportamiento de bloque, esto es porque aunque flote, permite variar su tamaño.

[float - CSS Reference](https://cssreference.io/property/float/)

[float](https://developer.mozilla.org/es/docs/Web/CSS/float)

[float | CSS-Tricks](https://css-tricks.com/almanac/properties/f/float/)

Anteriormente se solía usar los elementos flotantes para diseñar una página web, sin embargo, esta es una mala práctica ya que en la actualidad existen mejores formas de diseño como flexbox o css-grid.

## Limpiar **Desplazamiento**

En muchos casos no deseamos que el texto de otro elemento (*ej: otro párrafo*) o elementos inline, rodeen a nuestro elemento flotante sino que aparezcan debajo, en estos casos se puede aplicar la propiedad `clear` indicando cuál es el lado que se desea evitar.

- `left`: si el elemento se encuentra a la izquierda
- `right`: si el elemento se encuentra a la derecha
- `both`: si el elemento se encuentra a la izquierda y derecha

![Untitled1.png](Untitled1.png)

[clear - CSS Reference](https://cssreference.io/property/clear/)

## Evitar Desbordamiento

Generalmente un elemento flotante no ocupa un espacio dentro de un contenedor, por lo que el contenedor se ajustará al tamaño de los demás elementos, si el elemento flotante es más grande que éstos ocurrirá un desbordamiento.

![Untitled2.png](Untitled2.png)

Elemento flotante desbordandose del primer elemento de bloque.

Existen muchas estrategias para evitar este desbordamiento, todas las estrategias proponen unos estilos particulares al contenedor del flotante (se usará la clase *.clearfix* para hacer referencia a este contenedor)

[The Clearfix: Force an Element To Self-Clear its Children | CSS-Tricks](https://css-tricks.com/snippets/css/clear-fix/)

[How To Clear Floats (Clearfix)](https://www.w3schools.com/howto/howto_css_clearfix.asp)

### Float

La primera estrategia para ajustar el tamaño del contenedor es que el contenedor también flote, de esta forma se ajustará al tamaño del contenido flotante.

```css
.clearfix {
	float: left;
}
```

### Overflow

La propiedad overflow de css nos permite controlar el comportamiento de una caja cuando su contenido es mayor al tamaño del contenedor, entre sus opciones nos permite esconder el contenido desbordado o agregar una barra de desplazamiento.

Sin embargo, cuando se trata de elementos flotantes y el contenedor NO tiene un tamaño fijo, se puede utilizar para ajustar su tamaño al elemento flotante.

```css
.clearfix {
	overflow: hidden;
}
```

Se suele usar el valor hidden para evitar que aparezcan barras de desplazamiento indeseadas.

### Pseudo-elementos

Se puede limpiar el desplazamiento del pseudo-elemento *after* para que el contenedor se alargue hasta completar el tamaño del flotante.

```css
.clearfix:after {
  content: "";
  display: block;
  clear: both;
}
```

[The Clearfix: Force an Element To Self-Clear its Children | CSS-Tricks](https://css-tricks.com/snippets/css/clear-fix/)

[How To Clear Floats (Clearfix)](https://www.w3schools.com/howto/howto_css_clearfix.asp)

### Display

Actualmente, se pueden ajustar los tamaños de los contenedores con algunos valores de la propiedad display, como lo es `inline-block`, sin embargo, este valor cambia una caja de elemento en bloque a elemento en línea, por lo que se está trabajando en un nuevo valor denominado `flow-root` que permite crear un elemento en bloque con su propio contexto interno. 

[Descubre flow-root, el valor moderno de display para limpiar floats en CSS - campusMVP.es](https://www.campusmvp.es/recursos/post/display-flow-root-para-limpiar-floats-css.aspx)

[Can I use... Support tables for HTML5, CSS3, etc](https://caniuse.com/#search=flow-root)

---

# Position

La propiedad position de CSS permite cambiar el comportamiento de posicionamiento de un elemento en la página entre los siguientes:

- `static`: El elemento es posicionado de acuerdo al flujo normal del documento.
- `relative`: El elemento es posicionado de acuerdo al flujo normal del documento, pero permite **desplazarlo** respecto a su ubicación natural.
- `fixed`: El elemento es removido del flujo normal del documento, permite **ubicarlo** respecto a la pantalla (*viewport*) según los valores de desplazamiento.
- `absolute`: El elemento es removido del flujo normal del documento, permite **ubicarlo** respecto al contenedor posicionado más próximo, según los valores de desplazamiento.
- `sticky`: El elemento es posicionado de acuerdo al flujo normal del documento mientras se encuentre dentro de la pantalla (*viewport*), luego de eso el elemento se posicionará como fijo (fixed) según los valores de **desplazamiento**.

Se considera que un elemento está "**posicionado**" cuando el valor de la propiedad position es diferente a *`static`*

[position](https://developer.mozilla.org/es/docs/Web/CSS/position)

[Propiedad position (Referencia de CSS 2.1)](https://uniwebsidad.com/libros/referencia-css2/position)

## Ubicación / Desplazamiento

Cuando deseamos desplazar un elemento, o ubicarlo respecto a otro según el método de posicionamiento tenemos algunas propiedades para ello, estas propiedades admiten una unidad de medida.

- `top`: Permite ubicar o desplazar elementos desde la parte superior hacia abajo.
- `right`: Permite ubicar o desplazar elementos desde el costado derecho hacia la izquierda.
- `bottom`:  Permite ubicar o desplazar elementos desde la parte inferior hacia arriba.
- `left`: Permite ubicar o desplazar elementos desde el costado izquierdo hacia la derecha.

[Positioning - CSS Reference](https://cssreference.io/positioning/#position)

[position | CSS-Tricks](https://css-tricks.com/almanac/properties/p/position/)

## z-index

A diferencia de los elementos flotantes, los elementos posicionados se sobreponen sobre otros elementos del documento, para controlar el orden de cuales elementos se muestran "delante" o "detrás" se puede usar la propiedad z-index.

Usualmente todos los elementos tienen un z-index en 0 y los elementos posicionados se organizan uno sobre otro según el orden en el documento HTML.

Para enviar un elemento detrás de los elementos estáticos, se pueden usar valores negativos.

Solamente funciona sobre elementos posicionados.

# Flexbox

El módulo flexbox permite diseñar, alinear y distribuir elementos de una forma eficiente,  incluso cuando su tamaño es desconocido y/o dinámico.

[A Complete Guide to Flexbox | CSS-Tricks](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

## Contenedor

Para usar flexbox, es necesario que el contenedor de los elementos a organizar tenga la propiedad `display: flex;`, o `display: inline-flex`, según si se desea que el contenedor sea tratado como elemento en bloque o elemento en línea.

Algunas propiedades complementarias del flexbox son:

- `flex-direction`: Determina la dirección en que serán organizados los elementos hijos (**flex-items**)
- `flex-wrap`: Define si los elementos hijos (**flex-items**) se fuerzan en una sola línea o pueden fluir en varias líneas.

## Contenido

Todos los elementos que se encuentren directamente dentro de un **flex container**, se comportarán como **flex items**, estos elementos se alinearán según la dirección que defina el **flex container** y su tamaño cambiará según el caso.

- Si **NO** tienen un tamaño predefinido, los flex-items se ajustarán automáticamente al tamaño de su contenido.
- Si tienen un tamaño predefinido se respetará mientras haya espacio disponible.
- Si no existe espacio disponible para que un elemento conserve su tamaño, éste se reducirá automáticamente por defecto.
    - Esta regla se puede cambiar modificando el valor de la propiedad `flex-shrink`.
- Si su tamaño no se puede reducir más, se generará un desbordamiento en el contenedor.
    - Si el **flex container** permite fluir a los ítems en varias líneas (*wrap*), saltará a la siguiente línea.
- Su tamaño puede crecer hasta ocupar todo el espacio disponible según el valor que se defina en la propiedad `flex-grow`.

Éstas reglas aplican para el ancho, si la dirección del flexbox es en fila. Si la dirección es columna, aplicará sobre el alto. Sin embargo, generalmente el alto no es limitado en una página web.

## Alineamiento

Usando Flexbox se pueden alinear elementos tanto horizontal como verticalmente, el encargado de establecer el método de alineación es el **flex-container** usando las propiedades:

- `justify-content`: Permite distribuir los elementos horizontalmente.
- `align-items`: Permite distribuir los elementos verticalmente.

![Untitled3.png](Untitled3.png)

Alineamiento Horizontal

![Untitled4.png](Untitled4.png)

Alineamiento Vertical

### Auto Alineamiento

Cada flex-item puede anular el alineamiento **vertical** que defina el flex container y definir su propia alineación con la propiedad `align-self`.

# Grid

CSS Grid es un sistema de distribución de elementos en red usando un diseño de cuadrícula (*filas y columnas*).

[A Complete Guide to Grid | CSS-Tricks](https://css-tricks.com/snippets/css/complete-guide-grid/)

## Contenedor

Para usar CSS Grid, es necesario que el contenedor de los elementos a organizar tenga la propiedad `display: grid;`, o `display: inline-grid`, según si se desea que el contenedor sea tratado como elemento en bloque o elemento en línea.

Inicialmente la cuadricula consiste en una sola columna, se puede determinar la cantidad y el tamaño de cada columna con la propiedad `grid-template-columns`.

- Se indica una lista de tamaños separados por espacios, la cantidad de tamaños determina la cantidad de columnas, y los tamaños en sí determinan el ancho de cada columna.
- Se puede utilizar la función `repeat(*cantidad*, *tamaño*)` para generar rápidamente varias columnas de igual tamaño.
- Los tamaños pueden ser unidades relativas, porcentajes o **fracciones (1fr)**, las fracciones son unidades de medida específicas para las grid, pues representan "**espacio disponible**". Con ésta unidad de medida podemos ajustar el diseño de la cuadrícula de forma flexible y sin desbordamientos.

Por defecto las cuadrículas no tienen un límite de filas, sin embargo se puede establecer una cantidad y tamaño mínimo para las filas con la propiedad `grid-template-row`.

Tanto las filas como las columnas no tienen un espacio de separación, éste se puede ajustar con las propiedades `column-gap` y `row-gap` (o se puede usar el shorthand `gap`).

```css
.grid-container {
	display: grid;
	grid-template-columns: repeat(3, 1fr);
	gap: 10px;
	padding: 10px;
}
```

La propiedad gap genera espacio solamente **ENTRE** filas y columnas, no entre el contenedor y los elementos.

## Contenido

Todos los elementos que se encuentren directamente dentro de un **grid container**, se comportarán como **grid ítems**, estos elementos se acomodarán según el diseño de la cuadrícula, ubicándose ordenadamente (LTR o RTL según el lenguaje) y siempre en la fila debajo de la anterior.

Así como en las tablas, los grid-items pueden abarcar más de una columna, o más de una fila usando las propiedades `grid-column` y `grid-row`

```css
.item-ancho {
	grid-column: span 2;
	grid-row: span 2;
}
```

## Alineamiento

Similar a Flex, grid tiene un sistema de alineamiento horizontal y vertical.

### Alineamiento horizontal

Cuando los grid-items son más pequeños que el tamaño de las columnas, se puede utilizar la propiedad `justify-items`, por defecto el valor es `*stretch*`, con lo que los elementos se estiran hasta ocupar todo el ancho.

![Untitled5.png](Untitled5.png)

justify-items: stretch

![Untitled6.png](Untitled6.png)

justify-items: start

![Untitled7.png](Untitled7.png)

justify-items: center;

![Untitled8.png](Untitled8.png)

justify-items: end;

También se puede aplicar `justify-content` de forma similar a flexbox, en ese caso los elementos distribuidos serán las columnas completas.

![Untitled9.png](Untitled9.png)

justify-content: space-evenly;

![Untitled10.png](Untitled10.png)

justify-content: space-between;

### Alineamiento vertical

Cuando los grid-items son más pequeños que el tamaño de las filas, se puede utilizar la propiedad `align-items`, por defecto el valor es `*stretch*`, con lo que los elementos se estiran hasta ocupar todo el alto.

![Untitled11.png](Untitled11.png)

align-items: stretch;

![Untitled12.png](Untitled12.png)

align-items: end;

![Untitled13.png](Untitled13.png)

align-items: center;

![Untitled14.png](Untitled14.png)

align-items: start;

### Auto Alineamiento

Similar a flexbox, cada ítem en particular puede anular el alineamiento vertical y horizontal ****que defina el grid container y definir su propia alineación con las propiedad `align-self` y `justify-self` respectivamente.
