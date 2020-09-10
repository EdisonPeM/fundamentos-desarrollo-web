---
title: Javascript
categories:
    - Avanzado
---

# Introducción

JavaScript es un lenguaje de programación y de scripting multiplataforma, multiparadigma y de alto nivel, que es interpretado en un **navegador web** o en un entorno de ejecución como **nodejs**.

Un Script se trata de una secuencia de comandos o pequeñas funcionalidades que se interpretan y ejecutan en un ambiente. En páginas web, estos scripts pueden agregar dinamismo al documento y aportar respuesta a la interacción del usuario, para ello JavaScript proporciona métodos que permiten modificar el DOM (Document Object model), manipular datos, utilizar el API de Html y muchas más funcionalidades.

Por otra parte, usando nodejs se puede interpretar el lenguaje del lado del servidor, permitendo crear aplicaciones con un API para comunicarse con otras aplicaciones, así como la posibilidad de conectarse con una base de datos para manipular y procesar la información con alguna lógica de negocio.

<!-- more -->

## Historia

JavaScript nace durante la década de los años 90, durante el surgimiento de sofisticadas aplicaciones web acompañadas de una lenta velocidad de navegación, esto originó la necesidad de concebir un lenguaje de programación que se ejecutara en el mismo navegador, con el objetivo de optimizar el tiempo de respuesta de los usuarios;

Un programador de Netscape llamado **Brendan Eich** pensó que podría solucionar este problema adaptando tecnologías existentes al navegador **Netscape Navigator 2.0**, que iba a lanzarse en 1995. Inicialmente lo llamó **LiveScript**.

Posteriormente, Netscape firmó una alianza con Sun Microsystems para el desarrollo del nuevo lenguaje de programación el cuál cambió su nombre por el de JavaScript. La razón del cambio de nombre fue exclusivamente por marketing, ya que Java era la palabra de moda en el mundo informático y de Internet de la época. Varios lenguajes de programación como JScript o VBScript surgieron por ese entonces, sin embargo Javascript prevaleció ante los demás.

### Estandar

Posteriormente, en el año de 1997, la empresa Netscape estandarizó el lenguaje JavaScript en su versión 1.1. El organismo **ECMA** (*European Computer Manufacturers Association*) y el comité TC39 definieron que estandarizar era la mejor decisión, por lo que se inauguró el término **ECMAScript** para el estándar del lenguaje.

En Diciembre de 1999 sale la tercera versión de ECMAScript y no es hasta en Diciembre de 2009 que sale la quinta versión (la 4ta fue abandonada) Ese mismo año nace nodejs. En junio de 2015 nace **ECMAScript 6**, esta actualización trajo cambios significativos en el lenguaje para la escritura de aplicaciones complejas, la versión actual es ECMAScript 10.

![Untitled.png](Untitled.png)

## JavaScript (Js) No es Java

![java-y-javascript-no-son-lo-mismo.jpg](java-y-javascript-no-son-lo-mismo.jpg)

Java es un lenguaje de programación orientado a objetos que se incorporó al ámbito de la informática en los años noventa. La idea de Java es que pueda realizarse programas con la posibilidad de ejecutarse en cualquier contexto, en cualquier ambiente, siendo así su portabilidad uno de sus principales logros.

JavaScript y Java son similares en algunos aspectos, pero fundamentalmente diferentes en otros. El lenguaje JavaScript se parece a Java pero no tiene el tipo estático (static) de Java, ni tiene un tipado fuerte. JavaScript usa la mayoría de la sintaxis de expresiones de Java, convenciones de nombrado, y las construcciones básicas de control de flujo, razón adicional por la cual se le cambió el nombre del original LiveScript a JavaScript.

