---
title: Elementos de Boostrap
categories:
    - Avanzado
---

# Componentes

Adicional a las diferentes clases que tiene bootstrap para gestionar la visualización y el diseño responsivo, posee una serie de componentes prediseñados con sus respectivas funcionalidades que responden a la interacción del usuario.

<!-- more -->

## Jumbotron

Un Jumbotron es un componente para llamar la atención del usuario, se utiliza para mostrar mensajes sobre algún contenido o información especial.

```html
<!-- jumbotron del tamaño de un contenedor -->
<div class="jumbotron">
	<!-- contenido -->
</div>

<!-- Jumbotrón que ocupa el 100% del ancho -->
<div class="jumbotron jumbotron-fluid">
  <div class="container">
		<!-- contenido -->
  </div>
</div>
```

[Jumbotron](https://getbootstrap.com/docs/4.5/components/jumbotron/)

[Bootstrap 4 Jumbotron](https://www.w3schools.com/bootstrap4/bootstrap_jumbotron.asp)

## Carousel

Un carousel se utiliza para mostrar imagenes de forma secuencial, estos poseen 3 partes

- `.carousel-indicators`: Se utilizan para seleccionar una imagen en específico
- `.carousel-inner`: Aquí van la secuencia de imagenes
    - `.carousel-item`: es el contenedor de las imagenes.
- `.carousel-control-[prev/next]`: son los controles para navegar entre las imagenes

Todo carrusel debe tener un **id** diferente, y tanto los **indicadores** como los **controles** deben referenciar a dicho id para asociar la interacción con éste.

```html
<div id="**example**" class="carousel slide" data-ride="carousel">

  <!-- Indicators -->
  <ul class="carousel-indicators">
    <li data-target="**#example**" data-slide-to="0" class="active"></li>
    <li data-target="**#example**" data-slide-to="1"></li>
    <li data-target="**#example**" data-slide-to="2"></li>
  </ul>

  <!-- The slideshow -->
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="..." alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." alt="...">
    </div>
  </div>

  <!-- Left and right controls -->
  <a class="carousel-control-prev" href="**#example**" data-slide="prev">
    <span class="carousel-control-prev-icon"></span>
  </a>
  <a class="carousel-control-next" href="**#example**" data-slide="next">
    <span class="carousel-control-next-icon"></span>
  </a>
</div>
```

[Carousel](https://getbootstrap.com/docs/4.5/components/carousel/)

[Bootstrap 4 Carousel](https://www.w3schools.com/bootstrap4/bootstrap_carousel.asp)

## List Group

Las listas en grupos se utilizan para mostrar información secuencial, admiten cualquier tipo de contenido.

```html
<ul class="list-group">
  <li class="list-group-item active">Cras justo odio</li>
  <li class="list-group-item">Dapibus ac facilisis in</li>
  <li class="list-group-item">Morbi leo risus</li>
</ul>
```

[List group](https://getbootstrap.com/docs/4.5/components/list-group/)

[Bootstrap 4 List Groups](https://www.w3schools.com/bootstrap4/bootstrap_list_groups.asp)

## Cards

Una tarjeta es un contenedor de contenido flexible y extensible. Incluye una amplia variedad de contenido, colores de fondo contextuales y potentes opciones de visualización.

Las cartas se componen de:

- `.card-header`: Consiste en la cabecera de una tarjeta
- `.card-img-top`: Se utiliza cuando desea agregar una imagen a la tarjeta
- `.card-body`: aquí va el contenido mismo de la tarjeta
- `.card-footer`: Se utiliza para agregar un pie de página a esta carta

```html
<div class="card">
	<div class="card-header">
		<!-- Header Content -->	
	</div>
  <img src="..." class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Lorem</p>
    <a href="#" class="card-link">Card link</a>
    <a href="#" class="card-link">Another link</a>
  </div>
	<div class="card-footer">
		<!-- Footer Content -->
  </div>
</div>
```

[Cards](https://getbootstrap.com/docs/4.5/components/card/)

[Bootstrap 4 Cards](https://www.w3schools.com/bootstrap4/bootstrap_cards.asp)

## Sobreposicion de texto en imagenes

Se puede camubiar la estructura de una carta para tener texto sobre las imagenes, usando las clases `.card-img` para la imagen y `.card-img-overlay` para el contenido.

```html
<div class="card bg-dark text-white">
  <img src="..." class="card-img" alt="...">
  <div class="card-img-overlay">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    <p class="card-text">Last updated 3 mins ago</p>
  </div>
</div>
```

## Conjunto de Cartas

Las cartas se pueden utilizar dentro del sistema de grid de bootstrap (container, row y col-*), sin embargo existen otras formas de agrupar cartas, simplemente agrupandolas dentro de un div con alguna de estas clases.

- `.card-group`: Se organizan en grupos de 3 cartas sin espacio entre ellas.
- `.card-deck`:  Se organizan en grupos de 3 cartas con espacio entre ellas.
- `.card-columns`: Se organizan usando un diseño Masonry.

[Cards](https://getbootstrap.com/docs/4.5/components/card/#card-layout)

## Stretched-link

Se utiliza cuando se desea convertir a toda la tarjeta en un link, se agrega la clase `.stretched-link` al link donde se encuentra la referencia.

```html
<div class="card" style="width: 18rem;">
  <img src="..." class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Card with stretched link</h5>
    <p class="card-text">Some quick example text.</p>
    <a href="#" class="card-link **stretched-link**">Go somewhere</a>
  </div>
</div>
```

[Stretched link](https://getbootstrap.com/docs/4.5/utilities/stretched-link/)

## Botones

Bootstrap tiene predefinido un conjunto de botones usando la clase `.btn` ****en algún botón o link, esta clase define la estructura del botón, por lo que se usa en conjunto con `.btn-[color]` o `.btn-outline` para darle estilos usando las palabras clave de los colores de bootstrap.

Los links pueden tener estilos de botónes y los botones pueden tener estilos de links, sin embargo los links se deben usar cuando queremos ir a otra página y los botones cuando queremos realizar alguna acción con la interacción del usuario.

[Buttons](https://getbootstrap.com/docs/4.5/components/buttons/)

[Bootstrap 4 Buttons](https://www.w3schools.com/bootstrap4/bootstrap_buttons.asp)

[Button group](https://getbootstrap.com/docs/4.5/components/button-group/)

[Bootstrap 4 Button Groups](https://www.w3schools.com/bootstrap4/bootstrap_button_groups.asp)

## Dropdown

Los dropdown son botones que esconden un submenu, estos se componen de dos partes:

- `.dropdown-toggle`: el cual es el botón que despliega el submenu.
- `.dropdown-menu`: Un contenedor con `.dropdown-item` los cuales son las opciones del menu

```html
<div class="dropdown">
  <button id="**dropdownExample**" class="btn btn-secondary dropdown-toggle" type="button"
					data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    <!-- text of a dropdown button -->
  </button>
  <div class="dropdown-menu" aria-labelledby="**dropdownExample**">
    <a class="dropdown-item" href="#">Action</a>
    <a class="dropdown-item" href="#">Another action</a>
    <a class="dropdown-item" href="#">Something else here</a>
  </div>
</div>
```

[Dropdowns](https://getbootstrap.com/docs/4.5/components/dropdowns/)

[Bootstrap 4 Dropdowns](https://www.w3schools.com/bootstrap4/bootstrap_dropdowns.asp)

## Collapse

Los collapse se utilizan para cambiar la visibilidad de un elemento usando un accionador (botón)

Estos elementos pueden estar separados (a diferencia del dropdown) por lo que se puede utilizar de multiples formas

El contenido a esconder deberá ir en un contenedor con la clase `.collapse` y debe tener un **`id`**, este se utiliza para el accionador.

El accionador (deberalmente un botón) debe usar los atributos`.data-toggle="collapse"` y `.data-target`, en este ultimo debe ir **#** y el id del collapse.

```html
<button data-toggle="collapse" data-target="**#demo**">
	<!-- text of a collapse button -->
</button>

<div id="**demo**" class="collapse">
	<!-- collapse content -->
</div>
```

[Collapse](https://getbootstrap.com/docs/4.5/components/collapse/)

[Bootstrap 4 Collapse](https://www.w3schools.com/bootstrap4/bootstrap_collapse.asp)

## Modal

Un modal es un elemento que se sobrepone a la página principal y la deshabilita pero la mantiene visible. 

Al igual que los collapse, los elementos modales requieren un activador (generalmente un botón) y un contenedor con el contenido del modal.

Para tener el código limpio, se recomienda que el contenedor del modal se escriba después del footer y antes de cerrar el body en el html.

El accionador (deberalmente un botón) debe usar los atributos`.data-toggle="modal"` y `.data-target`, en este ultimo debe ir **#** y el id del modal.

El contenido a esconder deberá ir en un contenedor con la clase `.modal` y debe tener un **`id`**, este se utiliza para el accionador, el modal tiene diferentes elementos:

- `.modal`, `.modal-dialog` y `.modal-content` son las clases requeridas para crear un modal.
- `.modal-header`: Aquí va el titulo del modal, así como el botón de cierre (de ser necesario)
    - El botón de cierre debe tener el atributo `data-dismiss="modal"`
- `.modal-body`: En este contendor va el contenido mismo del modal
- `.modal-footer`: Agrega un pie de página al modal.

```html
<!-- Button trigger modal -->
<button data-toggle="modal" data-target="**#exampleModal**">
	<!-- text of a collapse button -->
</button>

<!-- Modal -->
<div class="modal fade" id="**exampleModal**" tabindex="-1" 
		role="dialog" aria-labelledby="***exampleModalLabel***" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="***exampleModalLabel***">
					Modal title
				</h5>

				<!-- Botón de cierre -->
        <button type="button" class="close" ***data-dismiss="modal"*** aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
				<!-- Modal Content -->
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" ***data-dismiss="modal"***>
					Close
				</button>
        <button type="button" class="btn btn-primary">
					Save changes
				</button>
      </div>
    </div>
  </div>
</div>
```

[Modal](https://getbootstrap.com/docs/4.5/components/modal/)

[Bootstrap 4 Modals](https://www.w3schools.com/bootstrap4/bootstrap_modal.asp)

## Nav

Este elemento permite crear una lista con opciones de navegación

- la clase `.active` se utiliza para determinar el elemento actual seleccionado
- la clase `.disabled` se utiliza para definir un link deshabilitado

```html
<ul class="nav">
  <li class="nav-item">
    <a class="nav-link active" href="#">Active</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Link</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
  </li>
</ul>
```

[Navs](https://getbootstrap.com/docs/4.5/components/navs/)

[Bootstrap 4 Navs](https://www.w3schools.com/bootstrap4/bootstrap_navs.asp)

## Tabs

Los elementos de navegación pueden crear un sistema de pestañas interno para mejorar la organización del contenido. Las pestañas dividen el contenido en secciones significativas que ocupan menos espacio en la pantalla.

Estas pestañas consisten en un sistema con:

- `.nav-tabs` se agrega al sistema de navegación, para determinar la cantidad de pestañas y sus titulos
- `.tab-content`: define el contenido de cada pestaña, esta debe tener una serie de `.tab-pane` con un **id** que se utilizará por las pestañas para mostrar el respectivo contenido.

```html
<ul class="nav nav-tabs" id="myTab" role="tablist">
  <li class="nav-item" role="presentation">
    <a class="nav-link active" id="**home-tab**" 
				data-toggle="tab" href="**#home**" 
				role="tab" aria-controls="**home**" aria-selected="true">
			Home
		</a>
  </li>
  <li class="nav-item" role="presentation">
    <a class="nav-link" id="**profile-tab**" 
				data-toggle="tab" href="**#profile**"
				role="tab" aria-controls="**profile**" aria-selected="false">
			Profile
		</a>
  </li>
  <li class="nav-item" role="presentation">
    <a class="nav-link" id="**contact-tab**" 
				data-toggle="tab" href="**#contact**"
				role="tab" aria-controls="**contact**" aria-selected="false">
			Contact
		</a>
  </li>
</ul>

<div class="tab-content" id="myTabContent">
  <div class="tab-pane fade show active" id="**home**" 
				role="tabpanel" aria-labelledby="**home-tab**">
		<!-- Home tab content -->
	</div>
  <div class="tab-pane fade" id="**profile**" 
				role="tabpanel" aria-labelledby="**profile-tab**">
		<!-- Profile tab content -->
	</div>
  <div class="tab-pane fade" id="**contact**" 
				role="tabpanel" aria-labelledby="**contact-tab**">
		<!-- Contact tab content -->
	</div>
</div>
```

[Navs](https://getbootstrap.com/docs/4.5/components/navs/#javascript-behavior)

## Navbar

Las navbar de bootstrap son componentes para crear barras de navegación responsivas, esto es que el contenido (links) de la barra de navegación se muestren en un tamaño particular, ya que el diseño es mobile first siempre está escondida por defecto (en un collapse).

Los elementos que componen una barra de navegación son los siguientes:

- `.navbar` para el contenedor, generalmente `<nav>`, Esta puede ir acompañada de:
- `.navbar-expand-{breakpoint}` donde breackpoint se refiere al tamaño desde el cual se desea mostrar la barra completa (**sm, md, lg, xl**).
- `.navbar-ligth`: Para usar con colores de fondo claros, esto oscurece las letras.
- `.navbar-dark`: para colores de fondo oscuros, esto usa letras claras.
- Alguna utilizad de [posicionamiento](https://getbootstrap.com/docs/4.4/utilities/position/#sticky-top) de bootstrap

Dentro del navbar existen inicialmente 2 componentes:

- `.navbar-brand` Usado para el nombre de la empresa, producto o proyecto. Esta clase generalmente se usa en un `<a>`
- `.navbar-nav` Usado para listar las opciones de la barra de navegación

Para las opciones de navegación se suele utilizar un collapse para esconder la barra en un menú hamburguesa, para ello debe estar contenida en un div con la clases `.collapse.navbar-collapse`, así mismo debe existir un botón que desplegue el collapse con la clase `.navbar-toggler`.

```html
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Navbar</a>

  <button class="navbar-toggler" type="button" 
					data-toggle="collapse" data-target="**#navbarMenu**" 
					aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="**navbarMenu**">
    <ul class="navbar-nav">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home</a>
      </li>

      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>

      <li class="nav-item dropdown">
        <a class="nav-link dropdown-toggle" href="#" 
						id="**navbarDropdown**" role="button" data-toggle="dropdown" 
						aria-haspopup="true" aria-expanded="false">
          Dropdown
        </a>
        <div class="dropdown-menu" aria-labelledby="**navbarDropdown**">
          <a class="dropdown-item" href="#">Action</a>
          <a class="dropdown-item" href="#">Another action</a>
          <div class="dropdown-divider"></div>
          <a class="dropdown-item" href="#">Something else here</a>
        </div>
      </li>

      <li class="nav-item">
        <a class="nav-link disabled" href="#" 
						tabindex="-1" aria-disabled="true">Disabled</a>
      </li>
    </ul>
  </div>
</nav>
```

En los navbar se pueden usar dropdowns o formularios en linea.

[Navbar](https://getbootstrap.com/docs/4.5/components/navbar/)

[Bootstrap 4 Navigation Bar](https://www.w3schools.com/bootstrap4/bootstrap_navbar.asp)

## Formularios

Los formularios de bootstrap se pueden construir agregando la clase `.form-control` a un input, select o textarea y `.from-group` al conenedor del input y label.

```html
<div class="form-group">
  <label for="example">Email address</label>
  <input class="form-control" type="email" id="example" placeholder="name@example.com">
</div>
```

---

Para inputs de archivos se usa la clase `.form-control-file`

Para inputs de rangos se usa la clase `.form-control-range`

Para checkbox se utilizan las clases:

- `.form-check` para el contenedor
- `.form-check-input` en para el input tipo ckecbox
- `.form-check-label` para el label.

```html
<div class="form-group form-check">
  <input class="form-check-input" type="checkbox" id="exampleCheck">
  <label class="form-check-label" for="exampleCheck">Check me out</label>
</div>
```

---

Para Personalizar el layout se pueden usar filas y columnas de bootstrap dentro del formulario usando la clase `.form-row` para las filas

```html
<form>
  <div class="form-row">
    <div class="col-md">
      <input type="text" class="form-control" placeholder="First name">
    </div>
    <div class="col-md">
      <input type="text" class="form-control" placeholder="Last name">
    </div>
  </div>
</form>
```

```html
<form>
  <div class="form-row">
    <div class="form-group col-md-6">
      <label for="inputEmail">Email</label>
      <input class="form-control" id="inputEmail" type="email">
    </div>
    <div class="form-group col-md-6">
      <label for="inputPassword">Password</label>
      <input class="form-control" id="inputPassword" type="password">
    </div>
  </div>
  <div class="form-group">
    <label for="inputAddress">Address</label>
    <input class="form-control" id="inputAddress" placeholder="1234 Main St">
  </div>
  <div class="form-group">
    <label for="inputAddress2">Address 2</label>
    <input class="form-control" id="inputAddress2" placeholder="Apartment, studio, or floor">
  </div>
  <div class="form-row">
    <div class="form-group col-md-6">
      <label for="inputCity">City</label>
      <input type="text" class="form-control" id="inputCity">
    </div>
    <div class="form-group col-md-4">
      <label for="inputState">State</label>
      <select id="inputState" class="form-control">
        <option selected>Choose...</option>
        <option>...</option>
      </select>
    </div>
    <div class="form-group col-md-2">
      <label for="inputZip">Zip</label>
      <input type="text" class="form-control" id="inputZip">
    </div>
  </div>
  <div class="form-group">
    <div class="form-check">
      <input class="form-check-input" type="checkbox" id="gridCheck">
      <label class="form-check-label" for="gridCheck">
        Check me out
      </label>
    </div>
  </div>
  <button type="submit" class="btn btn-primary">Sign in</button>
</form>
```

[Forms](https://getbootstrap.com/docs/4.5/components/forms/)

[Bootstrap 4 Forms](https://www.w3schools.com/bootstrap4/bootstrap_forms.asp)

[Bootstrap 4 Custom Forms](https://www.w3schools.com/bootstrap4/bootstrap_forms_custom.asp)

## Inputs

Los inputs de un formulario se pueden personalizar para mostrar iconos o simbolos al usuario. para ello se utiliza dentro del `.input-group` las clases:

- `.input-group-prepend` para mostrar algo antes del input
- `.input-group-append` para mostrar algo después del input
- `.input-grouptext` para el contenido mismo

```html
<div class="input-group">
  <div class="input-group-prepend">
    <span class="input-group-text">@</span>
  </div>
  <input type="text" class="form-control" placeholder="Username">
</div>

<div class="input-group">
  <input type="text" class="form-control">
  <div class="input-group-append">
    <span class="input-group-text">$</span>
  </div>
</div>
```

[Input group](https://getbootstrap.com/docs/4.5/components/input-group/)

[Bootstrap 4 Input Groups](https://www.w3schools.com/bootstrap4/bootstrap_forms_inputs.asp)

## Alertas

Las alertas son pequeños componentes para mostrar mensajes contextuales en respuesta de acciones típicas de los usuarios.

Consta de la clase `.alert` y `.alert-{color}` según las opciones de colores de bootstrap

```html
<div class="alert alert-primary" role="alert">
  A simple primary alert with <a href="#" class="alert-link">an example link</a>. Give it a click if you like.
</div>
```

[Alerts](https://getbootstrap.com/docs/4.5/components/alerts/)

[Bootstrap 4 Alerts](https://www.w3schools.com/bootstrap4/bootstrap_alerts.asp)

# Iconos

Bootstrap cuenta con su propio conjunto de iconos, sin embargo se puede trabajar de la mano con otras librerías como **fontawesome**, **material-icons** entre otros.

[Bootstrap Icons](https://icons.getbootstrap.com/)

[Icons](https://getbootstrap.com/docs/4.5/extend/icons/)

# Temas

Dado que bootstrap es una librería de código abierto con licencia MIT, existen variaciones al framework, en el siguient link podrá encontrar versiones de bootstrap creados por la comunidad con diferentes colores, tipografía, tamaños y espaciado de los componentes.

[Free themes for Bootstrap](https://bootswatch.com/)

## Material Design

Si se desea trabajar con componentes de material design junto con las clases y utilidades de bootstrap, existen varias integraciones de éstos.

Material design es el **sistema de diseño** de google desarrollado en el 2014, existen diferentes frameworks como *materializecss* o *material kit* que se basan en este sistema de diseño, siendo (junto con *foundation*) las alternativas a bootstrap.

[Bootstrap Material Design](https://fezvrasta.github.io/bootstrap-material-design)

[Material Design for Bootstrap 4 - the most popular & free UI KIT](https://mdbootstrap.com/)

# Plantillas

Dado que bootstrap tiene licencia MIT, se pueden crear páginas de código libre (como no) y gratuitas (como pagas) desde donde se puede crear una página web, las plantillas y temas de bootstrap son páginas (archivos) creados por la comunidad para tener un punto de partida, donde solamente hay que modificar el contenido para adaptarlo a las necesidades de un proyecto.

[Examples](https://getbootstrap.com/docs/4.5/examples/)

[Bootstrap Themes Built & Curated by the Bootstrap Team.](https://themes.getbootstrap.com/)

[Free Bootstrap Themes, Templates, Snippets, and Guides](https://startbootstrap.com/)
