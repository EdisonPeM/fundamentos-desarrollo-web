---
title: Efectos y Animaciones
categories:
    - Avanzado
---

# Efectos

Usando solamente CSS se pueden crear diferentes tipos de efectos sobre cualquier elemento HTML, para ello es necesario declarar unos estilos **base** sobre los que se agregará el efecto y luego los estilos que van a variar con la interacción del usuario.

La interacción del usuario se puede dar cuando pasa el mouse sobre un elemento (`:hover`), cuando hace click (`:active`), o cuando llena un campo de un formulario (`:focus`).

Para el caso de dispositivos táctiles, `:hover` y `:active` se cumplen cuando se hace **touch** sobre el elemento.

Con CSS cualquier propiedad puede variar, desde tipografía, colores, estilos de fondo, tamaños, bordes, sombras, filtros, desplazamientos y transformaciones.

<!-- more -->

# Transition

La propiedad `transition` brinda una forma de agregar una pequeña animación, permitiendo controlar la velocidad con la que cambia una propiedad de CSS y así crear un efecto progresivo personalizado en vez de uno inmediato.

Dado que la mayoría de efectos se da entre dos cambios de estado (*uno inicial y otro final*), los navegadores web se encargan de calcular los estados intermedios entre estos. 

![Untitled.png](Untitled.png)

[Using CSS transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)

