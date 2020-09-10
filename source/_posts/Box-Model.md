---
title: Box Model
categories:
    - Fundamentos
---

Todos los elementos de HTML son representados como "**cajas**" regulares en un navegador web, estas cajas permiten modelar y configurar la estructura de nuestra página ya que encapsulan el  defino dentreo de cada etiqueta.

![Modelo_de_caja.svg](Modelo_de_caja.svg)

[Introduction to the CSS basic box model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model#content-area)

[The CSS Box Model | CSS-Tricks](https://css-tricks.com/the-css-)

<!-- more -->

# **Unidades de Medida**

Css posee diferentes sistemas de medida que se utilizan para ajustar tamaños o grosores.

## **Unidades absolutas**

Las unidades absolutas que trabaja css son:

- Pulgadas (`in`)
- Centímetros (*`cm`*)
- Milímetros (*`mm`*)
- Puntos (*`pt`*)

Sin embargo estas unidades de medida ya no se utilizan dado que no se adecuan a medios cambiantes como lo son las pantallas.

## **Unidades Relativas**

La unidades relativas son mayormente usadas ya que se adaptan más fácilmente a los diferentes medios.

- Pixeles (`px`)
- Letra (`em`)
- Letra Raiz (`rem`)

## **Porcentajes**

Css establece una unidad de medida proporcional a lo que se desee según donde se use, puede ser relativo al tamaño de la letra, al tamaño del elemento mismo o al tamaño del contenedor.

- Porcentual (`%`)
- Proporcional al viewport (`vh` y `vw`)

# **Modelo de Cajas**

## **Tamaño**

Todos los elementos de HTML ocupa un espacio en la página web, por lo que poseen un tamaño en **alto** y **ancho** dentro del documento. Sin embargo, podemos manipular los tamaños de cada elemento con las propiedades:

- `width`: Ajusta el **ancho** de un elemento.
- `height`: Ajusta el **alto** de un elemento.

La mayoría de los elementos tienen predefinido su ancho al 100% de su contenedor y su alto de forma automático según su contenido.

Los posibles valores de estas propiedades son:

- *`auto`*: El navegador calcula su tamaño.
- *`Unidad de Medida`*: Alguna unidad relativa o proporcional.
- *`fit-content`*: Se ajusta al tamaño del contenido.

[CSS Height and Width](https://www.w3schools.com/css/css_dimension.asp)

[width](https://developer.mozilla.org/en-US/docs/Web/CSS/width)

[height](https://developer.mozilla.org/en-US/docs/Web/CSS/height)

## Límites de tamaño

Adicionalmente también se pueden establecer límites tanto superior como inferior del tamaño que pueda tomar un elemento html.

- `min-height`: Define el tamaño mínimo en alto.
- `min-width`: Define el tamaño mínimo en ancho.
- `max-height`: Define el tamaño máximo en alto.
- `max-width`: Define el tamaño máximo en ancho.

Con estas propiedades podemos crear elementos de un tamaño mínimo específico y que se puedan agrandar a medida que aumenta su contenido, hasta completar un tamaño máximo.

## **Content**

El contenido se refiere al ***ESPACIO*** donde se almacena todo lo que está *“dentro”* del elemento html, ya sea texto, contenedores u otros elementos como listas, tablas, etc.

- En el caso de elementos multimedia como `<img>`, `video` o `iframe`, su contenido será el recurso cargado.
- En el caso de `<hr>` y `<br>` no tienen contenido alguno.

Generalmente cuando definimos el tamaño de un elemento, estamos definiendo el tamaño del espacio del contenido.

## **Padding**

El padding o relleno es un espacio que agregamos para separar el contenido de nuestro elemento de su borde.

```css
.contenedor {
	padding: 1em;
}
```

[padding](https://developer.mozilla.org/es/docs/Web/CSS/padding)

[CSS Padding](https://www.w3schools.com/css/css_padding.asp)

## **Border**

La propiedad `border` nos permite agregar una línea que rodea nuestro elemento. Para agregar un borde se debe especificar el *tipo de borde*, sin embargo se pueden especificar más detalles como el *grosor del borde* o *color del borde*.

### **border-type**

Con la propiedad `border-style` podemos especificar el tipo de borde, los cuales pueden ser:

- *`solid`*: Línea contínua.
- *`dashed`*: Líneas discontínuas.
- *`doted`*: Puntos seguidos.

### **border-width**

Con la propiedad `border-width` podemos cambiar el grosor del borde indicándole la unidad de medida que deseemos, por defecto ocupa `3px`.

### **border-color**

Con la propiedad `border-color` podemos cambiar el color del borde, el cual inicialmente es el mismo color que el de la letra.

### **border**

Con la propiedad `border` se puede especificar las diferentes características de los bordes en una sola linea:

```css
p {
    /* Borde sólido de 3px y del color de la letra */
    border: solid;
}

div {
    /* Borde sólido de 1px y rojo */
    border: 1px solid red;
}
```

Para esta propiedad no importa el orden de los valores.

[border](https://developer.mozilla.org/es/docs/Web/CSS/border)

[CSS Borders](https://www.w3schools.com/css/css_border.asp)

### **Border-Radius**

Los bordes de cualquier elemento se pueden redondear usando la propiedad `border-radius`, en donde se indica el radio del redondeo en cualquier unidad de medida.

```css
div {
    border-radius: 10px
}
```

Se pueden generar circunferencias cuando se utilizan tamaños en porcentajes por encima del `50%`

## **Margin**

El Margen es el espacio que agregamos para separar elementos entre sí. El body del html trae por defecto un `margin` de 8px.

```css
body {
	margin: 0;
}
```

[margin](https://developer.mozilla.org/es/docs/Web/CSS/margin)

[CSS Margin](https://www.w3schools.com/css/css_margin.asp)

## Contorno

El contorno de un elemento se trata de una línea que rodea un elemento pero no pertenece al elemento. Se suele encontrar en inputs o botones.

[CSS Outline](https://www.w3schools.com/css/css_outline.asp)

# ShortHands

Algunas propiedades CSS permiten asignar el valor de muchas otras propiedades de CSS al mismo tiempo, reduciendo así la cantidad de código que escribimos.

- En el caso de los bordes, la propiedad `border` simplifica la declaración del ancho, color y estilo.
- Para el caso del `margin` y `padding`, se simplifica el valor de los 4 **lados**.
- Para el caso del `border-radius`, se simplifica el valor del radio de las 4 **esquinas**.

En muchos casos, varias propiedades que pertenecen a una sola categoría se pueden resumir en un shorthand, por ejemplo propiedades de fuente o de fondo.

[Propiedades abreviadas](https://developer.mozilla.org/es/docs/Web/CSS/Shorthand_properties)

## **Lados**

Tanto `border`, `padding` y `margin` manejan los cuatro lados de cada elemento

- Lado Superior: `top`
- Lado Derecho: `right`
- Lado Inferior: `bottom`
- Lado Izquierdo: `left`

Estos manejan en general un tamaño, pero se le puede indicar un tamaño a cada lado agregando el nombre del lado que se desea modificar después de la propiedad y unido con un guión (`-`) como se muestra a continuación:

```css
div {
    border-top: solid 3px black;
    margin-left: 8px;
    padding-bottom: 1.3em;
}
```

### 4 Tamaños

Si se desea modificar todos los lados al mismo tiempo se puede simplificar para el caso del `padding` y el `margin` indicando los 4 valores consecutivamente en sentido de las agujas del reloj comenzando con el lado superior:

```css
div {
    padding: 10px 20px 30px 40px;
}
```

Lo cual será lo mismo qué:

```css
div {
    padding-top: 10px;
    padding-right: 20px;
    padding-bottom: 30px;
    padding-left: 40px;
}
```

### 3 Tamaños

Cuando se escriben 3 tamaños en estas propiedades, se indican: lado superior, lados laterales, lado inferior:

```css
div {
    margin: 10px 20px 30px;
}
```

Lo cual será lo mismo que:

```css
div {
    margin-top: 10px;
    margin-right: 20px;
    margin-left: 20px;
    margin-bottom: 30px;
}
```

### 2 Tamaños

Cuando se indican 2 tamaños, se relacionan: lados superior e inferior y lados laterales:

```css
div {
    padding: 10px 20px;
}
```

Lo cual será lo mismo que:

```css
div {
    padding-top: 10px;
    padding-bottom: 10px;
    padding-right: 20px;
    padding-left: 20px;
}
```

## **Esquinas**

Así como con los lados, algunos estilos como el `border-radius`, manejan las cuatro esquinas de cada elemento

- Esquina Superior - Izquierda
- Esquina Superior - Derecha
- Esquina Inferior - Derecha
- Esquina Inferior - Izquierda

Estos también manejan en general un tamaño, y se le puede indicar un tamaño a cada lado en sentido de las agujas del reloj comenzando con el lado superior

### 4 Tamaños

```css
div {
    border-radius: 10px 20px 30px 40px;
}
```

- Esquina Superior - Izquierda: 10px
- Esquina Superior - Derecha: 20px
- Esquina Inferior - Derecho: 30px
- Esquina Inferior - Izquierda: 40px

### 3 Tamaños

```css
div {
    border-radius: 10px 20px 30px;
}
```

- Esquina Superior - Izquierda: 10px
- Esquina Superior - Derecha: 20px
- Esquina Inferior - Derecha: 30px
- Esquina Inferior - Izquierda: 20px

### 2 Tamaños

```css
div {
    border-radius: 10px 20px;
}
```

- Esquina Superior - Izquierda: 10px
- Esquina Superior - Derecha: 20px
- Esquina Inferior - Derecha: 10px
- Esquina Inferior - Izquierda: 20px

---

# Tipos de Cajas

En CSS existen dos tipos fundamentales de cajas: en bloque y en línea.

Las cajas en **bloque** (`block`) son aquellos que:

- Ocupan el 100% del ancho del contenedor donde se encuentre
- Generan saltos de línea obligatorios antes y después de cada elemento.

Algunos elementos en bloque son:

- Contenedores: `<div>`
- Todos los títulos: `<h1>` … `<h6>`
- Párrafos: `<p>`
- Listas: `<ul>`, `<ol>`
- Tablas `<table>`

[Elementos en bloque](https://developer.mozilla.org/es/docs/Web/HTML/Block-level_elements)

Las cajas **en línea** (`inline`) son elementos que:

- Siguen el flujo del texto
- Se ajusta solamente al tamaño del texto dentro
- Ignoran los tamaños adicionales, paddings y margins superiores e inferiores.

    Aunque sí los puede mostrar, no afectan a los demás elementos.

Algunos elementos en línea:

- Contenedor de Texto: `<span>`
- Manipuladores de texto:  `<strong>`, `<em>`, `<u>`, `<del>`, `<small>`, `<mark>`.
- Hipervínculos: `<a>`
- Multimedia
    - Imágenes: `<img>`
    - Audio: `<audio>`
    - Video: `<video>`
    - Embebidos: `<iframe>`

[Elementos en línea](https://developer.mozilla.org/es/docs/Web/HTML/Elementos_en_l%C3%ADnea)

## Display

Usando la propidad `display` de css, podemos cambiar el tipo de caja de cualquier elemento según se necesite.

[CSS display property](https://www.w3schools.com/cssref/pr_class_display.asp)

[display](https://developer.mozilla.org/es/docs/Web/CSS/display)

## Otros Modelos

Existen otros modelos de caja en bloque que permiten visualizar los elementos con estilos particulares:

- `list-item`: Para Ítems de Lista, son exactamente como bloques pero se agregan los literales correspondiente a la lista que pertenece (`<li>`)
- `table`: Para Tablas (`<table>`), también generan saltos de línea, pero no ocupan el 100% del ancho por defecto.
    - `table-row-group`: Para grupos (`<thead>`, `<tbody>`)
    - `table-row`: para filas (`<tr>`)
    - `table-cell`: Para títulos y celdas (`<th>`, `<td>`)

También existen modelos de cajas que permiten manipular su contenido de forma personalizada.

- Flex: Permite manipular el contenido de forma flexible.
- Grid: Permite acomodar el contenido en forma de red.

Estos modelos se comportan como cajas en bloque.

## Modelos en linea

Algunos elementos combinan los modelos de caja en bloque para acomodarlos en línea (`inline-block`) y así crear cajas con tamaño variable pero que sigue el flujo del texto, como es el caso de los elementos de formularios:

- `<input>`
- `<textarea>`
- `<select>`
- `<button>`

Los elementos de multimedia (*embebidos*) se consideran elementos en línea, sin embargo tienen un comportamiento de bloque en línea (*inline-block*)

Así mismo, usando la propiedad *display* se pueden crear tablas en linea, así conservan sus tamaños pero siguen el flujo del texto (`inline-table`).

También existen modelos de *flex en linea* y *grid en linea*

## Ocultar Elementos

La propiedad Display también se puede utilizar para ocultar elementos de una página web, usando el valor `none`

# Centrar Elementos*

Según el modelo de caja podemos alinear horizontalmente un elemento.

### Elementos de Bloque

Cuando se trata de elementos en bloque, podemos usar la margen (`margin`) lateral de éstos para centrarlo indicando el valor `auto`

```css
.bloque-centrado {
	margin-left: auto;
	margin-right: auto;
}

.bloque-derecha {
	margin-left: auto;
}

.bloque-izquierda {
	margin-right: auto;
}
```

### Elementos en Línea

Cuando tenemos elementos en línea, debemos usar `text-align` en el contenedor, ya que estos elementos siguen el flujo del texto.

```css
.texto-centrado {
	text-align: center;
}
```

[CSS text-align property](https://www.w3schools.com/cssref/pr_text_text-align.ASP)

[text-align](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)

### Alineamiento Vertical

Cuando un elemento tiene un modelo `inline-block` o similar, se pueden alinear verticalmente con el texto usando la propiedad `vertical-align`, en el elemento mismo.

```css
.centrado-vertical {
	vertical-align: middle;
}
```

[vertical-align](https://developer.mozilla.org/es/docs/Web/CSS/vertical-align)

[vertical-align](https://developer.mozilla.org/es/docs/Web/CSS/vertical-align)

# **Box-sizing**

Inicialmente las propiedades de tamaño solamente definen el tamaño del **content** (*espacio donde iría el contenido**), mientras que el tamaño **TOTAL** de un elemento varía según el tamaño del content, padding y border.

- **Ancho total:** width + (padding-left + padding-right) + (border-size-left + border-size-right)
- **Alto total:** height + (padding-top + padding-bottom) + (border-size-top + border-size-bottom).

Sin embargo, podemos indicarle al user-agent que calcule el tamaño total según las propiedades de tamaño (width y height), en este caso, el tamaño de los elementos es siempre el mismo sin importar cuánto haya de padding o borde.

```css
* {
    box-sizing: border-box;
}
```

El valor por defecto es *`content-box`*

[box-sizing](https://developer.mozilla.org/es/docs/Web/CSS/box-sizing)

[CSS Box Sizing](https://www.w3schools.com/css/css3_box-sizing.asp)

[Box model - CSS Reference](https://cssreference.io/)

## Demo Interactivo

[Box Model Demo](http://guyroutledge.github.io/)
