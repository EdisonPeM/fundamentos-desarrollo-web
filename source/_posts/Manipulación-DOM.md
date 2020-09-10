---
title: Manipulación del DOM
categories:
    - Avanzado
---

# Introducción

JavaScript permite modificar el DOM (*Modelo de Objetos del Documento* HTML) de muchas formas, desde agregar y eliminar elementos al documento, modificar los atributos de elementos existentes (incluyendo las clases y estilos del mismo) y agregar funciones que reaccionan ante eventos del usuario.

! Cada elemento del DOM se conoce como **Nodo,** entre los cuales se distinguen los **nodos de elemento** (div, p, h1, etc...) y los **nodos de texto** (directamente el texto)

[Understanding Document Object Model in JavaScript](https://www.javascripttutorial.net/javascript-dom/document-object-model-in-javascript/)

<!-- more -->

# Seleccionar Elementos

Para que Js pueda modificar elementos de DOM debe seleccionarlos primero usando uno de las siguientes funciones del objeto **document**:

```jsx
document.getElementById() // Selecciona un elemento por su **id**

document.getElementsByName() // Selecciona elementos por su atributo **name**
document.getElementsByTagName() // Selecciona elementos por su **etiqueta**
document.getElementsByClassName() // Selecciona elementos por sus **clases**

document.querySelectorAll() // Selecciona elementos usando selectores de CSS
document.querySelector() // Selecciona el primer elemento usando selectores de CSS
```

Usualmente la forma más directa de seleccionar un elemento es por medio de la función `document.getElementById('')` ya que los id son únicos e irrepetibles dentro de un documento, mientras que el resto de funciones nos devuelven una **lista** de todos los elementos que coincidan con la selección.

```html
<section id="banner" class="banner-container bg-dark">
	<!-- content -->
</section>
```

```jsx
let banner = document.getElementById('banner')
console.log(banner)
```

[JavaScript getElementById() - Selecting an Element By Id](https://www.javascripttutorial.net/javascript-dom/javascript-getelementbyid/)

# Modificar Elementos

Cuando seleccionamos un elemento de HTML creamos un objeto de JS, donde los atributos HTML del elemento se pueden acceder a traves de propiedades.

```html
<img id="perfil" class="user-foto flotante" src="images/user.jpg"
			alt="foto de Usuario" title="Esta es la foto de perfil">
```

```jsx
let fotoUsuario = document.getElementById('perfil');
console.log(fotoUsuario.src);
console.log(fotoUsuario.alt);
console.log(fotoUsuario.title);
console.log(fotoUsuario.classList); // para acceder a las clases se usa classList
```

Modificar los atributos de un elemento se puede realizar asignando un nuevo valor al atributo que se desea cambiar:

```jsx
fotoUsuario.src = 'images/userProfile2.jpg';
fotoUsuario.title = 'Hemos cambiado la foto de perfil'
```

## Modificar el contenido

Si se desea modificar el texto contenido de un elemento se puede usar la propiedad **textContent**

```html
<p id="parrafo">
	lorem Ipsum, ...
</p>
```

```jsx
let parr = document.getElementById('parrafo');
console.log(parr.textContent) // lorem Ipsum, ....

parr.textContent = 'Hola Mundo';
```

[JavaScript textContent: Getting or Setting Text for a Node](https://www.javascripttutorial.net/javascript-dom/javascript-textcontent/)

## Modificando Estilos

Js también puede modificar los estilos de un elemento accediendo y modificando el valor del atributo **style,** de esta forma se agregan estilos en linea al elemento:

```jsx
fotoUsuario.style.width = '500px'; // width: 500px;
fotoUsuario.style.height = '300px'; // height: 500px;
```

Sin embargo, la notación de cada propiedad cambia, dado que js no acepta el guion (`-`) en sus nombres, las propiedades se re nombran:

```jsx
fotoUsuario.style.borderRadius = '15px'; // border-radius: 15px;
fotoUsuario.style.objectFit = 'cover'; // object-fit: cover;
```

## Modificando Clases

Por medio de Js se pueden agregar y eliminar clases de css a un elemento, por lo que permite una mejor manipulación de estilos, dejando la responsabilidad de éstos a css.

Para manipular las clases de los elementos se debe acceder a la propiedad **classList** de un elemento, con la cuál podemos usar las siguientes funciones:

```jsx
let navbar = document.getElementById('navbar');

navbar.classList.add('sticky-top') // Permite agregar una clase a un elemento
navbar.classList.remove('transparent') // Permite eliminar una clase del elemento

navbar.classList.contains('validar') // confirma si el elemento tiene la clase
navbar.classList.replace('navbar-dark', 'navbar-light') 
		// Permite remplazar una clase por otraconfirma si el elemento tiene la clase

navbar.classList.toggle('dark-mode') // Elimina o agrega una clase si Existe o No
```

[JavaScript classList: Manipulating CSS properties of an Element](https://www.javascripttutorial.net/javascript-dom/javascript-classlist/)

## Ocultando Elementos

Usando JS también se pueden ocultar y mostrar elementos cambiando el valor de la propiedad **hidden** entre `true` (oculto) y `false` (visible)

```jsx
navbar.hidden = true;
```

Un elemento con el atributo `hidden` (en true) es similar a tener una clase con
 `display: none;`

# Eventos

Un evento es una acción que ocurre en el navegador web, ya sea por la interacción del usuario o por algún otro evento externo a la página. 

Cada evento puede tener un controlador de eventos (*event handler*), el cuál consiste en una función que se ejecutará cuando ocurra el evento.

```html
<button type="button" id="modo-nocturno">Activar Modo Nocturno<button>
```

```jsx
// 1. Se selecciona el elemento al cuál se agregará el *event handler*
let modoNoctBtn = document.getElementById('modo-nocturno');

// 2. Se crea la función que se ejecuta con el evento
function changeMode(){
	document.body.classList.toggle('dark-mode')
}

// 3. Asoiar la función con el evento
modoNoctBtn.addEventListener('click', changeMode);
```

```jsx
// Otra forma de obtener el mismo resultado con menos lineas de código
//	 es utilizando la siguiente notación.
element.addEventListener('event', function(){
	// code block
});
```

[Understanding JavaScript Events](https://www.javascripttutorial.net/javascript-dom/javascript-events/)

## Tipos de Eventos

HTML y JS utilizan un gran conjunto de eventos para agregar interacción a una página web, entre los diferentes eventos que existen podemos encontrar:

- **document**
    - `load`: es el evento principal, ocurre cuando una página termina de cargar.
    - `scroll`: cuando se realiza un scroll en el documento (u otro elemento)
- Mouse:
    - `mousedown`: cuando el usuario hace click (antes de soltarlo)
    - `mouseup`: cuando el usuario suelta el click
    - `click`: cuando el usuario hace click (ocurre después de soltarse)
    - `dblclick`: cuando el usuario hace dobleclick
    - `contextmenu`: cuando se hace click derecho (antes de desplegar el menú)

    Movimiento del Mouse:

    - `mouseover`: cuando el usuario mueve el mouse hacia adentro de un elemento
    - `mouseomove`: cuando el usuario mueve el mouse sobre el elemento (se ejecuta continuamente mientras el mouse esté moviendose)
    - `mouseoout`: cuando el usuario mueve el mouse hacia afuera de un elemento

    [Understanding JavaScript Mouse Events By Examples](https://www.javascripttutorial.net/javascript-dom/javascript-mouse-events/)

- Teclado (usualmente asociados a inputs)
    - `keydown`: cuando se apreta una tecla
    - `keyup`: cuando se apreta una tecla y se suelta
    - `keypress`: cuando se mantiene apretada una tecla

    [JavaScript Keyboard Events Explained](https://www.javascripttutorial.net/javascript-dom/javascript-keyboard-events/)

- Texto:
    - `copy`: cuando el usuario copia un texto
    - `cut`: cuando el usuario corta un texto
    - `paste`: cuando el usuario pega un texto (usualmente inputs)
- Inputs:
    - `focus`: cuando un input está seleccionado para escribir (se ejecuta continuamente mientras esté seleccionado)
    - `input`: cada vez que el usuario ingresa datos a un input
    - `select`: cuando el usuario selecciona un texto (en inputs)
    - `change`: cuando el usuario ingresa cambia un valor de un input
    - `blur`: cuando un input está seleccionado para escribir y se deselecciona

    [JavaScript Focus Events](https://www.javascripttutorial.net/javascript-dom/javascript-focus-events/)

- Formularios:
    - `submit`: Cuando se envía un formulario (antes de enviar los datos)
    - `reset`: cuando se reinicia un formulario.

    [JavaScript Form](https://www.javascripttutorial.net/javascript-dom/javascript-form/)

## Cancelar un evento

Para cancelar un eventoc por defecto, como el `submit` de un formulario, se puede usar la función `preventDefault()` del evento de la siguiente forma

```jsx
function cancelEvent(event) {
    event.preventDefault()
}

form.addEventListener('submit', cancelEvent)
input.addEventListener('paste', cancelEvent)
```

[HTML Event Attributes](https://www.w3schools.com/tags/ref_eventattributes.asp)

[HTML DOM Event Object](https://www.w3schools.com/jsref/dom_obj_event.asp)
