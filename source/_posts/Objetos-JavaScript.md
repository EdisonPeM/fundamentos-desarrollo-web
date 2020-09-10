---
title: Objetos JavaScript
categories:
    - Avanzado
---

# Introducción

Javascript es un lenguaje multiparadigma, entre los que se encuentra que es **basado en objetos (*prototipos*)**, esto significa que todo en javascript es un **objeto**, cada objeto es simplemente una colección de **propiedades** y **funciones**. Se puede acceder a dichas propiedades o funciones a través del identificador del objeto, un punto y el identificador de la propiedad o función.

```jsx
// console es el objeto, log es una función de dicho objeto
console.log('Hola Mundo')

// document es el objeto, write es una función de dicho objeto
document.write('<h1>Hola Mundo</h1>')
```

<!-- more -->

# Number

Cuando definimos una **variable numérica** en nuestro código, se pueden utilizar una una serie de funciones de Number a las que podemos acceder agregando un punto a nuestra variable seguido del nombre de la función.

```jsx
let num = 1024.234567;

**console.log(num.toString()); // "1024.234567"
**console.log(num.toFixed(2)); // "1024.23"
**console.log(num.toExponential()); // "1.024234567e+3"
```

Las funciones anteriores convierten el **numero a texto** en diferentes formatos, sin embargo, existen dos funciones que permiten convertir **texto a numero**, estas funciones no están asociadas a ningún objeto.

```jsx
let textNum = "1234.54"

console.log(parseInt(textNum)); // 1234
console.log(parseFloat(textNum)); // 1234.54
console.log(isNaN(textNum)) // false 
```

[JavaScript Number Methods](https://www.w3schools.com/js/js_number_methods.asp)

# Math

Math es un objeto de Js que tiene incorporada una serie de constantes y funciones matemáticas.

```jsx
console.log(Math.PI) // 3.141592653589793
console.log(Math.E) // 2.718281828459045

console.log(Math.sin(Math.PI/2)) // 1
console.log(Math.cos(Math.PI)) // -1

console.log(Math.random()) // random number between (0,1)
```

[Math](https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/Math)

# String

Cuando definimos una **variable de texto** en nuestro código, se pueden utilizar una una serie de funciones y atributos de String a las que podemos acceder agregando un punto a nuestra variable seguido del nombre de la función.

```jsx
let mensaje = "Bienvenidos al Curso de Fundamentos Web";

console.log(mensaje.length); // 39

console.log(mensaje.toLowerCase()); // "bienvenidos al curso de fundamentos web"
console.log(mensaje.toUpperCase()); // "BIENVENIDOS AL CURSO DE FUNDAMENTOS WEB"
```

## SubString

Se conoce como subString a un string dentro de string, esto es, una texto que se puede sacar de otro texto, ya sean palabras completas, caracteres o secuenca de caracteres.

```jsx
console.log(mensaje); // "Bienvenidos al Curso de Fundamentos Web"

// Buscar la posición de un caracter o string 
console.log(mensaje.indexOf('B')); // 0
console.log(mensaje.indexOf('b')); // 38
console.log(mensaje.indexOf('Fundamentos')); // 24

// Seleccionar caracteres según la posición indicada
console.log(mensaje.charAt(1)); // "i"
console.log(mensaje.charAt(2)); // "e"

// Seleccionar subString (posiciónInicial, longitud)
console.log(mensaje.substr(24, 11)); // "Fundamentos"
```

## Split

Se puede convertir una cadena de texto a un arreglo usando la funcion split de String, en este caso se utiliza un **separador**

```jsx
let mensaje = "Bienvenidos al Curso de Fundamentos Web";
console.log(mensaje.split(' ')); 
// ["Bienvenidos", "al", "curso", "de", "Fundamentos", "Web"]
```

[JavaScript String Methods](https://www.w3schools.com/js/js_string_methods.asp)

# Array

Los arreglos son objetos que nos permiten crear **listas** de elementos, dichos elementos pueden ser números, cadenas de texto, booleanos, también se pueden crear listas de objetos así como listas de listas.

La creación de una lista en Js se realiza con llaves cuadradas `[ ]`. Para agregar elementos a una lista se utiiliza la función **push** con el valor que se desea agregar. Para eliminar elementos de una lista se puede utilizar la función **pop**, en este caso eliminará el último valor de la lista.

```jsx
let lista = [];

// Agrega un elemento al final de la lista
lista.push("Ejemplo")
console.log(lista)

// Elimina el último elemento de la lista
lista.pop()
console.log(lista)
```

También se pueden crear listas con valores iniciados

```jsx
let opciones = ["home", "about", "contact"];

// length Muestra la longitud de la lista
console.log(lista.length)

// Buscar la posición de un elemento en lista
console.log(lista.indexOf("about")); // 1

// Acceder a una posición de la lista
console.log(lista[0])
console.log(lista[1])
console.log(lista[2])

// Modificar un elemento particular de la lista
lista[1] = "services"
console.log(lista)
```

## Join

Los arreglos se pueden convertir en una cadena de texto, uniendo cada elemento de la lista con la función **join**, indicando un separador.

```jsx
let palabrasMensaje = ["Bienvenidos", "al", "curso", "de", "Fundamentos", "Web"];
console.log(palabrasMensaje.join(' '));
```

[JavaScript Arrays](https://www.w3schools.com/js/js_arrays.asp)

---

# Objetos Propios

Adicional a los objetos existentes en JS podemos crear nuestros propios objetos usando corchetes `{ }` y asociarlo a una variable.

```jsx
let myObj = {}
```

Tanto los atributos como las funciones asociadas a un objeto se les conoce como propiedades, estas propiedades constan de una clave y un valor separadso por dos punto (`:`) y cada propiedad (clave-valor) debe ir separada por coma (`,`).

Para un objeto cada clave es única e irrepetible y cada valor puede ser de cualquier tipo de dato (tanto texto, numero, booleano, como listas y funciones).

```jsx
var persona = {
  nombre: 'John',
	apellido: 'Doe',
  edad: 32,
	casado: false,
  intereses: ['música', 'esquí'],
  saludar: function() {
    alert('Hola, Soy '+ this.nombre[0] + ' ' + this.nombre[1] + '. ');
  }
};
```

# JSON

Un **JSON** (*JavaScript Object Notation*) es un formato de archivos de texto que utiliza la notación de Objetos de Javascript para describir los datos transmitidos entre aplicaciones web.

Estos archivos tienen la extención `.json` y tienen la estructura clave valor, donde la clave debe ir dentre de comillas dobles (`""`), igualmente las propiedades (datos) van separados por coma (`,`).

```json
{
	"menu": {
	  "id": "file",
	  "value": "File",
	  "popup": {
	    "menuitem": [
	      {"value": "New", "onclick": "CreateNewDoc()"},
	      {"value": "Open", "onclick": "OpenDoc()"},
	      {"value": "Close", "onclick": "CloseDoc()"}
	    ]
	  }
	}
}
```

Este formato puede existir fuera de Javascript y pueden ser interpretados por diferentes lenguajes de programación.

[Trabajando con JSON](https://developer.mozilla.org/es/docs/Learn/JavaScript/Objects/JSON)
