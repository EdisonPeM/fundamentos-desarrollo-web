---
title: Bootstrap
categories:
    - Avanzado
---

# Introducción

> Bootstrap es una biblioteca multiplataforma o conjunto de herramientas de código abierto para diseño de sitios y aplicaciones web.

Bootstrap consiste de una colección de varios elementos web personalizables y funciones completamente empaquetados en una sola herramienta.

Se creó en el 2011 como solución interna para solucionar las inconsistencias en el desarrollo dentro del equipo de ingeniería de Twitter. Básicamente, no se había establecido ninguna convención sobre las formas en las que los ingenieros de Twitter elegían cómo desarrollar la plataforma.

La versión actual (*Julio 2020*) es bootstrap v4.5.0 y se encuentra en desarrollo la versión bootstrap v5.0

[Bootstrap](https://getbootstrap.com/)

[Bootstrap 4 Tutorial](https://www.w3schools.com/bootstrap4/default.asp)

<!-- more -->

# Configuración

Para incorporar bootstrap a un sitio web basta con agregar los links correspondientes a los estilos y a los javascript.

```html
<!-- CSS only -->
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css" integrity="sha384-9aIt2nRpC12Uk9gS9baDl411NQApFmC26EwAOH8WgZl5MYYxFfc+NcPb1dKGj7Sk" crossorigin="anonymous">
```

```html
<!-- JS, Popper.js, and jQuery -->
<script src="https://code.jquery.com/jquery-3.5.1.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/js/bootstrap.min.js" integrity="sha384-OgVRvuATP1z7JjHLkuOU7Xw704+h835Lr+6QL9UvYjZE3Ipu6Tp75j7Bh/kR0JKI" crossorigin="anonymous"></script>
```

[Introduction](https://getbootstrap.com/docs/4.5/getting-started/introduction/)

# Reboot

Bootstrap internamente **reinicia** todos los estilos base de una página web para que exista una uniformidad entre diferentes navegadores, por lo que al usar bootstrap ya no es necesario definir reglas como:

```css
*,
*::before,
*::after {
	box-sizing: border-box;
}

body {
	margin: 0;
	background-color: #fff;
}
```

Algunos de sus cambios son:

- Las fuentes web predeterminadas (Helvetica Neue, Helvetica y Arial) cambian en Bootstrap 4 y son remplazadas con una "pila de fuentes nativas" para una representación de texto óptima en cada dispositivo y sistema operativo.
- Todos los elementos de encabezado, párrafos y listas no poseen margin-top, y poseen un `margin-bottom: 1rem`;
    - Las listas anidadas no tienen margin.
- Las listas de descripción también poseen diferentes márgenes, el elemento `<dd>` no posee `margin-left` y el elemento `<dt>` están en negrita.
- Las tablas están ajustadas a bordes colapsados  y aseguran una consistencia constante **text-align**. Cambios adicionales para bordes, relleno y más vienen con la clase `.table`
- Varios elementos de formulario tienen estilos base más simples.
    - `<fieldset>`: No tiene bordes, relleno o margen, por lo que se pueden usar fácilmente como envoltorios para entradas individuales o grupos de entradas.
    - `<legend>`: Se han rediseñado para mostrarse como una especie de encabezado.
    - `<label>`: Tiene ahora un `display: inline-block` para soportar márgenes.
    - `<input>`, `<select>`, `<textarea>` y `<button>s` se abordan principalmente mediante Normalize, pero Reboot también elimina sus márgenes.
    - `<textarea>`: Solo se puede cambiar de tamaño verticalmente.
    - `<button>`: Tiene un `cursor: pointer` cuando no está deshabilitado.

[Reboot](https://getbootstrap.com/docs/4.5/content/reboot/)

## Nuevo Atributo

Se agrega el atributo de html `hidden` con el que se define un `display:none` por defecto.

# Contenido

Bootstrap define diferentes conjuntos de clases para personalizar el contenido de una página según la categoría.

## Tipografía

- Las clases `.h1` hasta `.h6` simulan los tamaños de los titulos, permitiendo usar las etiquetas de html según su finalidad semántica.
- Las clases `.display-1` hasta `.display-4` muestran texto más grande que los títulos tradicionales.
- La clase `.text-muted` ayuda a denotar texto secundario.
- La case `.lead` permite destacar un párrafo

[Typography](https://getbootstrap.com/docs/4.5/content/typography/)

## Texto

Entre las diferentes clases que bootstrap tiene para gestionar el comportamiento del texto destacan.

- `.text-left`: Texto alineado a la izquierda
- `.text-center`: Texto centrado
- `.text-right`: Texto alineado a la derecha
- `.text-justify`: Texto justificado

Estas clases permiten un comportamiento responsive.

[Text](https://getbootstrap.com/docs/4.5/utilities/text/)

[Interactions](https://getbootstrap.com/docs/4.5/utilities/interactions/)

## Listas

- La clase `.list-unstyled` permite generar una lista sin viñetas (ya sea ordenada o sin ordenar).
- La clase `.list-inline` permite generar una lista en línea (horizontal), para ello los ítems de lista deben usar la clase `.list-inline-item`

[Typography](https://getbootstrap.com/docs/4.5/content/typography/#lists)

## Tablas

Las tablas de boostrap no tienen decoración alguna, solamente colapsan los bordes, sin embargo se pueden personalizar con la clase .table acompañada de las variaciones de diseño.

- `.table` Agrega un estilo de tabla con líneas horizontales a una tabla
- `.table-dark` Acompaña a la clase `.table` para crear una tabla oscura con texto claro.
- `.table-striped` acompaña a la clase .table para crar una tabla con colores intercalados entre las filas de la tabla.
- `.thead-light` y `.thead-dark` definen los estilos de la cabecera de la tabla (`<thead>`).

[Tables](https://getbootstrap.com/docs/4.5/content/tables/)

## Imágenes

- `.img-fluid` con esta clase se pueden crear imágenes responsive, es decir `max-width:100%`
- `.img-thumbnail` permite agregar un marco (padding) y borde redondeado de 1px.

[Images](https://getbootstrap.com/docs/4.5/content/images/)

## Embebidos

Para videos de youtube embebidos, bootstrap maneja una serie de clases que permiten gestionar el aspecto del video.

- La clase `.embed-responsive-item` Se debe agregar al `<iframe>`
- Este debe ir dentro de un div con la clase `.embed-responsive`, esta clase puede ir acompañada de la clase correspondiente al aspecto que se desea:
    - `.embed-responsive-21by9`
    - `.embed-responsive-16by9`
    - `.embed-responsive-4by3`
    - `.embed-responsive-1by1`

[Embeds](https://getbootstrap.com/docs/4.5/utilities/embed/)

## Colores

Bootstrap tiene predefinido un set de colores:

- **primary**: #007bff
- **secondary**: #6c757d
- **success**: #28a745
- **danger**: #dc3545
- **warning**: #ffc107
- **info**: #17a2b8
- **light**: #f8f9fa
- **dark**: #343a40
- **white**: #fff

![Untitled.png](Untitled.png)

Estos colores se utilizan agregando la palabra clave según donde sea posible

- `.text-[color]` Permite dar color al texto según la palabra clave del set de colores
- `.bg-[color]` Permiten cambiar el color de fondo según la palabra clave del set de colores

[Colors](https://getbootstrap.com/docs/4.5/utilities/colors/)

Otros elementos donde se utilizan estas palabras son:

- `.border-[color]` Permite cambiar el color del borde según la palabra clave del set de colores (esta debe ir acompañada de las clases de bordes `.border`)
- `.btn-[color]` Permite cambiar el color de un botón según la palabra clave del set de colores (esta debe ir acompañada de las clases de botones `.btn`)

# Responsive Design

Bootstrap utiliza un diseño mobile-first con un sistema de 12 columnas y 4 diferentes breakpoints, con lo que permite crear 5 diferentes diseños.

**El objetivo es el diseño móvil primero y sensible**. El CSS de Bootstrap tiene como objetivo aplicar el mínimo de estilos para hacer que un diseño funcione en el punto de interrupción más pequeño, y luego capas en estilos para ajustar ese diseño para dispositivos más grandes. Esto optimiza el CSS, mejora el tiempo de representación y proporciona una gran experiencia para sus visitantes.

- El tamaño **base** usa el nombre de **Extra Small (**<576px**)** *- Mobile Portrait*
- **Small (sm)** se utiliza para pantallas más grandes de 576px. *- Mobile Landscape*
- **Medium (md)** se utiliza para pantallas más grandes de 768px. *- Tablet Portrait*
- **Large (lg)** se utiliza para pantallas más grandes de 992px. *- Tablet landscape, Desktops*
- **Extra Large (xl)** se utiliza para pantallas más grandes de 1200px. *- Large Desktops*

![Untitled1.png](Untitled1.png)

![Untitled2.png](Untitled2.png)

![Untitled3.png](Untitled3.png)

[Overview](https://getbootstrap.com/docs/4.5/layout/overview/#responsive-breakpoints)

## Contenedores

Los contenedores de Bootstrap permiten contener y centrar el contenido de un sitio dentro de ellos, estos contenedores matienen un tamaño inicial de 100% y luego para cada breakpoint utilizan un tamaño fijo buscando mantener una buena proporción en cada pantalla.

Existen diferentes tipos de contenedores, cada uno busca ocupar el 100% hasta llegar al breakpoint que se corresponda según:

![Untitled4.png](Untitled4.png)

`.container` y `.container-sm` cumplen el mismo objetivo

[Overview](https://getbootstrap.com/docs/4.5/layout/overview/)

[Bootstrap 4 Containers](https://www.w3schools.com/bootstrap4/bootstrap_containers.asp)

## Layouts

El sistema de grid layout de Bootstrap utiliza una serie de contenedores (`.container-*`), filas (`.row`) y columnas (`.col-*`) para diseñar y alinear el contenido.

- Los contenedores proporcionan un medio para centrar y rellenar horizontalmente los contenidos de su sitio.
- Las filas son envoltorios para columnas. Cada columna tiene un padding horizontal para controlar el espacio entre ellas.
    - Se pueden eliminar esos espacios con la clase `.no-gutters` junto con `.row`
- El contenido debe colocarse dentro de las columnas y solo las columnas pueden ser hijos inmediatos de las filas.
- Las clases de columnas indican la cantidad de columnas que le gustaría usar de las 12 posibles por fila.

```html
<div class="container">
	<div class="row">
		<div class="col-3"></div>
		<div class="col-7"></div>
		<div class="col-2"></div>
	</div>
</div>
```

---

Las columnas de bootstrap responden a los breakpoints, esto es que siempre buscan ocupar las 12 columnas hasta llegar al breakpoint que se corresponda, luego se organizan según la cantidad de columnas que se definió y según los infijos que se utilicen (sm, md, lg, xl).

![Untitled5.png](Untitled5.png)

Se pueden combinar diferentes tipos de columnas para crear un diseño responsive

```html
<div class="container">
	<div class="row">
		<div class="col-sm-6 col-lg-3"></div>
		<div class="col-sm-6 col-lg-7"></div>
		<div class="col-lg-2"></div>
	</div>
</div>
```

### AutoLayout

Se pueden utilizar las clases de columnas (`.col`, `.col-sm`, `.col-md`, `.col-lg` y `.col-xl`) sin indicar la cantidad de columnas que ocupará cada columna y así generar columnas con el mismo tamaño.

```html
<div class="container">
	<div class="row">
		<div class="col-sm"></div>
		<div class="col-sm"></div>
		<div class="col-sm"></div>
		<div class="col-sm"></div>
****		<div class="col-sm"></div>
	</div>
</div>
```

[Grid system](https://getbootstrap.com/docs/4.5/layout/grid/)

[Bootstrap 4 Grid System](https://www.w3schools.com/bootstrap4/bootstrap_grid_system.asp)

### Alineamiento

La clase `.row` utiliza el módulo de flexbox, por lo que admite utilidades de flexbox para alinear las columnas horizontalmente.

# Box-Model

Bootstrap configura el box model en border-box, esto es, que los tamaños de los elementos incluyen el border y el padding.

## Tamaños

La configuración de tamaño se puede realizar con clases de bootstrap, sin embargo estas son limitadas:

`.w-25`: Width 25%

`.w-50`: Width 50%

`.w-75`: Width 75%

`.w-100`: Width 100%

`.w-auto`: Width auto

`.h-25`: Height 25% 

`.h-50`: Height 50% 

`.h-75`: Height 75% 

`.h-100`: Height 100% 

`.h-auto`: Height auto

[Sizing](https://getbootstrap.com/docs/4.5/utilities/sizing/)

## Espacios

Los espacios se refieren al **margin** y al **padding**, para ello bootstrap cuenta con un conjunto de clases bien estructuradas que permiten gestionar los tamaños y lados de los espacios.

Este conjunto de clases tiene la siguiente estructura:

- `.{propiedad}{lado(s)}-{tamaño}` Para Mobile portrait
- `.{propiedad}{lado(s)}-{breakpoint}-{tamaño}` Para otras pantallas

Donde la propiedad se refiere al margin (`m`) o padding (`p`)

Los lados se refiere a top (`t`), right (`r`), bottom (`b`), left (`l`), top y bottom (`y`), left y right (`x`).

Los tamaños son relativos a un tamaño predeterminado de bootstrap, estos se utilizan como números entre `0` (sin espacios) hasta `5` (tamaño más grande), además del valor `auto`

El breakpoint se refiere a los infijos `sm`, `md`, `lg` y `xl`, con esto se refiere a que los espacios definidos solamente se aplicarán DESDE el breackpoint correspondiente.

```html
<div class="p-1 p-md-3">
	<!-- contenido -->
</div>
```

Las clases `mx-auto` y `mx-{breakpoint}-auto` funcionan bien para centrar elementos de bloque.

[Spacing](https://getbootstrap.com/docs/4.5/utilities/spacing/)

## Borders

Para agregar bordes a un elemento se puede usar la clase:

- `.border` con ésto se crea un borde sólido de 1px de ancho (color gris por defecto).
- Para cambiar los colores del borde se pueden agregar las clases `.border-*[color]*` donde [color] se refiere a una palabra clave del set de colores de bootstrap.
- `.rounded` Se utiliza para agregar bordes redondeados, esto agrega un redondeo de .25rem (*4px si la fuente es de 16px*).
- `.rounded-circle` Se utiliza para crear un círculo, agregando un redondeado de 50%.

[Borders](https://getbootstrap.com/docs/4.5/utilities/borders/)

## Sombras

Para agregar sombras de bootstrap se pueden usar las clases:

- `.shadow`: Genera una sombra Normal de bootstrap
- `.shadow-sm`: Genera una sombra más pequeña (no debe confundirse con el breakpoint sm)
- `.shadow-lg`:  Genera una sombra más grande (no debe confundirse con el breakpoint lg)

[Shadows](https://getbootstrap.com/docs/4.5/utilities/shadows/)

# Display

Las clases que manipulan el display de un elemento puede variar según los puntos de quiebre, estas clases tienen la estructura:

- `.d-{tipo}` Para Mobile portrait
- `.d-{breakpoint}-{tipo}` Para Otras pantallas

Donde los tipos son:

- `none`
- `block`
- `flex`

- `inline`
- `inline-block`
- `inline-flex`

El breakpoint se refiere a los infijos `sm`, `md`, `lg` y `xl`, con esto se refiere a que el display aplicará DESDE el breackpoint correspondiente.

Esto nos permite cambiar el tipo de display entre diferentes breakpoints, y de la misma forma nos permite ocultar y mostrar elementos en diferentes pantallas.

```html
<!-- Elemento oculto en celular -->
<div class=""d-none d-md-block>
</div>

<!-- Elemento visible en celular y escritorio grande pero oculto en tablet -->
<div class=""d-md-none d-xl-block>
</div>

<!-- Elemento block en celular pero flex en tablet y desktop-->
<div class=""d-block d-md-flex>
</div>
```

Bootstrap v4.5 no tiene soporte para `display: grid`;

[Display property](https://getbootstrap.com/docs/4.5/utilities/display/)

[Display property](https://getbootstrap.com/docs/4.5/utilities/display/#hiding-elements)

# Flexbox

Para manipular las configuraciones de un flexbox bootstrap ofrece un conjunto de clases correspondientes:

- **Flex-direction**: `.flex-row`,`.flex-row-reverse`, `.flex-column`, `.flex-column-reverse`
- **Flex-wrap**: `.flex-nowrap`, `.flex-wrap`, `.flex-wrap-reverse`
- **Justify-content**: `.justify-content-start`, `.justify-content-end`, `.justify-content-center`, `.justify-content-between`, `.justify-content-around`
- **align-items**: `.align-items-start`, `.align-items-end`, `.align-items-center`, `.align-items-baseline`, `.align-items-stretch`

Todas las clases de flexbox tienen comportamiento responsive, esto es que admiten los puntos de quiebre.

[Flex](https://getbootstrap.com/docs/4.5/utilities/flex/)

[A Complete Guide to Flexbox | CSS-Tricks](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

# Float

El módulo de flotantes de bootstrap también contiene clases responsivas según los puntos de quiebre, estas clases tienen la estructura:

- `.float-{tipo}` Para Mobile portrait
- `.float-{breakpoint}-{tipo}` Para otras pantallas

Donde los tipos son:

- `left`
- `right`
- `none`

El breakpoint se refiere a los infijos `sm`, `md`, `lg` y `xl`, con esto el elemento se puede configurar para que flote solamente en ciertas pantallas

Para evitar desbordamientos por flotantes, el contenedor debe tener la clase `.clearfix`

```html
<div class="clearfix">
	<img class="d-block mx-auto float-md-left " src="..." alt="...">
	<p>
		lorem....
	</p>
	<img class="img-fluid d-block mx-auto float-md-right m-md-2">
	<p>
		lorem....
	</p>
</div>
```

[Float](https://getbootstrap.com/docs/4.5/utilities/float/)

[Clearfix](https://getbootstrap.com/docs/4.5/utilities/clearfix/)

# Position

Existen diferentes clases para manipular el posicionamiento de un elemento, entre estas existen clases para fijar elementos en la pantalla:

- `.fixed-top`: Para fijar un elemento en la parte superior de lado a lado
- `.fixed-bottom`: Para fijar un elemento en la parte superior de lado a lado
- `.sticky-top`: Genera un comportamiento sticky en la parte superior de lado a lado

[Position](https://getbootstrap.com/docs/4.5/utilities/position/)
