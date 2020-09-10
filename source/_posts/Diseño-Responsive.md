---
title: Diseño Responsive
categories:
    - Avanzado
---

# Responsive Design

Se le conoce como Diseño Web Responsivo o Adaptativo (responsive web design - RWD) a un conjunto de prácticas que permiten a las páginas web alterar su diseño y apariencia para adaptarse a diferentes anchos de pantalla, resoluciones o dispositivos, desde ordenadores de escritorio a tablets y móviles.

> "*una web para todos*"

![Untitled.png](Untitled.png)

[9 basic principles of responsive web design](https://blog.froont.com/9-basic-principles-of-responsive-web-design/)

[Diseño responsivo entienda como funciona](https://medium.com/@mikejavier/dise%C3%B1o-responsivo-entienda-como-funciona-5f0729132b11)

[Responsinator](http://www.responsinator.com/)

<!-- more -->

# Viewport

El viewport de un dispositivo (Navegador) es el área visible de la ventana gráfica de una página web. Generalmente **no es del mismo tamaño que la página renderizada**, en donde se brindan barras de desplazamiento para que el usuario pueda acceder a todo el contenido.

Antes de las tabletas y los teléfonos móviles, las páginas web estaban diseñadas solo para pantallas de escritorio, y era común que las páginas web tuvieran un diseño estático y un tamaño fijo (**980px**).

Con la llegada de la navegación con tabletas y teléfonos móviles, las páginas web de tamaño fijo eran demasiado grandes para la ventana gráfica. Para solucionar esto, los navegadores en esos dispositivos redujeron la página web para que se ajustara a la pantalla.

Para mitigar este problema, Apple introdujo el meta tag "viewport" en Safari para iOS que permite a los desarrolladores controlar su tamaño y escala. Muchos navegadores hoy lo soportan, aunque no es parte de ningún standard.

```html
<meta name="viewport" content="width=device-width, user-scalable=no">
```

[Usando la etiqueta meta viewport para controlar la composición en los navegadores móviles](https://developer.mozilla.org/es/docs/M%C3%B3vil/Viewport_meta_tag)

### A Pixel is not a Pixel

Los dispositivos móviles cada día tienen una resolución de pantalla mayor a las pantallas de escritorio, sin embargo estas resoluciones no son las mismas que se utilizan en el desarrollo de páginas web con diseño responsive.

Apple fue pionero en esto con su pantalla Retina, donde se dividió el concepto de píxeles en **píxeles de hardware** y de **software**. Un pixel de hardware es un punto de luz individual en la pantalla. Un pixel de software, también llamado **pixel CSS** en el mundo web, es una unidad de medida.

El fabricante del dispositivo determina cuántos píxeles de hardware equivalen a un pixel de software, un concepto conocido como la **densidad de píxeles** del dispositivo. Si un solo pixel CSS contiene cuatro píxeles de hardware (2 píxeles de ancho y 2 píxeles de alto) la densidad de píxeles es 2. Otros dispositivos tienen una densidad de píxeles del dispositivo de 3, lo que significa que cada pixel CSS contiene 9 píxeles de hardware.

Un pixel CSS, por otro lado, está diseñado para ser aproximadamente equivalente en todos los dispositivos. Si carga el mismo sitio web en dispositivos uno al lado del otro con dimensiones físicas similares, pero diferentes proporciones de píxeles, el sitio web tendrá aproximadamente el mismo tamaño visual.

[Designing for a new generation of mobile devices: a pixel is not a pixel](https://juiceboxinteractive.com/blog/a-pixel-is-not-a-pixel-designing-for-a-new-generation-of-mobile-devices/)

[mydevice.io : web devices capabilities](https://www.mydevice.io/)

### Units vw y vh

Las unidades de medida `vh` y `vw` son similares a las unidades `em` o `rem`, en donde se especifica una proporción a la altura del viewport (vh) y al ancho del viewport (vw).

1vh = 1% de la altura del viewport

100vh = altura del viewport

1vw = 1% del ancho del viewport

100vw = ancho del viewport

También existen las unidades vmin y vmax, donde **vmin** hace referencia al tamaño más pequeño de una ventana (alto o ancho según la orientación) y **vmax** se referencia con el tamaño más grande del viewport.

[Viewport units CSS. Qué es y cómo utilizar vw, vh, vmin y vmax](https://www.yunbitsoftware.com/blog/2017/06/22/viewport-units-css-que-es/)

[Cómo funcionan las unidades de medida vh, vw, vmin y vmax - Programando a medianoche](https://www.programandoamedianoche.com/2018/01/como-funcionan-las-unidades-de-medida-vh-vw-vmin-y-vmax/)

# Responsive vs Adaptative

El diseño adaptativo es una estrategia para diseñar una web que se adaptara a cada uno de los dispositivos que se necesite, es decir, que para cada dispositivo se tiene un conjunto de estilos diferentes. Este enfoque requería JavaScript para detectar la resolución de la pantalla y cargar el CSS correcto.

Por el contrario el diseño responsive se basa en adaptar los estilos ya existentes a los diferentes tamaños de viewport con varias técnicas y principios.

# Mobile First vs Desktop First

Dado que el diseño responsive busca adaptar los estilos existentes, es necesario tener una base sobre la cuál partir, y luego definir los diferentes cambios que se aplicarán a una página según las resoluciones.

El término **Desktop** **First** se refiere a comenzar a diseñar un sitio web desde la resolución más grande e ir disminuyendo y adaptando el contenido hacia el diseño de la resolución más pequeña.

El término **Mobile First** por el contrario, se refiere a comenzar con el diseño de un sitio web desde la resolución más pequeña y luego ir creciendo y adaptando el contenido hacia la resolución más grande.

![Untitled1.png](Untitled1.png)

[Diseño responsive: ¿cómo configurarlo correctamente? - Aukera](https://aukera.es/blog/diseno-responsive/)

## Content First

El diseño del contenido primero es un nuevo enfoque en donde el diseño parte desde los contenidos que debe tener una página web, las imágenes reales, textos reales, y así identificar los objetivos de contenidos, el volumen, la audiencia, el tono y las características de los mismos.

[Content-First: ¿qué es primero, el diseño o los contenidos?](https://www.ttandem.com/blog/content-first-que-es-primero-el-diseno-o-los-contenidos/)

# Flow Content

Uno de los principios del diseño responsive es el contenido fluido, este se refiere a que todo nuestro contenido debe fluir con la página, sobretodo con el ancho de la pantalla, pues a medida que el viewport varía el contenido tenderá a ocupar todo el espacio horizontal y estirarse o recogerse en el eje vertical.

## Relative Size

En el eje vertical los elementos pueden variar su altura, pues es común el uso del **scroll** para visualizar todo el contenido de la página, por eso mismo es necesario que no se tengan alturas fijas (**height**) y que los elementos que se ubican debajo se permitan desplazar en caso que un elemento crezca.

En el eje horizontal, es necesario trabajar con unidades relativas `%` o `vh/vw`, de ésta forma cuando varíe el ancho del viewport se conservarán las proporciones predefinidas.

## Limit Sizing

Dado que los tamaños de las pantallas de los dispositivos son diferentes, la experiencia del usuario varía en cada una, en pantallas pequeñas se recomienda que los elementos ocupen todo el espacio posible, sin embargo en pantallas grandes es recomendado dejar espacios vacíos para no saturar de información al usuario, por ello se limitan los tamaños para que no crezcan más de un punto máximo, permitiendo dejar espacios deseados.

# Responsive Images

Las imágenes responsive son imágenes que se ajustan automáticamente para adaptarse al tamaño de la pantalla. El enfoque más simple para las imágenes responsivas es tomar una imagen que tenga el tamaño más grande que puedas necesitar, y reducirla.

```css
img {
	width: 100%;
	height: auto;
}
```

Si desea que una imagen se reduzca si es necesario, pero nunca se amplíe para que sea más grande que su tamaño original, use max-width: 100%:

[How To Create Responsive Images](https://www.w3schools.com/howto/howto_css_image_responsive.asp)

## Changing Images

Una estrategia más avanzada es cambiar las imágenes según el tamaño de la pantalla, pues aunque imágenes muy grandes se puedan reducir, pueden generar una carga más lenta a la hora de abrir la página desde un dispositivo móvil, por lo que también se tienen en cuenta los tamaños de las fotos, la resolución y el peso de cada una para los diferentes casos.

[Imágenes adaptables](https://developer.mozilla.org/es/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)

[Responsive HTML images demo](https://mdn.github.io/learning-area/html/multimedia-and-embedding/responsive-images/responsive.html)

## Vectors

Cuando se trabaja con íconos, ilustraciones o imágenes creadas por computador, es preferible trabajar de forma vectorizado, es decir, archivos **.svg**, ya que este tipo de imágenes no pierden la resolución independientemente de su tamaño.

# Media Queries

Una **media query** es una consulta que se realiza en css para aplicar estilos particulares al documento si se cumple una determinada condición.

Se puede aplicar una media query de dos formas, usando la **regla-at** `@media` en css, o usando el atributo `media` de html a la hora de cargar un archivo css.

```html
<!-- CSS media query on a link element -->
<link rel="stylesheet" media="(max-width: 800px)" href="example.css" >
```

```css
/* CSS media query within a stylesheet */
@media (max-width: 800px) {
	/* CSS Code here */
}
```

[CSS media queries](https://developer.mozilla.org/es/docs/CSS/Media_queries)

[CSS Media Queries](https://www.w3schools.com/css/css3_mediaqueries.asp)

## Media Types

Existen diferentes tipos de medios que se pueden consultar con una **media query,** entre ellos están:

- `all`: ****Apto para todos los dispositivos.
- `print`: ****Destinado a material impreso y visualización de documentos en una pantalla en el modo de vista previa de impresión.
- `screen`: ****Destinado principalmente a las pantallas.
- `speech`: Destinado a sintetizadores de voz.

## Operators

Dado que son condiciones lógicas, también se pueden utilizar operadores lógicas

- `and`: Se utiliza cuando se desea que se cumplan dos o más condiciones al tiempo.
- `,`(*or*): Se utiliza cuando se desea que se cumpla al menos una condicion.
- `not`: Se utiliza cuando se desean aplicar los estilos en caso contrario a la condición dada, el operador **not** aplica a todo el query.
- `only`: El operador only previene que navegadores antiguos que no soportan queries con funciones apliquen los estilos asignados:

Ejemplo:

```css
@media only screen and (min-width: 500px), not speech and (max-width: 980px) {
	/*--- Css Code Here ---*/
}
```

## Size Conditions

Usando media queries se pueden comparar diferentes propiedades relacionadas con el tamaño de la pantalla como:

- **width**: anchura de la ventana del navegador (viewport).
- **height**: altura de la ventana del navegador (viewport).
- **device-width**: anchura de la resolución de pantalla.
- **device-height**: altura de la resolución de pantalla.
- **resolution**: densidad de píxeles (dpi).

Para cada propiedad existen los valores **max** y **min:**

- **min-width:** Mayor al ancho de la ventana del navegador (viewport).
- **max-width:** Menor al ancho de la ventana del navegador (viewport).

A la hora de contruir un sitio usando la estrategia **Mobile First** se usan las condiciones `min-width`, ordenadas de menor a mayor.

```css
@media only screen and (min-width: 480px){}
@media only screen and (min-width: 980px){}
```

Cuando se contruye un sitio usando la estrategia **Desktop First** se usan las condiciones `max-width`, ordenadas de mayor a menor.

```css
@media only screen and (max-width: 980px){}
@media only screen and (max-width: 480px){}
```

### Breakpoints

Los breakpoints o puntos de quiebre, son medidas genéricas de anchura en donde se realizan "*saltos"* para el diseño responsive y se aplican estilos CSS concretos para determinadas media queries.

![Untitled2.png](Untitled2.png)

Existen diferentes sistemas de medidas para los breakpoints.

- 320px, 480px, 768px, 1024px
- 480px, 768px, 960px, 1200px.
- 576px, 768px, 992px, 1200px. (Bootstrap)
- 640px, 1024px, 1200px, 1440px. (Foundation)
- 600px, 960px, 1280px, 1920px. (Material UI)

## Orientation Conditions

Se pueden usar media queries teniendo en cuenta la orientación del dispositivo, para ello se utiliza la propiedad **orientation,** y sus posibles valores son:

- **portrait:** Cuando la altura es mayor al ancho.
- **landscape:** Cuando el ancho es mayor a la altura.

![Untitled3.png](Untitled3.png)

```css
@media (orientation: landscape) {
	/*--- css code here ---*/
}
```
