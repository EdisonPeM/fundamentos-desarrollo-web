---
title: Validación de Formularios
categories:
    - Avanzado
---

# Validación HTML

Los formularios tienen varias formas de validar la entrada de un usuario, desde tipos de inputs, atributos de validación de HTML, hasta funciones con Js.

<!-- [**Formularios**](/fundamentos-desarrollo-web/2020/09/08/CONTENIDO/Formularios) -->

[Tipos de input de HTML5](https://developer.mozilla.org/es/docs/Learn/HTML/Forms/Tipos_input_HTML5)

[Validación de formularios de datos](https://developer.mozilla.org/es/docs/Learn/HTML/Forms/Validacion_formulario_datos)

<!-- more -->

## Campos Obligatorios

Usando el atributo `require` en algún input (select o textarea) un campo se convierte en **obligatorio** para el usuario, esto significa que deberá completar algún dato y no dejarlo vacio.

```jsx
<div class="form_field">
    <label for="userName">Usuario</label>
    <input id="userName" name="userName" required>
</div>
<div class="form_field">
    <label for="password">Contraseña</label>
    <input type="password" id="password" name="password" required>
</div>
```

## Rango Numérico

Para números se puede limitar un rango con los atributos:

- `min`: limita el valor mínimo que puede ingresar el usuario
- `max`: limita el valor maximo que puede ingresar el usuario

```html
<div class="form_field">
	<label for="filtro">Filtrar cantidad: </label>
	<input type="number" id="filtro" name="filtro" min="0" max="100">
</div>
```

Esta validación se realiza solamente con campos con entrada numerica y fechas:

```jsx
<input type="number" id="..." name="..." min="0" max="1000000">
<input type="range"  id="..." name="..." min="-10" max="-10" step="2">

<input type="date"           id="..." name="..." min="2020-07-30">
<input type="datetime-local" id="..." name="..." max="1994-11-05T08:15">
<input type="month"          id="..." name="..." min="2021-06">
```

## Longitud de Entrada

Se puede validar la longitud de la entradad el usuario en campos de texto usando atributos;

- `minlength`: designa el tamaño minimo de caracteres admitidos
- `maxlength`: designa el tamaño máximo de caracteres admitidos

```html
<div class="form_field">
    <label for="password">Contraseña</label>
    <input type="password" id="password" name="password" minlength="8">
</div>
```

Esta validación se hace solamente sobre campos donde el usuario puede ingresar texto como:

```jsx
<input type="text"     id="..." name="..." minlength="X" maxlength="Y">
<input type="search"   id="..." name="..." minlength="X" maxlength="Y">
<input type="password" id="..." name="..." minlength="X" maxlength="Y">
<input type="email"    id="..." name="..." minlength="X" maxlength="Y">
<input type="url"      id="..." name="..." minlength="X" maxlength="Y">
<input type="tel"      id="..." name="..." minlength="X" maxlength="Y">
<textarea id="..." name="..." minlength="X" maxlength="Y"></textarea>
```

## Formato

HTML permite hacer validaciones de formato, internamente utiliza esta validación para los campos:

- `<input type="email">`: Evalua que tenga el formato ***texto*@*texto***, donde texto puede ser cualquier cosa
- `<input type="url">`: Valida que el formato sea **http://*texto*** o **https://*texto*** donde texto puede ser cualquier cosa.

Adicionalmente a estas validaciones se puede establecer un formato específico para cada campo de entrada de texto, usando el atributo `pattern` con alguna **expresion regular**.

```jsx
<input type="text"     id="..." name="..." pattern="">
<input type="email"    id="..." name="..." pattern="">
<input type="password" id="..." name="..." pattern="">
<input type="tel"      id="..." name="..." pattern="">
```

Algunos patrones comunes son:

- **Nombre de Usuario**
    - `[a-zA-Z][a-zA-Z0-9-_]{3,32}`

        Debe comenzar con una letra minuscula o mayuscula, seguida de 3 a 32 letras, numeros, guiones o guion al piso.

        [RegExr: Learn, Build, & Test RegEx](https://regexr.com/2toke)

- **Correo:**
    - `^[a-zA-Z0-9.!#$%&’+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)$`

        Este es el formato de correo admitido por la w3c.

    - `^[\w\.-]+@[\w\.-]+\.\w{2,4}$`

        El correo puede tener letras, numeros, guiones, guion al piso y punto, seguido del simbolo @ y luego letras, numeros, guiones, guion al piso y punto, finaliza con un punto y 2 a 4 letras (*.com / .co*)

        [RegExr: Learn, Build, & Test RegEx](https://regexr.com/2ri2c)

- **Contraseña**:
    - `^(?=.\d)(?=.[a-z])(?=.[A-Z])(?=.[a-zA-Z]).{8,}$`

        Debe tener al menos 8 carácteres con al menos 1 letra mayúscula, 1 letra minúscula y 1 número, también puede contener caracteres especiales

        [RegExr: Learn, Build, & Test RegEx](https://regexr.com/3bfsi)

- **Telefono**:
    - `[0-9]{3}-[0-9]{3}-[0-9]{4}`

        Debe tener el formato xxx-xxx-xxxx

    - `^\s*(?:\+?(\d{1,3}))?([-. (](\d{3})[-. )])?((\d{3})[-. ](\d{2,4})(?:[-.x ](\d+))?)\s*$`

        Admite diferentes formatos de telefono:

        [RegExr: Learn, Build, & Test RegEx](https://regexr.com/38pvb)

[Expresiones Regulares](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Regular_Expressions)

# JavaScript

Usando JS se pueden hacer más validaciones en los campos de un formulario.

Estas validaciones se pueden aplicar en cualquier momento:

- Cualdo el usuario cambia el valor de algún input usando el evento `change`.

    ```jsx
    const usernameInput = document.getElementById('email')
    usernameInput.addEventListener('change', function(){
    	let username = usernameInput.value
    	if(username.length < 8){
    		this.setCustomValidity('Su usuario debe tener más de 8 caracteres')
    	} else {
    		this.setCustomValidity('')		
    	}
    })
    ```

- Cuando el usuario ingresa texto usando el evento `input` de los inputs o textarea.

    ```jsx
    const passwordInput = document.getElementById('email')
    const password2Input = document.getElementById('email')
    password2Input.addEventListener('input', function(){
    	let pass1 = passwordInput.value
    	let pass2 = password2Input.value
    	if(pass1 !== pass2){
    		this.setCustomValidity('Las contraseñas no coinciden')
    	} else {
    		this.setCustomValidity('')		
    	}
    })
    ```

- Cuando el formulario se envía con el evento `submit`, en este evento se pueden validar todos los campos al tiempo:

    ```jsx
    const registro = document.getElementById('registro')
    registro.addEventListener('submit', function (event) {
        let validado = true;
        let mensajeError = '';

    		// Obtención de los valores de los campos
        let nombre = registro['nombre'].value
        let apellido = registro['apellido'].value
        let tipoDocumento = registro['tipoDocumento'].value
        let numDocumento = registro['numDocumento'].value
        let telefono = registro['telefono'].value
        let nacimiento = registro['nacimiento'].value
        let correo = registro['correo'].value
        let password = registro['password'].value
        let password2 = registro['password2'].value
        let message = registro['message'].value

    		// Para los checkbox se utiliza el atributo checked
        let terminos = registro['terminos'].checked
        let newsletter = registro['newsletter'].checked

        //--- Validación de Campos ---
    		// Longitud del nombre
        if (nombre.length < 6) {
            validado = false;
            mensajeError += '> Su Nombre debe tener más de 6 caracteres'
            mensajeError += '<br>'
        }

    		// Tipo de Documento Obligatorio
        if (tipoDocumento == "") {
            validado = false;
            mensajeError += '> Debe Seleccionar un tipo de Documento'
            mensajeError += '<br>'
        }
    		
    		// Rango numérico
    		if (numDocumento == "" || parseInt(numDocumento) < 100000) {
            validado = false;
            mensajeError += '> Su numero de Documento debe ser mayor a 100000'
            mensajeError += '<br>'
        }

        // Validacion de fecha
        let diff = moment().diff(nacimiento, 'year')
        if (nacimiento == "" || diff < 18) {
            mensajeError += '> Debe ser mayor de Edad'
            mensajeError += '<br>'
        }

    		// Validación con expresiones regulares
        let emailValidation = /^[\w\.-]+@[\w\.-]+\.\w{2,4}$/;
        if (emailValidation.test(correo) == false) {
            validado = false;
            mensajeError += '> Ingrese un correo valido'
            mensajeError += '<br>'
        }

    		// Validación con expresiones regulares
        let passwordValidation = /^(?=.*\d)(?=.*[a-z])(?=.*[A-Z])(?=.*[a-zA-Z]).{8,}$/;
        if (passwordValidation.test(password) == false) {
            validado = false;
            mensajeError += '> La contraseña debe tener al menos 8 carácteres, 1 letra minuscula, 1 letra mayuscula y 1 número'
            mensajeError += '<br>'
        }

    		// Validación de exactitud de campos
        if (password2 !== password) {
            validado = false;
            mensajeError += '> Las contraseñas no coinciden'
            mensajeError += '<br>'
        }

    		// Validación de checkbox
        if (terminos == false) {
            validado = false;
            mensajeError += '> Debe aceptar los terminos y condiciones de uso'
            mensajeError += '<br>'
        }

    		// Fin de las validaciones
    		// Creación de un mensaje de alerta y agregación de estilos
        registro.classList.remove('form-validation')
        let alerta = document.getElementById('mensaje-formulario')
        if (validado == false) {
            alerta.innerHTML = mensajeError
            alerta.hidden = false

            registro.classList.add('form-validation')
    				event.preventDefault()
        }
    })
    ```

## Campos Obligatorios

Para validad un campo obligario según el tipo de campo se hace la validación que el valor del campo sea diferente a una cadena vacia:

```jsx
let tipoDocumento = registro['tipoDocumento'].value
if (tipoDocumento == "") {
	  validado = false;
	  mensajeError += '> Debe Seleccionar un tipo de Documento'
	  mensajeError += '<br>'
}
```

O si se trata de un checkbox, se puede compara si está activado o no

```jsx
let terminos = registro['terminos'].checked
if (terminos == false) {
      validado = false;
      mensajeError += '> Debe aceptar los terminos y condiciones de uso'
      mensajeError += '<br>'
  }
```

## Rengo Numérico

En Js todos los campos son cadenas de texto, por lo que se debe convertir a número usando las funciones `parseInt` o `parseFloat` según se necesite, también se debe validar que el campo no esté vacio.

```jsx
let numDocumento = registro['numDocumento'].value
if (numDocumento == "" || parseInt(numDocumento) < 100000) {
    validado = false;
    mensajeError += '> Su numero de Documento debe ser mayor a 100000'
    mensajeError += '<br>'
}
```

## Longitud de Entrada

Dado que todos los valores de entrada del usuario son considerados como cadenas de texto, se puede validar la longitud de este texto con el atributo `length`

```jsx
let nombre = registro['nombre'].value
if (nombre.length < 6) {
    validado = false;
    mensajeError += '> Su Nombre debe tener más de 6 caracteres'
    mensajeError += '<br>'
}
```

## Formato

Así como en HTML5 con el atributo `pattern` se pueden utilizar expresiones regulares en JS con los simbolos `/expr/` donde **expr** se refiere a la expresión regular, luego se puede *"probar"* si un texto cumple con esa expresión usando la función `text`.

```jsx
let emailValidation = /^[\w\.-]+@[\w\.-]+\.\w{2,4}$/
if (emailValidation.test(correo) == false) {
    validado = false;
    mensajeError += '> Ingrese un correo valido'
    mensajeError += '<br>'
}

let passwordValidation = /^(?=.*\d)(?=.*[a-z])(?=.*[A-Z])(?=.*[a-zA-Z]).{8,}$/
if (passwordValidation.test(password) == false) {
    validado = false;
    mensajeError += '> La contraseña debe tener al menos 8 carácteres, 1 letra minuscula, 1 letra mayuscula y 1 número'
    mensajeError += '<br>'
}
```

En el anterior ejemplo se utilizan las expresiones regulares: 

- Correo: `^([\w\.\-_]+)?\w+@[\w-_]+(\.\w+){1,}$`
- Contraseña: `^(?=.*\d)(?=.*[a-z])(?=.*[A-Z])(?=.*[a-zA-Z]).{8,}$`

## Fechas

Para manejar fechas en JS se utiliza comunmente el objeto `Date` sin embargo, se puede utilizar la librería `momentjs` para hacer calculos con fechas rápidamente.

```jsx
let nacimiento = registro['nacimiento'].value
let diff = moment().diff(nacimiento, 'year')
if (nacimiento == "" || diff < 18) {
    mensajeError += '> Debe ser mayor de Edad'
    mensajeError += '<br>'
}
```

## Relacionando varios campos

Con Js se pueden relacionar los valores de dos o más campos, para una validación más estricta, solamente basta con obtener los diferentes valores y compararlos o asociarlos

```jsx
let password = registro['password'].value
let password2 = registro['password2'].value
if (password2 !== password) {
      validado = false;
      mensajeError += '> Las contraseñas no coinciden'
      mensajeError += '<br>'
  }
```

## Mensaje de Alerta

Con Js se puede mostrar un mensaje de alerta con algún mensaje con las respectivas validaciones.

```jsx
let alerta = document.getElementById('mensaje-formulario')
if (validado == false) {
    alerta.innerHTML = mensajeError
    alerta.hidden = false
	
		// Se agregan estilos al formulario
    registro.classList.add('form-validation')

		// Esta linea de código evita que el formulario sea enviado
    event.preventDefault()
}
```

# Submit

El evento submit, generalmente se utiliza cuando la página se está renderizando desde un servidor web que renderiza una página con plantillas como javascript (pug), python (jinja) o php.

En frameworks como React, Angular o Vue, se suele cancelar este evento para realizar las peticiones con programación, usando funciones como `fetch` o librerías como `**axios`.**

Para cancelar este evento se utiliza la función preventDefault del evento mismo:

```jsx
const registro = document.forms['registro']
registro.addEventListener('submit', function(event){
	event.preventDefault()
});
```
