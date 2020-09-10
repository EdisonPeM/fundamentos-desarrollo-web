---
title: Storage
categories:
    - Avanzado
---

# Introducción

Las páginas web suelten utilizar una base de datos para almacenar datos persistentes, sin embargo, estas bases de datos al ser tan grandes se guardan en un servidor, y solemante se puede acceder a ellas a traves de una aplicación del lado del servidor, o un servidor web. De esta forma, la parte visual de una página se comunica con el servidor web y éste se encarga de administrar los datos.

Sin embargo, muchas veces una página requiere guardar datos sin necesitdad de una base de datos, esto se utiliza para manejar algunos estados de las vistas de la página (Como autenticación de usuarios o algunas configuraciones y preferencias de sitio), por lo que se utiliza un almacenamiento más pequeño en cada dispositivo donde el usuario acceda a una página.

Este almacenamiento tiene diferentes formas, entre las cuales podemos encontrar las **Cookies**, que son datos que se envían constantemente a un ***servidor*** (como tokens de autenticación o estadisticas de uso de un sitio), el **LocalStorage** que almacena datos que se mantienen unicamente en el ***navegador***, pero tienen más capacidad (5MB) y no se borran con el tiempo, y el **sessionStorage** el cuál almacena los datos también en el navegador, pero se limpia cada vez que se finaliza una sesión de la página web.

Este tipo de almacenamiento se basa en un sistema de **clave-valor** por lo que los datos (valor) están asociados a una clave.

