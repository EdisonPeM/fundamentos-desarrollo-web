---
title: Metodologías CSS
categories:
    - Herramientas
---

# Priorización de Estilos

Existen diferentes formas de agregar estilos a un documento de HTML y así mismo existen diferentes formas de definir la apariencia y configuración de un elemento HTML. En este sentido, es importante entender cuales estilos tendrán más relevancia que otros:

1. Estilos por defecto, es decir los estilos específicos de cada navegador definidos por su **usuario agente**.
2. Atributos de HTML, como **`width=""`** o **`height=""`.**
3. Código CSS, ya sea interno o externo, dependiendo el orden de escritura, priorizando el **último**.
4. Aplicar estilos a un elemento HTML directamente con el atributo **`style=""`**.

Aplicar estilos con el atributo style se considera mala práctica, pues no permite la reutilización de estilos a otros elementos

La palabra clave **`!important`** se puede agregar a una declaración de css en cualquier regla para priorizar un estilo sobre las demás declaraciones. Esta se considera mala práctica ya que puede llegar a causar una completa reestructuración de código en el futuro. También es sinónimo de que el sistema de clases no está bien definida.

<!-- more -->

## Especificidad

CSS es un lenguaje basado en reglas con las que se definen los estilos de uno o varios elementos según el selector que se esté usando y dado que existen diferentes selectores y combinación de selectores, se pueden aplicar distintas reglas al mismo elemento de html, por ejemplo:

```html
<div class="container">
	<p id="p1"> lorem </p>
	<img class="img-p" src="..." alt="...">
</div>
```

Para agregar estilos a la imagen, se pueden usar diferentes tipos de selectores de CSS, entre nombres de etiqueta, clases, id, pseudo-clases, y selectores de atributos:

```css
.img-p { /*...*/ }
p + img { /*...*/ }
#p1 ~ .img-p { /*...*/ }
.container > img { /*...*/ }
.container .img-p { /*...*/ }
div img:first-child { /*...*/ }
div > p + img[src="..."]:last-child  { /*...*/ }
```

Cuando más de una regla afecta al mismo elemento, **CSS combina** los estilos que son diferentes entre sí, por lo que si las reglas son de diferente naturaleza no habrá conflicto a la hora de renderizar dichos estilos.

Por el contrario, cuando diferentes reglas modifican las mismas propiedades, se tendrán en cuenta primero las reglas con mayor **especificidad.**

Para el calculo de la especificidad se debe contar la cantidad de selectores que tiene una regla y asignarla a una posición según:

1. Elementos (*etiqueta html*) y pseudo-elementos.
2. Clases, pseudo-clases y atributos.
3. IDs.

Los combinadores (`+`, `>`, `~`, `' '`) y la pseudo-clase de negación (`:not()`) no tienen efecto sobre la especificidad. Sin embargo, los selectores declarados dentro de :not() si lo tienen.

El selector universal (`*`) y los estilos heredados tienen una especificidad de 0.

```css
/* (0, 0, 1) */
img { /*...*/ }

/* (0, 1, 0) */
.img-p { /*...*/ }

/* (0, 0, 2) */
p + img { /*...*/ }

/* (1, 1, 0) */
#p1 ~ .img-p { /*...*/ }

/* (0, 1, 1) */
.container > img { /*...*/ }

/* (0, 2, 0) */
.container .img-p { /*...*/ }

/* (0, 1, 2) */
div img:first-child { /*...*/ }

/* (0, 2, 3) */
div > p + img[src="..."]:last-child  { /*...*/ }
```

Si diferentes reglas tienen la misma especificidad, se tendrá en cuenta el **orden de escritura (*cascada*),** priorizando el ultimo escrito**.**

