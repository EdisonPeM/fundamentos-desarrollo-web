---
title: Animaciones Automáticas
categories:
    - Avanzado
---

# @keyframes

La regla-at @keyframes permite crear la estructura de una animación a partir de la definición de los diferentes estados de ésta, de esta forma se puede tener un control más específico sobre los pasos intermedios de la secuencia de animación que se obtiene al dejar que el navegador maneje todo automáticamente.

<!-- more -->

Para crear keyframes se debe indicar el nombre del keyframe justo después de la regla y dentro del bloque de código se deben escribir los diferentes estados

```css
@keyframes *nombre-animacion* {
	/* Estados de la animación */
}
```

[@keyframes](https://developer.mozilla.org/es/docs/Web/CSS/@keyframes)

[CSS @keyframes Rule](https://www.w3schools.com/cssref/css3_pr_animation-keyframes.asp)

## Estado inicial - Estado final

Para definir solamente un estado inicial y un estado final de una animación se pueden utilizar las palabras clave **from** y **to**

```css
@keyframes nombre-animacion {
	from {
		/* Propiedades del estado inicial */
	}

	to {
		/* Propiedades del estado final */
	}
}
```

![Untitled.png](Untitled.png)

## Estados intermedios

Cuando se desea que una animación tenga más de dos estados se pueden especificar los diferentes momentos del tiempo según un porcentaje de la duración de la animación.

En este sentido 0% representa el estado de partida (**from**) y 100% el estado final (**to**).

```css
@keyframe animacion-variada {
	0% {
		/* Propiedades del estado inicial */
	}
	50%{
		/* Propiedades del estado intermedio a la mitad del tiempo */
	}
	70%{
		/* Propiedades del estado intermedio al 70% del tiempo */
	}
	100%{
		/* Propiedades del estado final */
	}
}
```

Cuando se trabajan estados intermedios, varios estados pueden compartir los mismos estilos, separando los porcentajes con una coma (`,`)

```css
@keyframe animacion-ciclo {
	0%, 
  100% {
		/* Propiedades del estado inicial y final */
	}
	
  25%, 
  75% {
		/* Propiedades de los estados intermedios al 25% y 75% del tiempo */
	}

	50%{
		/* Propiedades del estado intermedio a la mitad del tiempo */
	}
}
```

## Propiedades Animables

Al igual que las transiciones, no todas las propiedades son animables, sin embargo si se incluyen las propiedades que no se pueden animar en sus reglas de keyframe, se mostraran pero no se animarán.

Entre las diferentes propiedades animables, se recomienda trabajar **colores, transformaciones y opacidad**.

[Efectos y Animaciones](Efectos%20y%20Animaciones%20cb7adc506baa415dba392904c314c533.md)

[Animatable CSS properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties)

# Animación

[animation | CSS-Tricks](https://css-tricks.com/almanac/properties/a/animation/)

[Usando animaciones CSS](https://developer.mozilla.org/es/docs/Web/CSS/CSS_Animations/Usando_animaciones_CSS)

[CSS Animations](https://www.w3schools.com/css/css3_animations.asp)

[Animations - CSS Reference](https://cssreference.io/animations/)

## Nombre de la Animación

Una vez creado los keyframes se pueden asociar por medio de la propiedad **`animation-name`**

## Duración

Para determinar la duración de un ciclo de la animación se debe especificar la propiedad **`animation-duration`**, esta es obligatoria ya que su valor por defecto es **0s**.

Esta propiedad acepta medidas de tiempo en Segundos (`s`) y mili segundos (`ms`). 

## Delay

La propiedad `animation-delay` permite definir un tiempo de espera entre el momento en que el elemento se carga y el comienzo de la secuencia de la animación.

## Cantidad de ciclos

Dado que las animaciones con @keyframes son automáticas, es decir, no necesita la interacción del usuario, se puede definir cuántas veces se desea que se repita con la propiedad `**animation-iteration-count`.**

Esta propiedad recibe un número sin unidad de medida, también se puede indicar `infinite` para repetir la animación indefinidamente.

## Función de Tiempo

Con la propiedad `**animation-timing-function**` se puede cambiar la variación en la velocidad de la animación. Para ello se especifica una **curva cúbica bézier**, sus posibles valores son: ****

- `ease`: Inicio normal, luego rápido, luego finaliza normal (*default*)
- `linear`: velocidad constante de principio a fin.
- `ease-in`: inicio lento.
- `ease-out`: Final lento.
- `ease-in-out`: Inicio y fin lentos.
- `cubic-bezier(n,n,n,n)`: le permite definir sus propios valores en una función de cubic-bezier

[cubic-bezier.com](https://cubic-bezier.com/#0,0,1,1)

[Easing Functions Cheat Sheet](https://easings.net/#)

## Dirección

Dado que los @keyframes definen diferentes estados, se puede especificar la dirección de la animación (principio-fin / fin-principio) con la propiedad `**animation-direction**`

Sus posibles valores son:

- `**normal**`: La animación se reproduce hacia adelante.
- `reverse`: La animación se reproduce hacia atrás
- `alternate`: La animación se reproduce primero hacia adelante, luego hacia atrás
- `alternate-reverse`: La animación se reproduce primero hacia atrás, luego hacia adelante

## Fill Mode

Con la propiedad `**animation-fill-mode`** se puede especificar si al finalizar una animación el elemento mantendrá las propiedades del último estado, del primero, ninguno o ambos.

- `none`
- `forwards`
- `backwards`
- `both`

## ShortHand

Usando la propiedad `**animation**` se pueden resumir las demás propiedades. Este shorthand debe respetar el siguiente orden:

[animation-name](https://developer.mozilla.org/es/docs/Web/CSS/animation-name)
[animation-duration](https://developer.mozilla.org/es/docs/Web/CSS/animation-duration)
[animation-timing-function](https://developer.mozilla.org/es/docs/Web/CSS/animation-timing-function)
[animation-delay](https://developer.mozilla.org/es/docs/Web/CSS/animation-delay)
[animation-direction](https://developer.mozilla.org/es/docs/Web/CSS/animation-direction)
[animation-iteration-count](https://developer.mozilla.org/es/docs/Web/CSS/animation-iteration-count)
[animation-fill-mode](https://developer.mozilla.org/es/docs/Web/CSS/animation-fill-mode)
[animation-play-state](https://developer.mozilla.org/es/docs/Web/CSS/animation-play-state)

Las propiedades `animation-name` y  `animation-duration` son necesarias, las demás son opcionales.

Se pueden agregar varias animaciones separadas por coma con sus respectivas configuraciones.

[animation](https://developer.mozilla.org/es/docs/Web/CSS/animation)

# Librerías

[Animate.css](https://animate.style/)

[AOS](https://michalsnik.github.io/aos/)