[HTML Web Storage API](https://www.w3schools.com/html/html5_webstorage.asp)

[Cookies vs localStorage](https://medium.com/datadriveninvestor/cookies-vs-local-storage-2f3732c7d977)

<!-- more -->

# Cookies

Las cookies son datos almacenados por el navegador de forma persistente durante un tiempo de expiración, estos datos se envían continuamente el servidor, se usa generalmente para saber si dos solicitudes provienen del mismo navegador y así, por ejemplo, mantener un inicio de sesión de un usuario. el estado de un carrito de compras, puntajes de juegos o cualquier otra cosa que el servidor deba recordar, tambuén se suelen guardar preferencias y estadisticas del comportamiento del usuario.

[JavaScript Cookies](https://www.w3schools.com/js/js_cookies.asp)

[Document.cookie](https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie)

## Guardar Cookies

Las cookies se guardan en el atributo `**document.cookie`.** para guardar una cookie se debe asignar una cadena de texto con el siguiente formato

- "cookieName=cookieValue;expireDate";

```jsx
document.cookie = "nombre=Edison;expires=30 Aug 2020 12:00:00 UTC";
document.cookie = "apellido=Peñuela;expires=30 Aug 2020 12:00:00 UTC";
```

Cada vez que se asigna un nuevo valor, este no se sobreescribe, sino que se añade a las cookies existentes.

## Leer Cookies

Para leer una cookie se puede llamar al mismo atributo document.cookie donde nos mostrará todas las cookies existentes en una cadena de texto separando las cookies por espacios.

```jsx
console.log(document.cookie) // "nombre=Edison apellido=Peñuela"
```

## Actualizar Cookies

Actualizar una cookie es similar a crearla, esto es, que se guarda el valor en `**document.cookie**`, esta vez, usando la misma clave que se desea sobreescribir

```jsx
document.cookie = "nombre=Edison";
document.cookie = "nombre=Tatiana";
document.cookie = "nombre=BICTIA";
```

## Eliminar Cookies

Para eliminar una cookie, se realiza el mismo proceso de actualización, sin embargo, esta vez se deja el valor vavio:

```jsx
document.cookie = "nombre=";
```

# LocalStorage

El LocalStorage es un almacenamiento existente dentro de un navegador y son persistentes entre diferentes sesiones de navegación, los datos almacenados en localStorage no tienen fecha de expiración, pero sí se pueden limpiar usando js.

Estos datos no se envían al servidor, sino que se utilizan para guardar estados de visualización de la página web en el cliente (navegador), por lo que en diferentes navegadores se pierden estos datos.

El localStorage no debe almacenar datos sensibles como credenciales o tarjetas de crédito, pues estos pueden ser leidos publicamente en el navegador (extenciones, librerías, ataques, etc..)

[Window.localStorage](https://developer.mozilla.org/es/docs/Web/API/Window/localStorage)

## Guardar Datos

Para guardar algún dato en el localStorage se utiliza la función **`setItem`**, indicando la clave y el valor de la siguiente forma:

```jsx
localStorage.setItem('nombre', 'edison');
localStorage.setItem('Apellido', 'peñuela');
localStorage.setItem('curso', 'Fundamentos Web');
localStorage.setItem('estudiantes', '25');
```

Todos los datos almacenados en el localStorage deben ser cadenas de texto.

## Leer Datos

Para leer los datos del logalStorage se utiliza la función `**getItem`** con la clave que deseamos consultar, sin embargo, si no hay un registro con dicha clave, el valor devuelto será `**null**` .

```jsx
let nombre = localStorage.getItem('nombre')
console.log(nombre) // "edison"

let apellido = localStorage.getItem('apellido')
console.log(apellido) // null

apellido = localStorage.getItem('Apellido')
console.log(apellido) // "peñuela"
```

Las claves del localStorage son únicas y **case sensitive**, es decir, no es la mima clave en minusculas que en mayusculas.

Todos los datos guardados en el storage se almacenan como cadenas de texto, por lo que para trabajar con números es necesario convertilos de texto a numero

```jsx
let estudiantes = 0;
let estudiantesTexto = localStorage.getItem('estudiantes')
// Se debe validar que no sea nulo o cadena vacia para poder convertirlo
if(estudiantesTexto !== null && estudiantesTexto !== ''){
	estudiantes = parseInt(estudiantesTexto)
}
console.log(estudiantes) // 25
```

## Actualizar Datos

Para actualizar una clave, se utiliza la misma función `**setItem**`, si la clave ya existe en el storage, su valor se sobreescribe (actualiza) con el nuevo valor:

```jsx
// Se guarda la calve tema por primera vez
localStorage.setItem('tema', 'storage')
let tema = localStorage.getItem('tema')
console.log(tema) // "storage"

// se actualiza el valor de la misma clave
localStorage.setItem('tema', 'cookies')
tema = localStorage.getItem('tema')
console.log(tema) // "cookies"
```

## Eliminar Datos

Si se desean eliminar los datos del Storage hay dos opciones, se pueden eliminar claves particulares o todas las claves, para eliminar un dato se utiliza el método `**removeItem`** con la clave que se desea borrar del storage;

```jsx
localStorage.removeItem("curso");
let curso = localStorage.getItem('curso');
console.log(curso) // null
```

Cuando se elimina una clave, al querer obtener su valor, el resultado será nulo.

Para eliminar todo el Storage se utiliza la función `**clear**`, de esta forma se eliminarán todas las claves con sus respectivos valores

```jsx
localStorage.clear();
// El atributo length permite ver cuántas claves tiene el Storage
console.log(localStorage.length) // 0
```

# SessionStorage

El SessionStorage es un almacenamiento que solamente existe durante una sesión de navegación, es decir, que cuando se cierran las pestañas o ventanas de la página (incluyendo sub páginas) se borran los datos.

El Session Storage se mantiene cuando se navega entre varias págnas del mismo dominio (Subpaginas) o cuando se refresca la página (*F5*).

Se suele utilizar para guardar estados para una sesión, como cuál es la vista actual, o para almacenar los datos de los campos de formularios en forma de autoguardado temporal.

```jsx
let formularioContacto = document.form['contactenos']
let correo = formularioContacto['correo'].value
let asunto = formularioContacto['asunto'].value
let mensaje = formularioContacto['mensaje'].value
```

[Window.sessionStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/sessionStorage)

## Guardar Datos

Para guardar algún dato se utiliza el objeto sessionStorage y la función **`setItem`**, indicando la clave y el valor de la siguiente forma:

```jsx
sessionStorage.setItem('correoForm', correo)
sessionStorage.setItem('asuntoForm', asunto)
sessionStorage.setItem('mensajeForm', mensaje)
```

Todos los datos almacenados en el localStorage deben ser cadenas de texto.

## Leer Datos

Para leer los datos del SessionStorage se utiliza la función `**getItem`** con la clave que deseamos consultar, sin embargo, si no hay un registro con dicha clave, el valor devuelto será `**null**` .

```jsx
formularioContacto['correo'].value = sessionStorage.getItem('correoForm')
formularioContacto['asunto'].value = sessionStorage.getItem('asuntoForm')
formularioContacto['mensaje'].value = sessionStorage.getItem('mensajeForm')
```

Las claves del sessionStorage son únicas y **case sensitive**, es decir, no es la mima clave en minusculas que en mayusculas, los datos también siempre se guardan en forma de cadenas de texto.

## Actualizar Datos

Para actualizar una clave, se utiliza la función `**setItem**`, si la clave ya existe en el storage, su valor se sobreescribe (actualiza) con el nuevo valor:

```jsx
let mensajeInput = formularioContacto['mensaje']
// El sessionStorage se actualizará cada vez que el usuario ingrese algún dato
mensajeInput.addEventListener('input', function(){
	sessionStorage.setItem('mensajeForm', this.value)
});
```

## Eliminar Datos

Si se desean eliminar los datos del Storage hay dos opciones, se pueden eliminar claves particulares o todas las claves, para eliminar un dato se utiliza el método `**removeItem`** con la clave que se desea borrar del storage;

```jsx
sessionStorage.removeItem('asuntoForm')
let asunto = localStorage.getItem('asuntoForm');
console.log(asunto) // null
```

Cuando se elimina una clave, al querer obtener su valor, el resultado será nulo.

Para eliminar todo el Storage se utiliza la función `**clear**`, de esta forma se eliminarán todas las claves con sus respectivos valores

```jsx
sessionStorage.clear();
// El atributo length permite ver cuántas claves tiene el Storage
console.log(sessionStorage.length) // 0
```

# Almacenamiento de Objetos

Dado que los diferentes tipos de almacenamiento guardan cadenas de texto, no es posible guardar objetos directamente, sin embargo se pueden utilizar funciones del objeto **`JSON`** para manejar este tipo de datos.

## Guardar Objetos

Para guardar objetos se debe convertir este a una cadena de texto usando la función `JSON.stringify()` y esta cadena de texto sí se puede almacenar

```jsx
let datosObj = {
	correo: formularioContacto['correo'].value,
	asunto: formularioContacto['asunto'].value,
	mensaje: formularioContacto['mensaje'].value
}

let datosTexto = JSON.stringify(datosObj)
localStorage.setItem('datos', datosTexto)
```

## Leer Datos

Para leer los objetos, por el contrario, se debe convertir la cadena de texto a un Objeto, esto se puede realizar con la función `JSON.parse()`.

```jsx
let datosTexto = localStorage.getItem('datos')
let datosObj = JSON.parse(datosTexto)
```

[Trabajando con JSON](https://developer.mozilla.org/es/docs/Learn/JavaScript/Objects/JSON)