[Specificity Calculator](https://specificity.keegan.st/)

[Especificidad](https://developer.mozilla.org/es/docs/Web/CSS/Especificidad)

[Cascada y especificidad](http://w3.unpocodetodo.info/css3/cascada.php)

[20 consejos para escribir CSS moderno - Parte 2](https://programacion.net/articulo/20_consejos_para_escribir_css_moderno_parte_2_1580)

# Metodologías

[Metodologías o Arquitecturas CSS (OOCSS, BEM, SMACSS, ITCSS, Atomic Design)](https://medium.com/williambastidasblog/metodolog%C3%ADas-o-arquitecturas-css-oocss-bem-smacss-itcss-atomic-design-a1a3cfbfa6c9)

[Methods to Organize CSS | CSS-Tricks](https://css-tricks.com/methods-organize-css/)

## CSS Atómico

Con Atomic CSS, se crea una clase separada para cada propiedad reutilizable. Este estilo permite minimizar la cantidad de código CSS reutilizando declaraciones.

Atomic CSS se usa en varios marcos para especificar estilos de elementos correctivos y en algunas capas de otras metodologías.

```css
/* Shorthand Atomic CSS Examples */
.bgc-blue { background-color: #357edd; } 
.f1 { font-size: 3rem; }
.m0 { margin: 0; }

/* Longhand Atomic CSS Examples */
.background-blue  { background-color: #357edd; }
.backgroundcolor-blue  { background-color: #357edd; }

.text-h1 { font-size: 3rem; }
.text-3rem { font-size: 3rem; }

.marg-0 { margin: 0; }
.margin-0 { margin: 0; }
```

[Let's Define Exactly What Atomic CSS is | CSS-Tricks](https://css-tricks.com/lets-define-exactly-atomic-css/)

## Bloques, Elementos y Modificadores (BEM)

BEM es una metodología que sugiere una manera estructurada de **nombrar** clases, basado en las propiedades del elemento en cuestión.

- **Bloque**: Entidad independiente que es significativa por sí sola. (header, container, menu, checkbox, input, button...)

    ```css
    .card {
    	display: flex;
    	border-radius: 3px;
    	padding: 7px 12px;
    	border: 1px solid #D5D5D5;
    	background-image: linear-gradient(#EEE, #DDD);
    	font: 700 13px/18px Helvetica, arial;
    }
    ```

- **Elemento**: Una parte de un bloque que no tiene un significado independiente y está semánticamente vinculado a su bloque. (menu item, list item, checkbox caption, header title...)

    ```css
    .card__img {} 
    .card__header {}
    .card__content {}
    ```

- **Modificador**: Una bandera en un bloque o elemento. Se utilizan para cambiar la apariencia o el comportamiento. (disabled, highlighted, checked, fixed, size big, color yellow, state danger...)

    ```css
    .card__link--disabled {
    	color: #ddd;
    }

    .button--danger {
    	color: #900;
    }
    ```

[BEM - Block Element Modifier](http://getbem.com/introduction/)

[BEM 101 | CSS-Tricks](https://css-tricks.com/bem-101/)

## CSS orientado a objetos (OOCSS)

La metodología de CSS orientado a objetos recomienda prestar más atención a características comunes en común entre los diferentes elementos y separarlas en módulos u objetos, que se pueden reutilizar en cualquier lugar. Esta metodología se basa en dos principios:

### Separación de estructura y diseño.

Casi todos los elementos en una página web tienen características visuales que se repiten en diferentes contextos como los colores, sombras, bordes, etc. también llamados **estilos**.

**Estilos Comunes**

Al crear un objeto (*elemento html con una* *clase*) se define su **estructura,** pero esta estructura debe estar separada de sus **estilos,** y en cambio se deben crear de forma independiente los estilos comunes a diferentes elementos.

```css
/* Objetos (Estructura) */
.button {
  width: 200px;
  height: 50px;
}

.widget {
  width: 500px;
  min-height: 200px;
  overflow: auto;
}

/* Estilos */
.skin {
  border: solid 1px #ccc;
  background: linear-gradient(#ccc, #222);
  box-shadow: rgba(0, 0, 0, .5) 2px 2px 5px;
}
```

**Modificadores de Estilo**

Así mismo si se desea crear un nuevo tipo de objeto con estilos diferentes, se pueden crear clases que modifiquen sus estilos y así tener diferentes objetos de forma dinámica.

```css
.big-button {
  font-size: 24px;
  font-weight: bold;
  padding: 0.8em 1.5em;
  border-radius: 8px;
}
```

```html
<a href="#" class="button big-button skin">Cuidado!</a>
```

### Separación de contenedor y contenido

OOCSS recomienda que los estilos de un elemento no dependan de ningún elemento contenedor. Esto significa que puedan reutilizar en cualquier parte del documento, independientemente del contexto estructural.

```css
.sidebar h3 {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 2em;
  line-height: 1;
  color: #777;
  text-shadow: rgba(0, 0, 0, .3) 3px 3px 6px;
}

.footer h3 {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1.5em;
  line-height: 1;
  color: #777;
  text-shadow: rgba(0, 0, 0, .3) 2px 2px 4px;
}
```

```css
.header-inside {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1;
  color: #777;
  text-shadow: rgba(0, 0, 0, .3) 3px 3px 6px;
}

.big-text {
	font-size: 2em;
}

.mid-text {
	font-size: 1.5em;
}
```

[An Introduction To Object Oriented CSS (OOCSS) - Smashing Magazine](https://www.smashingmagazine.com/2011/12/an-introduction-to-object-oriented-css-oocss/)

[stubbornella/oocss](https://github.com/stubbornella/oocss/wiki)

## Arquitectura escalable y modular para CSS (SMACSS).

La Metodología SMACSS indica cómo se pueden categorizar las reglas de estilo de CSS, con ello podemos evitar la repetición de código para facilitar el mantenimiento y aumentar la consistencia.

Al separar las reglas en las cinco categorías, es más fácil identificar la función de un estilo en particular dentro del alcance general de la página. En proyectos grandes, es más probable que los estilos se dividan en varios archivos. En estos casos, la convención de nomenclatura también facilita encontrar a que archivo pertenece un estilo.

- **Reglas básicas:** se establecen los estilos por defectos de los elementos HTML individuales, los típicos selectores CSS de tipo. Por ejemplo:

    ```css
    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
    	margin: 0; 
    	font-family: 'Roboto', sans-serif;
    	font-size: 18px;
    }
    ```

- **Reglas del layout:** se divide la página en secciones (`header`, `main content`, `footer`, `navigation`, etc.) y se asignan los estilos relacionados con su estructura.
- **Reglas de módulos:** elementos que pueden ser reusables, modulares e independientes del contexto. Por ejemplo: llamadas a la acción (*botones*) o galerías de imágenes.
- **Reglas de estados:** se define el comportamiento del layout y sus módulos en diferentes estados: diferentes resoluciones.
- **Reglas de temas:** Estilos que modifican al layout y módulos. Estas reglas son opcionales, y las puedes utilizar para estilos que puede que quieras reemplazar, normalmente se utiliza en sitios web que cuentan con varios temas, por ejemplo, uno oscuro y uno claro.

![Untitled.png](Untitled.png)

[Home - Scalable and Modular Architecture for CSS](http://smacss.com/)
