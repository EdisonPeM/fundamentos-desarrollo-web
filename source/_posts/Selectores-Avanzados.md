---
title: Selectores Avanzados
categories:
    - Intermedio
---

# Básicos

un selector es la forma en la que **seleccionamos** los elementos de nuestro html que deseamos modificar, estos selectores pueden hacer referencia a grupos de elementos o a elementos específicos y se puede escribir de diferentes maneras.

[CSS Selectors](https://www.w3schools.com/css/css_selectors.asp)

[Selectores CSS](https://developer.mozilla.org/es/docs/Web/CSS/Selectores_CSS)

<!-- more -->

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

Para este selector se debe iniciar siempre con numera (#) seguido del identificador del elemento y el conjunto de reglas de estilo.

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

# Pseudo Clases

Las pseudoclases permiten la selección de elementos, basada en información de estado que no está contenida en el árbol de documentos.

Las pseudoclases se asocian a los elementos usando dos puntos (`:`) justo después del selector.

[Pseudo-classes](https://developer.mozilla.org/es/docs/Web/CSS/Pseudo-classes)

[CSS Pseudo-classes](https://www.w3schools.com/css/css_pseudo_classes.asp)

## Interacción con Mouse

Permite agregar estilos a elementos basados en la interacción del usuario con el elemento.

- `:hover` Permite agregar estilos cuando el usuario pasa el mouse por encima de un elemento
- `:active` Permite agregar estilos mientras el usuario hace click sobre un elemento

[:hover](https://developer.mozilla.org/es/docs/Web/CSS/:hover)

[:active](https://developer.mozilla.org/es/docs/Web/CSS/:active)

## Estado de Links

Algunas pseudoclases permiten cambiar los estilos de los links según:

- `:link` cuando un hipervinculo **NO** ha sido visitado.
- `:visited` cuando un hipervinculo YA ha sido visitado.

[:link](https://developer.mozilla.org/es/docs/Web/CSS/:link)

[:visited](https://developer.mozilla.org/es/docs/Web/CSS/:visited)

## Estado de Inputs

Las pseudoclases permiten agregar estilos a inputs, selects y textarea según las entradas del usuario.

- `:focus` sí el usuario está escribiendo sobre el elemento.
- `:required` / `:optional` según si un campo es obligatorio u opcional.
- `:disabled` / `:enable` según si un campo está deshabilitado o no
- `:valid` / `:invalid` según si el campo es valido según las validaciones de html o no.

[Pseudo-clases útiles para formularios)](https://programaenlinea.net/pseudo-clases-utiles-formularios/)

## Relación de Hijos

También se pueden usar pseudoclases para recorrer elementos como listas o filas de tablas.

- `:first-child` / `:last-child` Permite seleccionar el primer elemento (o ultimo) dentro de un contenedor.
- `:nth-child(n)` / `:nth-last-child(n)` Permite seleccionar el elemento numero ***n*** dentro de un contenedor.
    - Se puede escribir simplemente **`n`** para seleccionar TODOS los elementos del contenedor.
    - Se pueden escribir las palabras clave `even` y  `odd` haciendo referencia a los elementos **pares** e **impares** respectivamente.
    - Se puede describir un patron usando la letra n 
    Por ejemplo: 4n, 3n+1, 7n+5

![Untitled.png](Untitled.png)

[:first-child](https://developer.mozilla.org/es/docs/Web/CSS/:first-child)

[:nth-child](https://developer.mozilla.org/es/docs/Web/CSS/:nth-child)

[CSS :nth-child() Selector](https://www.w3schools.com/cssref/sel_nth-child.asp)

[Tryit Editor v3.6](https://www.w3schools.com/cssref/tryit.asp?filename=trycss3_nth-child_odd_even)

## :not(*selector*)

La pseudoclase not nos permite seleccionar un elemento que NO coinciden con el selector dentro del parentesis.

# Pseudo Elementos

Los pseudo-elemento, son formas en las que css añade estilos a una parte concreta de los elementos.

Los pseudo-elementos se asocian a un elemento usando doble dos puntos (`::`) justo después de un selector.

[CSS Pseudo-elements](https://www.w3schools.com/css/css_pseudo_elements.asp)

[Pseudoelementos](https://developer.mozilla.org/es/docs/Web/CSS/Pseudoelementos)

## Texto

Con los pseudo-elementos se puede modificar texto concreto dentro de un elemento:

- `::first-letter` permite cambiar el estilo de la primera letra de un texto.
- `::first-line` permite cambiar el estilo de la primera linea de texto.
- `::selection` Permite cambiar el estilo de algún texto seleccionado por el usuario.

## Decoraciones

Los pseudo-elementos `::before` y `::after` permiten agregar decoraciones a un elemento antes o después respectivamente.

Para describir el contenido de la decoración se usa la propiedad `content`

```css
q::before { 
  content: "«";
  color: blue;
}

q::after { 
  content: "»";
  color: red;
}
```

[::before (:before)](https://developer.mozilla.org/en-US/docs/Web/CSS/::before)

[::after (:after)](https://developer.mozilla.org/en-US/docs/Web/CSS/::after)

# Selector de atributo

El selector de atributos CSS coincide con elementos basados ​​en la presencia o el valor de un atributo dado.

Los atributos se asocian a los elementos usando llaves cuadradas `[atributte]`.

[Attribute selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors)

[CSS Attribute Selector](https://www.w3schools.com/css/css_attribute_selectors.asp)

# Composición de Selectores

## Union de Selectores

Un selector puede hacer referencia a un elemento, pero se puede agregar más selectores para que una regla sea más específica, los diferentes tipos de selectores se pueden unir respetando el siguiente orden:

```css
tagName#id.clase-1.clase-2[attribute]:pseudo-clase::pseudo-elemento {
	/* Estilos */
}
```

Ejemplo:

```css
div.efecto-mouse:hover {
	opacity: 70%
}
```

Aunque la regla de css aumenta su especifidad, NO se recomienda anidar muchos selectores en la misma regla.

## Agrupación de Selectores

Se pueden agrupar diferentes selectores en una misma regla de css para compartir estilos sin tener que repetir código. Para ésto, los diferentes selectores deben ir separados por coma (`,`)

```css
h1, 
h2,
.texto-rojo {
	color: red;
}
```

## Combinaciones

La combinación se selectores se utiliza para establecer reglas de estilos basadas en la relación jerarquica entre elementos.

[CSS Combinators](https://www.w3schools.com/css/css_combinators.asp)

### Contenedor / Contenido

El combinador `>` selecciona los elementos que son hijos directos del primer elemento.

```css
ul > li {
	backgroud-color: cyan;
}
```

[Selectores de hijo](https://developer.mozilla.org/es/docs/Web/CSS/Child_combinator)

El combinador  `` (espacio) selecciona cualquier elemento que sea descendientes del primer elemento.

```css
.menu a {
  display: block;
  padding: .5em;
}
```

[Los selectores descendientes](https://developer.mozilla.org/es/docs/Web/CSS/Descendant_combinator)

### Adyacencia

El combinador `+` selecciona hermanos adyacentes. Esto quiere decir que el segundo elemento sigue directamente al primero y ambos comparten el mismo elemento padre.

```css
img + span.caption {
  font-style: italic;
	font-size: 0.8em;
}
```

[Selectores de hermanos adyacentes](https://developer.mozilla.org/es/docs/Web/CSS/Selectores_hermanos_adyacentes)

El combinador `~` selecciona cualquier hermano subsecuente. Esto quiere decir que el segundo elemento sigue al primero (no necesariamente de forma inmediata) y ambos comparten el mismo elemento padre.

```css
h2 ~ p {
	font-size: 1.2em;
}
```

[Selectores de hermanos generales](https://developer.mozilla.org/es/docs/Web/CSS/Selectores_hermanos_generales)