[1.2. Breve historia (Introducción a JavaScript)](https://uniwebsidad.com/libros/javascript/capitulo-1/breve-historia)

[Introducción](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Introducci%C3%B3n)

[Introducción a Javascript](https://desarrolloweb.com/articulos/introduccion-javascript.html)

# Incorporación

Para incorporar código javascipt a una página web se puede realizar de varias formas.

## Interno

Usando la etiqueta `<script>` al final del documento:

```html
<html>
<head></head>
<body>

   <script>
       // Código Js
    </script>
</body>
</html>
```

## Externo

Usando un archivo con extensión **.js** en donde tengamos el código, este archivo se agrega al documento con la etiqueta `<script>` paro usando el atributo `src`

```html
<html>
<head></head>
<body>

   <script src="filePath"></script>
</body>
</html>
```

Donde `href="filePath"` hace referencia al archivo .js

### *FilePath*

Se le conoce como **FilePath** a la ubicación de un archivo dentro de un equipo, y existen dos formas de ubicar un archivo, con una “**ruta relativa**” y una “**ruta absoluta**”.

- **Ruta Absoluta**: Es la ubicación exacta de un archivo dentro de un pc
    - en Windows sería: `"C:\\users\Edison\Escritorio\miPaginaWeb\js\script.js"`
    - mientras que en Linux podría ser: `"/home/edison/Escritorio/miPaginaWeb/js/script.js"`

También se le llama ruta absoluta a las rutas de internet (URL)

- **Ruta Relativa**: Se refiere la ubicación de un archivo respecto a otro, para esto se deben seguir las siguientes reglas:
    - **Carpeta Actual**: usando un punto (`.`) podemos referirnos a la carpeta actual, por ejemplo si deseamos agregar una imagen dentro de nuestro `index.html` podemos usar la ruta: `"./js/script.js"`.
    - **Carpeta Superior**: usando punto punto (`..`) Diferente de dos puntos (`:`), podemos referirnos a una carpeta superior y luego ubicar un archivo, por ejemplo si deseamos cargar una imagen desde un documento html que se encuentra en una subcarpeta, se podría usar la ruta `"../js/script.js"`

El filepath es **casesensitive,**  esto significa que hace distinción entre mayusculas y minusculas, siempre se deben indicar el nombre de las carpetas o archivos **exactamente** igual a como a parecen en el explorador de archivos.

# Sintaxis

Como todo lenguaje de programación, javascript está basado en **sentencias**, cada sentencia representa una instrucción o un conjunto de instrucciones a la maquina (o al navegador).

Las sentencias están separadas entre sí por **punto y coma** (Sin embargo no son obligatorias cuando están separadas en lineas de código independientes).

JavaScript es **case-sensitive**, lo que significa que distingue mayúsculas y minúsculas y utiliza el conjunto de caracteres Unicode. Sin embargo para los **identificadores** (nombre de variables, funciones o propiedades), se deben seguir las siguients reglas:

- El primer carácter debe ser una letra (minuscula).
- Los caracteres posteriores pueden ser letras, dígitos o guiones bajos (_).
- No se permiten espacios, guiones u otros simbolos especiales en dichos nombres.
- Para nombres compuestos se utiliza **camelCase**, es decir la primera letra de la segunda palabra en adelante comienza con mayuscula y el resto en minuscula.
- No se pueden utilizar **palabras reservadas**.

## Comentarios

Para agregar comentarios dentro del código se utilizan dos metodos:

```jsx
// comentario en una sola línea

/* este es un comentario 
   multilínea
 */
```

# Variables

Una variable representa un espacio en la memoria de un ordenador, donde almacena información o datos (**valores**) y se acceden a éstos por medio de un **identificador.**

El nombre de la variable es la forma usual de referirse al valor almacenado, esta separación entre nombre y contenido permite que el nombre sea usado independientemente de la información exacta que representa.

Para **definir** nuevas variables, se utilizan las palabras reservadas seguido del identificador o nombre de la variable:

- `let`: para crear variables cuyo valor puede cambiar en tiempo de ejecución.
- `const`: para variables cuyo valor es inmutable en tiempo de ejecución.

Otras formas aceptadas pero ya **NO** se recomiendan son:

- `var`: es una forma de definir variables con un alcance local más amplio (a nivel de funciones), mientras que `let` define variables con un alcance a nivel de bloques (condiciones, ciclos, etc)
- **Sin palabra reservada**: Las variables creadas de esta forma tienen un alcance global sin importar donde son definidas.

Para **asignar** un valor se utilizar el simbolo `=` seguido del valor correspondiente según los diferentes tipos de datos o el resultado de una operación.

## Tipos de Datos

JavaScript cuenta con 6 diferentes tipos de datos primitivos: 

- **Numeros (Number):** Consisten en números enteros o flotantes, Por ejemplo: `42` o `3.14159`.
    - **infinity:** Infinito es un valor numerico que representa 1/0.
    - **NaN (Not a Number):** Este es un valor resultante de convertir un texto con letras en número.
- **Cadenas de Texto (String):** Consiste en una secuencia de caracteres, las cadenas de texo se definen entre comillas sencillas o comillas dobles, Por ejemplo `'Hola Mundo'`
- **Booleano (Boolean):** Consiste en valores binarios donde valores `true` y `false`.

```jsx
const pi = 3.1415
let foo = "Hola Mundo!"
let bar = false
```

---

- **undefined:** Este es el tipo de dato de una variable sin valor.
- **null**. Una palabra clave especial que denota un valor nulo (Propiedades no existentes de un objeto existente).

![Untitled1.png](Untitled1.png)

---

- **Objeto (Object)**: Todos los demás elementos de Js son objetos (los objetos de js tienen atributos y funciones)
    - **Array:** Es un tipo de objeto que representa una lista de elementos.
    - **Date:** Es un tipo de objeto ****para trabajar con fechas.
    - **Math**: Es un tipo de objeto con funciones matemáticas.

[Gramática y Tipos](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Grammar_and_types#Basics)

[W3Schools JS Exercise](https://www.w3schools.com/js/exercise_js.asp?filename=exercise_js_variables1)

## Mostrar en consola

Para visualizar el valor de una variable o el resultado de una operación se utiliza la función:

```jsx
console.log()
```

Donde dentro del paréntesis va lo que se va a mostrar en pantalla, ya sean datos o variables

```jsx
console.log(5)
console.log("Hola Mundo!")

console.log(pi)
console.log(foo)
```

También se puede utilizar para mostrar el resultado de una operación.

[JavaScript Debugging](https://www.w3schools.com/js/js_debugging.asp)

# Operaciones

## Aritméticas

Javascript soporta el siguiente conjunto de operaciones entre números:

- `+`: Suma
- `-`: Resta
- `*`: Multiplicación
- `/`: Division
- `**`: Potencia (ES2016)
- `%`: Modulo (Resto de la division)

```jsx
let x = 10
let y = 11

console.log(x + y)
console.log(x - y)
console.log(x * y)
console.log(x / y)
```

[Expresiones y operadores](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Expressions_and_Operators#Operadores_aritm%C3%A9ticos)

[JavaScript Arithmetic](https://www.w3schools.com/js/js_arithmetic.asp)

[W3Schools JS Exercise](https://www.w3schools.com/js/exercise_js.asp?filename=exercise_js_operators1)

### Incremento

La operación de incremento se utiliza para aumentar el valor de una variable numérica. Este incremento tiene varias formas de implementación:

- Una unidad a la vez, se utiliza el operador `++`

    ```jsx
    let miNumero = 3;
    console.log(miNumero) // 3
    miNumero++;
    console.log(miNumero) // 4
    ```

- Valores personalizados, se utiliza el operador `+=`

    ```jsx
    let miNumero = 3;
    console.log(miNumero) // 3
    miNumero += 5;
    console.log(miNumero) // 8
    ```

Otros operadores son:

- `--` para decremento de a una unidad a la vez
- `-=` para decremento con valores personalizados

[Expresiones y operadores](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Expressions_and_Operators#Operadores_de_asignaci%C3%B3n)

[JavaScript Assignment](https://www.w3schools.com/js/js_assignment.asp)

## Strings

Las cadenas de texto se pueden unir usando la operación **concatenación**, la cuál se realiza con el símbolo `+`

```jsx
let foo = 'hola '
let bar = 'mundo'

console.log(foo + bar) // 'holamundo'
```

[Expresiones y operadores](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Expressions_and_Operators#Operadores_de_cadenas_de_caracteres)

### String + Number

Una característica de Javascript es que tiene un tipado dinámico, por lo que las variables pueden tener cualquier tipo de dato y este puede variar en tiempo de ejecución.

Al realizar operaciones entre diferentes tipos de datos se pueden dar diferentes resultados

```jsx
let numero = 2
let texto = 'hola'

// La operación suma se comporta como concatenación
console.log(numero + texto) // '2hola'
console.log(texto + numero) // 'hola2'

// Otras operaciones comportan de foma aritmética
console.log(numero - texto) // NaN
console.log(texto - numero) // NaN
```

Sin embargo, si el texto consta solamente de caracteres numéricos, las operaciones diferentes a la suma sí se podrán realizar.

```jsx
let numero = 2
let texto = '10'

// La operación suma se comporta como concatenación
console.log(numero + texto) // '210'
console.log(texto + numero) // '102'

// Otras operaciones comportan de foma aritmética
console.log(numero - texto) // -18
console.log(texto - numero) //  18
```

---

## Lógicas

Las operaciones lógicas son operaciones que se realizan entre **booleanos** y se implementan con los siguientes símbolos:

- `&&` Operación **AND**
- `||` Operación **OR**
- `!` Operación **NOT**

```jsx
let a = true
let b = false
console.log(a || b) // true
console.log(a && b) // false
console.log(!a) // false
```

### Tabla de Verdad

**A**

true

true

false

false

**B**

true

false

true

false

**A && B**

true

false

false

false

**A || B**

true

true

true

false

[Expresiones y operadores](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Expressions_and_Operators#Operadores_l%C3%B3gicos)

## Comparaciones

Los operadores de comparación se utilizan en declaraciones lógicas para determinar la igualdad o diferencia entre variables o valores, el resultado de una comparación es un valor booleano (**true** / **false**).

- `==`: Igualdad
- `===`: Igualdad estricta
- `>`: Mayor qué
- `>=`: Mayor **o** igual ****que.

```jsx
console.log(8 == 5)
console.log(8 > 5)
console.log(8 >= 5)
```

- `!=`: Diferencia
- `!==`: Diferencia Estricta
- `<`: Menor que
- `<=`: Menor **o** igual que

```jsx
console.log(8 != 5)
console.log(8 < 5)
console.log(8 <= 5)
```

[Expresiones y operadores](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Expressions_and_Operators#Operadores_de_comparaci%C3%B3n)

[JavaScript Comparison and Logical Operators](https://www.w3schools.com/js/js_comparisons.asp)

[W3Schools JS Exercise](https://www.w3schools.com/js/exercise_js.asp?filename=exercise_js_comparisons1)

# Condicionales

Las declaraciones condicionales se utilizan para realizar diferentes acciones basadas en diferentes condiciones. Una **condición** es algún valor booleano, ya sea:

- Variable booleana
- Resultado de una comparación
- Resultado de una operación booleana (entre variables y/o comparaciones).

Las condicionales se declaran usando la sentencia **`if`** y se puede complementar con las sentencias `**else**` y `**else if**`. y las instrucciones para cada caso se definen en un **bloque de código**.

```jsx
if (condition) {
  // bloque de código si la condición se cumple
}
```

```jsx
if (condition) {
  // bloque de código si la condición se cumple
} else {
  // bloque de código si la condición NO se cumple
}
```

```jsx
if (condition) {
  // bloque de código si la condición se cumple
} else if (otherCondition){
  // bloque de código si la condición NO se cumple pero sí se cumple la segunda
} else {
  // bloque de código si Ninguna condición se cumple
}
```

Se pueden evaluar variables como condiciones, en este caso los siguientes valores se evalúan como falso (también conocidos como valores **falsy**):

- `false`: Variable booleana con valor false.
- `0`: Variable numérica con valor 0.
- `NaN`: Variable numérica con valor NaN.
- `""`: Variable de texto con una cadena vacía como valor.
- `undefined`: Variable sin asignar.
- `null`: Elemento no existente.

Los demás valores serán considerados verdaderos (**truthy**).

[Control de flujo y manejo de errores](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Control_de_flujo_y_manejo_de_errores#Sentencia_if...else)

[JavaScript if else else if](https://www.w3schools.com/js/js_if_else.asp)

[W3Schools JS Exercise](https://www.w3schools.com/js/exercise_js.asp?filename=exercise_js_conditions1)

# Ciclos

Los ciclos ofrecen diferentes formas de ejecutar un bloque de código repetidamente.

## While Loop

Los ciclos while se ejecutan mientras que una condición sea verdadera

```jsx
while(condition){
	// bloque de código a ejecutar repetidamente
}
```

Es importante que la condición cambie en el tiempo para finalizar el ciclo, de lo contrario se ejecutará para siempre (**Loop infinito**) y bloqueará la página.

[Bucles e iteración](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Bucles_e_iteraci%C3%B3n#sentencia_while)

[JavaScript while Loop](https://www.w3schools.com/js/js_loop_while.asp)

[W3Schools JS Exercise](https://www.w3schools.com/js/exercise_js.asp?filename=exercise_js_loop_while1)

## Do-While Loop

Un ciclo do-while es similar al ciclo while, sin embargo en éste el bloque de código se ejecuta al menos una vez sin importar la validez de la condición.

```jsx
do {
	// bloque de código a ejecutar repetidamente
} while(condition);
```

[Bucles e iteración](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Bucles_e_iteraci%C3%B3n#sentencia_do...while)

## For Loop

Los ciclos for se utilizan cuando se desea ejecutar algo una cantidad de veces predefinidas, para ello utilizan una variable numérica que irá incrementando en cada ciclo hasta llegar a un valor específico.

```jsx
let cantCiclos = 10;
for(let i = 0; i < cantCiclos; i++){
		// bloque de código a ejecutar 10 veces
}
```

Los ciclos for se utilizan frecuentemente para recorrer una lista de elementos.

[Bucles e iteración](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Bucles_e_iteraci%C3%B3n#sentencia_for)

[JavaScript for Loop](https://www.w3schools.com/js/js_loop_for.asp)

[W3Schools JS Exercise](https://www.w3schools.com/js/exercise_js.asp?filename=exercise_js_loops1)

## Break / Continue

Si se desea romper un ciclo a la fuerza se puede utilizar la palabra reservada **break.**

```jsx
for(let i = 0; i < 10; i++) {
	if(i == 6){
		break;
	}
	console.log(i);
}
```

```jsx
> 0
> 1
> 2
> 3
> 4
> 5
```

Si se desea saltar una iteración del ciclo se utiliza la palabra reservada **continue**

```jsx
for(let i = 0; i < 10; i++) {
	if(i == 6){
		continue;
	}
	console.log(i);
}
```

```jsx
> 0
> 1
> 2
> 3
> 4
> 5
> 7
> 8
> 9
```

[JavaScript Break and Continue](https://www.w3schools.com/js/js_break.asp)

[Bucles e iteración](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Bucles_e_iteraci%C3%B3n#sentencia_break)

# Funciones

Una función es un conjunto de sentencias (bloque de código) que realizan una tarea o calculan un valor. Las funciones se almacenan en memoria y solo se ejecutan cuando "algo" lo invoca.

## Invocar Funciones

Para invocar una función se debe escribir el identificador de la función seguido de paréntesis `()`.

```jsx
alert()
prompt()
confirm()
```

También pueden estar asociadas a un objeto, en este caso se debe escribir el identificador del objeto seguido de un punto (.) y el identificador de la función junto con los paréntesis `()`.

```jsx
console.log()
console.clear()
document.write()
```

## Parámetros / Argumentos

Muchas veces las funciones requieren un valor para funcionar (**parámetro**), o para cambiar su comportamiento, este valor se escribe dentro de los paréntesis (**argumento**).

```jsx
console.log('Este es un mensaje en consola')
alert('Este es un mensaje de alerta')
confirm('Esta es una pregunta de confirmación')
```

Una función puede tener más de un parámetro, en este caso se utilizan comas para separar los valores.

```jsx
console.log('Hola', 'Mundo', 'Este es', 'El curso de', 'Fundamentos')
```

## Retornos

Algunas funciones pueden devolver un valor según el tipo de función, este valor se puede almacenar en una variable para utilizarla más adelante.

```jsx
let nombre = prompt('Ingresa tu nombre')
alert('Bienvenido ' + nombre)
```

Los retornos de funciones se pueden utilizar para controlar el flujo de un algoritmo (condición, ciclo, etc.)

```jsx
let continuar = true;
let iteracion = 0;
while(continuar){
	iteracion++
	alert('Esta es la iteracion '+iteracion);
	continuar = confirm('Desea continuar?');
}
```

## Definir Funciones

Para definir una función propia se utiliza la palabra reservada `function` seguido del identificador de la función con la siguiente estructura:

```jsx
function miFuncion(){
	// Código a ejecutar cuando la función sea invocada
}
```

Si se desea agregar parámetros a la función se escribe un identificador dentro del paréntesis (la cantidad de identificadores como parámetros), estos identificadores se podrán usar como **variables** **dentro** de la función.

```jsx
	function saludar(mensaje){
		// Código a ejecutar cuando la función sea invocada
		alert('Hola, ' + mensaje)
	}
```

Para agregar retornos se utiliza la palabra clave `return` seguido del valor que se desea retornar.

```jsx
function sumar(num1, num2){
	return num1 + num2
}

function restar(num1, num2){
	let resta = num1 + num2
	return resta
}
```

Todas las variables creadas dentro de una función no "existen" fuera de ella.