[CSS Transitions](https://www.w3schools.com/css/css3_transitions.asp)

## Propiedades Animables

Usando la propiedad `transition-property` se especifica el nombre o nombres de las propiedades CSS a las que deberían aplicarse las transiciones.

No todas las propiedades son animables.

[Animatable CSS properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties)

## Duración

Con la propiedad `transition-duration` se determina la duración de la animación. Se Puede especificar una única duración que se aplique a todas las propiedades durante la transición o valores múltiples que permitan a cada propiedad de transición un periodo de tiempo diferente.

Esta propiedad acepta medidas de tiempo en Segundos (`s`) y mili segundos (`ms`).

## Delay

La propiedad `transition-delay` permite definir un tiempo de espera entre el momento en que cambia una propiedad y el inicio de la transición. Al igual que con todas las demás propiedades de transición, cada delay puede declararse como valores separados por comas.

Esta es una propiedad **opcional** por lo que no es necesaria para crear un efecto.

## Función de Tiempo

Con la propiedad `transition-timing-function` se puede cambiar la variación en la velocidad de la animación. Para ello se especifica una **curva cúbica bézier**, sus posibles valores son: ****

- `ease`: Especifica un inicio normal, luego rápido, luego finaliza normal (*default*)
- `linear`: Especifica la misma velocidad de principio a fin.
- `ease-in`: Especifica un efecto con un inicio lento.
- `ease-out`: Especifica un efecto con un final lento.
- `ease-in-out`: Especifica un efecto con inicio y fin lentos.
- `cubic-bezier(n,n,n,n)`: le permite definir sus propios valores en una función de cubic-bezier

[cubic-bezier.com](https://cubic-bezier.com/#0,0,1,1)

[Easing Functions Cheat Sheet](https://easings.net/#)

## ShortHand

Usando la propiedad `transition` se pueden resumir las demás propiedades. Este shorthand debe respetar el siguiente orden:

`transition: property duration timing-function delay;`

Donde sus valores por defecto son:

`transition: all 0s ease 0s`

Así mismo como las demás propiedades de transición, se pueden configurar diferentes animaciones separadas por coma.

Para este shorthand solamente la propiedad `transition-duration` es **requerida.**

[Transitions - CSS Reference](https://cssreference.io/transitions/)

# Efectos Comunes

## Colores

Cambiando las propiedades `color` y `background-color`, se pueden generar efectos de cambio de color alternando color de texto y color de fondo.

```css
.banner {
	/* Estado inicial */
  background-color: #ff8a65;

	transition-property: background-color, color;
	transition-duration: 1s;
}

.banner:hover {
	/* Estado Final */
  background-color: #d32f2f;
  color: white;
}
```

## **Tamaños**

Se puede variar el tamaño de un elemento cambiando las propiedades  `width` y `height`.

Si se está usando `box-sizing: border-box;`, El tamaño de un elemento también varía con el `padding` y `border`.

```css
* {
	box-sizing: border-box;
}

.box {
	/* Estados iniciales */
	width: 100px;
	height: 100px;
	padding: 1em;
	border: 2px solid;
	/*
		border-width: 2px;
		border-style: solid;
	*/
	transition-property: width, height, padding, border;
	transition-duration: 1s;
}

.box:hover {
	/* Estados Finales */
	width: 200px;
	height: 50px;
	padding: 1.5em;
	border-width: 10px;
}
```

## **Bordes**

Usualmente se agregan bordes transparentes y luego se les da color (`border-color`) para evitar cambiar el tamaño de los elementos, también se pueden redondear el borde con `border-radius`.

```css
.box {
	/* Estado inicial */
	border: solid transparent;
	/*
		border-style: solid;
		border-color: transparent;
	*/
	transition: border 1s, border-radius 1s;
}

.box:hover {
	/* Estado Final */
	border-color: red;
	border-radius: 50%;
}
```

## **Sombras**

Para generar el efecto de superposición se agrega una sombra sobre un elemento (`box-shadow` y `text-shadow`)

```css
.box {
  width: 100px;
  height: 100px;

	/*  Estado inicial  */
	/* -- Sin Sombra -- */
	transition: box-shadow 1s;
}

.box:hover {
	/* Estado Final */
  box-shadow: 0 0 5px;
}
```

## **Fondo**

Se puede alternar las imagenes de fondo de un elemento cambiando el valor de la propiedad `background-image`.

```css
.fondo {
	/* Estado inicial */
	background-image: url('../imagenes/fondo1.jpeg');

	transition: background-image 1s;
}

.fondo:hover {
	/* Estado Final */
	background-image: url('../imagenes/fondo2.jpeg');
}
```

## Transparencia

La propiedad opacity también es animable, por lo que se puede generar una animación sobre la transparencia.

```css
.banner {
	/* Estado inicial */
	opacity: 0;

	transition: opacity 1s;
}

.banner:hover {
	/* Estado Final */
	opacity: 0.8;
}
```

## **Filtros**

Sobre imágenes se pueden agregar filtros como escala de grises (`filter: grayscale(50%)`), desenfoques (`filter: blur(5px);`) o transparencias (`filter: opacity(80%)`).

```css
.efecto-img {
	/* Estado inicial */
	filter: grayscale(100%) blur(2px) saturate(100%);
	transition: filter 1s;
}

.efecto-img:hover {
	/* Estado Final */
  filter: grayscale(0%) blur(0px) saturate(180%);
}
```

## **Desplazamientos**

Usando posicionamiento relativo y absoluto se puede desplazar un elemento usando las propiedades `top` y `left`. En este caso la interacción del usuario será con el elemento contenedor.

```css
.container {
  height: 200px;
  width: 500px;
  border: solid;

  position: relative;
}

.box {
  background-color: #3df;
  width: 100px;
  height: 100px;

  position: absolute;
	/* Estado inicial */
  top: 0;
  left: 0;

	transition: top 1s, left 1s;
}

.container:hover .box {
	/* Estado Final */
  top: calc(100% - 100px);
  left: calc(100% - 100px);
}
```

# Transformaciones

Las transformaciones CSS permiten trasladar, rotar, escalar o sesgar los elementos de html de acuerdo a los valores establecidos en la propiedad `transform` a través de las diferentes funciones.

[transform - CSS Reference](https://cssreference.io/property/transform/)

[transform](https://developer.mozilla.org/es/docs/Web/CSS/transform)

[transform | CSS-Tricks](https://css-tricks.com/almanac/properties/t/transform/)

## Traslación

La función `translate()` permite desplazar un elemento desde su **posición actual** en dirección horizontal siendo positivo hacia la derecha y negativo hacia la izquierda, y dirección vertical siendo positivo hacia abajo y negativo hacia arriba.

También se puede establecer un desplazamiento en cada eje por separado con las propiedades

- `translateX()` para el eje horizontal.
- `translateY()` para el eje vertical.

```css
.container {
  height: 200px;
  width: 500px;
  border: solid;
}

.box {
  background-color: #3df;
  width: 100px;
  height: 100px;

	/* Estado inicial */
  transform: translate(0, 0);
	transition: transform 1s;
}

.container:hover .box {
	/* Estado Final */
  transform: translate(100%, 100%);
}
```

## Escalamiento

La función `scale()` permite aumentar o disminuir el tamaño de un elemento, de acuerdo con los parámetros dados para el ancho y la altura establecidos como una relación.

- Un valor de 1 conserva su tamaño
- Un valor menor a 1 disminuye su tamaño (La mitad sería 0.5)
- Un valor mayor a 1 aumenta su tamaño (El doble sería 2)

```css
.box {
  width: 100px;
  height: 100px;
	
	/* Estado inicial */
	transform: scale(1);
	transition: transform 1s;
}

.box:hover {
	/* Estado Final */
	transform: scale(2);
}
```

Al agrandar un elemento, este mantiene su posición original pero se superpone sobre los demás, por lo que se suele utilizar dentro de contenedores con un control de desbordamiento (`overflow`).

```css
.card {
	overflow: hidden;
  width: 300px;
  height: 200px;
}

.card-img {
	/* Estado inicial */
	transform: scale(1);
	transition: transform 1s;
}

.card:hover .card-img {
	/* Estado Final */
	transform: scale(1.5);
}
```

Al igual que las anteriores transformaciones, se puede establecer un escalamiento en cada eje por separado con las propiedades

- `scaleX()` para el eje horizontal.
- `scaleY()` para el eje vertical.

## Rotación

La función `rotate()` gira un elemento en sentido horario o antihorario según un grado (**deg**) dado (positivo horario y negativo antihorario).

```css
.box {
  width: 100px;
  height: 100px;
	
	/* Estado inicial */
	transform: rotate(0deg);
	transition: transform 1s;
}

.box:hover {
	/* Estado Final */
	transform: rotate(30deg);
}
```

También se puede crear una rotación 3D según el eje de rotación con las propiedades.

- `rotateX()` para el eje horizontal.
- `rotateY()` para el eje vertical.

```css
.box {
  width: 100px;
  height: 100px;
	
	/* Estado inicial */
	transform: rotateY(0deg);
	transition: transform 1s;
}

.box:hover {
	/* Estado Final */
	transform: rotateY(360deg);
}
```

## Torcer

Las funciones `skewX()` y `skewY()` permiten "***torcer***" un elemento a lo largo de los ejes X e Y respectivamente, según los ángulos dados (`deg`).

- Los ángulos inclinarán el eje opuesto del elemento según el ángulo dado.
- Los ángulos límite son **-90deg** y **90deg.**

```css
.box-x {
	transform: skewX(15deg);
	transition: transform 1s;
}

.box-y {
	transform: skewY(45deg);
}
```

![Untitled1.png](Untitled1.png)

Ambas propiedades se pueden resumir en la función  `skew()`.

```css
.box {
	transform: skew(15deg, 45deg);
}
```

## Todas Juntas

La propiedad transform permite la implementación de varias transformaciones, para ello se deben escribir las correspondientes funciones separadas por espacio.

# Transition + Transform

Para crear una animación con transform, es necesario contar con el estado inicial de todas las transformaciones que se deseen animar.

```css
.container {
	height: 200px;
  width: 500px;
  border: solid;
}

.b1 {
  /* Estado inicial */
  transform: translate(0, 0) rotate(0deg) scale(1);
  transition: transform 1s;
}

.container:hover .b1 {
  /* Estado Final */
  transform: translate(100%, 50px) rotate(45deg) scale(1.2);
}
```
