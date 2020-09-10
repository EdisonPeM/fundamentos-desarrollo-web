---
title: Formularios
categories:
    - Intermedio
---

# Estructura HTML

Un formulario es una forma de manipular datos del usuario, ya sea un registro a una página, un inicio de sesión o una suscripción, la forma en la que el usuario ingresa esos datos es por medio de inputs y permite su manipulación por medio de botones. Para crear un formulario se utiliza la etiqueta:

- `<form>`

Cuando un formulario es completado, usualmente lo datos se envían a un servidor para ser tratados y validados, cuando pasa eso a veces la página se redirige a otra o simplemente aparece un mensaje de validación.

<!-- more -->

Los formularios usualmente utilizan los siguientes atributos:

- `action`: Indica al formulario qué hacer cuando se envién los datos, se indica la dirección de un servidor o se especifica la página que se mostará después.
- `method`: Determina el metodo de envío de los datos.
    - *`GET`*: Envía los datos junto con la dirección URL, los datos son públicos y cualquiera los puede ver, se utiliza comúnmente para búsquedas.
    - *`POST`*: Envía los datos escondidos en el cuerpo de la petición, se utiliza cuando los datos son sensibles como contraseñas o números de cuenta.
- `id`: Para identificar el formulario

Los campos de los formularios se pueden agrupar con las etiquetas:

- `<fieldset>`: Permite agrupar un conjunto de inputs
- `<legend>`: Permite agregar un titulo a dicho conjunto

Dentro de los formularios se utilizan las siguientes etiquetas:

- `<input>`: Especifica un campo donde el usuario puede escribir o ingresar datos.
- `<select>`: Crea una lista de opciones ya sea unica o multiple.
    - `<option>`: Agrega una opción a la lista de select.
- `<textarea>`: Crea un cuadro de texto para entradas largas.
- `<label>`: Crea una etiqueta para un input del formulario.
- `<div>`: Se utiliza para dar agrupar inputs y darles estilos.
- `<button>`: Crea un botón de formulario para enviar los datos u otra acción.

Tanto los inputs como los select y textarea se utilizan junto con los siguientes atributos:

- `name`: Define cuál será el nombre de los datos cuando se envíe el formulario.
- `id`: Agrega un identificador unico a un input.
    - La etiqueta label utiliza el atributo `for` para asociarlo con el `id` del input, select o textarea correspondiente.

```html
<form action="#" method="GET" id="registro">
	<div>
		<label for="nombre">Ingrese su nombre</label>
		<input id="nombre" name="nombre">
	</div>
	<div>
		<label for="fav">Seleccione su Favorito</label>
		<select id="fav" name="fav">
			<option>Carros</option>
			<option>Motos</option>
			<option>Ciclas</option>
		</select>
	</div>
	<div>
		<label for="message">Mensaje</label>
		<textarea id="message" name="message"></textarea>
	</div>
	<button>Enviar</button>
</form>
```

La etiqueta `<input>` es vacia (***self-closing***), es decir, no tiene etiqueta de cierre.

[Forms - HTML Reference](https://htmlreference.io/forms/)

[input](https://developer.mozilla.org/es/docs/Web/HTML/Elemento/input)

[HTML Forms](https://www.w3schools.com/html/html_forms.asp)

# Tipos de Inputs

## Texto

Con HTML5 llega una variedad de inputs que se pueden especificar utilizando el atributo `type`, el valor por defecto es `"text"`.

Un input de texto es una entrada donde el usuario deberá ingresar datos alfanumericos, por ejemplo un input para nombres y apellidos.

```html
<div class="form_field">
    <label for="nombre">Nombre</label>
    <input id="nombre" name="nombre">
</div>
<div class="form_field">
    <label for="apellido">Apellido</label>
    <input type="text" id="apellido" name="apellido">
</div>
```

## **Correo**

Para usar un input de correos electrónicos se agrega `type="email"`

Para este input, HTML5 automáticamente valida que su contenido contenga “@”.

```html
<div class="form_field">
		<label for="correo">Correo Electronico</label>
    <input type="email" id="correo" name="correo">
</div>
```

## **Contraseña**

El input para contraseñas se utiliza usando `type="password"`,

Este tipo de input es similar a un input de texto, pues recibe cualquier caracter, la única diferencia es que “esconde” el contenido, este input no se encarga de encripar o cifrar la contraseña, solo la esconde para que no sea visible.

```html
<div class="form_field">
    <label for="password">Contraseña</label>
    <input type="password" id="password" name="password">
</div>
```

## **Radio Button**

Un radio button es un input de selección única con varias opciones, Para ello se utiliza `type="radio"`

Los input tipo radio deben tener el mismo `name` para asociarlos a la misma entrada, adicionalmente deben usar el atributo `value` para especificar el valor de la opción a seleccionar.

```html
<fieldset class="form_fieldset">
  <legend>Seleccione su Genero</legend>
	<div class="form_field--radio">
	    <input type="radio" id="masculino" name="genero" value="Masculino">
	    <label for="masculino">Masculino</label>
	</div>
  <div class="form_field--radio">
    <input type="radio" id="femenino" name="genero" value="Femenino">
    <label for="femenino">Femenino</label>
  </div>
  <div class="form_field--radio">
    <input type="radio" id="otro" name="genero" value="Otro">
    <label for="otro">Otro</label>
  </div>
</fieldset>
```

## **Checkbox**

Los inputs tipo checkbox tienen dos objetivos, principalmente a diferencia del radio button, permite seleccionar varias opciones. Se utiliza `type="checkbox"`

Igualmente que el radio, se utiliza el mismo `name` para asociar los campos y `value` para indicar cuál es el valor que el usuario está seleccionando.

```html
<fieldset class="form_fieldset">
    <legend>Habilidades en Lenguajes de programacion</legend>
		<div class="form_field--checkox">
				<input type="checkbox" id="skill-html" name="skills" value="html">
				<label for="skill-html">Html</label>
		</div>
		<div class="form_field--checkox">
				<input type="checkbox" id="skill-css" name="skills" value="css">
				<label for="skill-css">Css</label>
		</div>
		<div class="form_field--checkox">
				<input type="checkbox" id="skill-js" name="skills" value="Js">
				<label for="skill-js">Js</label>
		</div>
</fieldset>
```

La segunda intención de los checkbox es dar a elegir a un usuario entre aceptar o no una opción, para este no es necesario definir un valor específico.

```html
<div class="form_field--checkox">
		<input type="checkbox" id="terminos" name="terminos">
		<label for="terminos">Aceptar Terminos y condiciones de uso</label>
</div>
<div class="form_field--checkox">
		<input type="checkbox" id="newsletter" name="newsletter">
		<label for="newsletter">Suscribirse a nuestro boletin</label>
</div>
```

## Número

los inputs númericos son aquellos que solamente aceptan números, se pueden utilizar para telefonos o numeros de documento.

Para usarlo se especifica `type="number"`.

```html
<div class="form_field">
    <label for="numDocumento">Numero de Documento</label>
    <input type="number" id="numDocumento" name="numDocumento">
</div>
```

### Rango

Un input tipo rango, permite crear un deslizador entre un rango de números, este se usa con `type="range"` y se definen los valores mínimo y máximo, así como el paso (step) del deslizador 

```html
<div class="form_field">
    <label for="precio">Elegir Precios</label>
    <input type="range" id="precio" name="precio"
						min="300000" max="1000000" step="10000">
</div>
```

Los atributos min, max y step se pueden definir también en el input `type=number"`.

### Telefono

Los números telefonicos se pueden trabajar mediante inputs con `type="tel"`, estos inputs generalmente trabajan con el atributo `pattern` donde se especifica el formato del telefono que se admite ya que este tipo de input acepta tanto numeros como letras.

```html
<div class="form_field">
    <label for="telefono">Telefono</label>
    <input type="tel" id="telefono" name="telefono"
						pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}">
</div>
```

## **Fechas**

Existen diferentes formas de recibir fechas en HTML,

- *`date`*: Admite solamente fechas.
- *`datetime-local`*: Recibe fechas con horas.

```html
 <div class="form_field">
    <label for="nacimiento">Fecha Nacimiento</label>
    <input type="date" name="nacimiento" id="nacimiento">
</div>
```

## Select

La etiqueta `<select>` crea un menú de opciones para elegir, las opciones contenidas en el menú son representadas por elementos `<option>`, los cuales pueden ser agrupados por elementos `<optgroup>`.

Al igual que *checkbox* y *radio button*, cada opción deberá tener el atributo `value` para identificar su significado ya que el usuario solo da click para seleccionar la opción, mas no escribe directamente el valor exacto.

```html
<div class="form_field">
    <label for="tipoDocumento">Tipo de Documento</label>
    <select id="tipoDocumento" name="tipoDocumento">
        <option value="">Seleccione una opcion</option>
        <option value="ti">Tarjeta Identidad</option>
        <option value="cc">Cédula De Ciudadania</option>
        <option value="pasaporte">Pasaporte</option>
    </select>
</div>
```

También se puede utilizar para selección multiple usando el atributo multiple

```html
<div class="form_field">
		<label for="cars">Escoja carros favoritos</label>
		<select name="cars" id="cars" multiple>
		  <option value="volvo">Volvo</option>
		  <option value="saab">Saab</option>
		  <option value="opel">Opel</option>
		  <option value="audi">Audi</option>
		</select>
</div>
```

## TextArea

Un `<textarea>` es una forma en la que se pueden agregar un dato de varias lineas, generalmente se utilizan para comentarios, descripciones, post, etc.

Estos campos se utilizan con los atributos:

- `cols`: Indica el tamaño a lo ancho del textarea en terminos de caractéres.
- `rows`: Indica el tamaño a lo ancho del textarea en terminos de lineas de texto.

```html
<div class="form_field">
    <label for="message">Mensaje</label>
    <textarea id="message" name="descripcion" cols="30" rows="10" ></textarea>
</div>
```

## **Botones**

Existen diferentes tipos de botones, para agregar un botón se utiliza la etiqueta `<button>` y para cambiar el tipo se usa el atributo `type`, este puede ser:

- `submit`: valor por defecto, envía los datos del formulario hacia donde se especifique en `action`.
- `reset`: borra todas las entradas de un usuario
- `button`: no hace nada, pero se utiliza para agragar funciones de JS

```html
<button>Enviar</button>
<button type="reset">Borrar</button>
<button type="button">Verificar</button>
```

# **Atributos Adicionales**

Todos los inputs de un formulario, incluyendo textarea y select, pueden tener algunos de los siguientes atributos.

## AutoFocus

Con el atributo `autofocus` un input se selecciona automaticamente al cargar la página para que el usuario pueda comenzar a escribir en él.

## Ejemplo de valores

Muchas veces queremos indicar al usuario cómo deben ser el formato de los valores de entrada, por ejemplo una dirección o un telefono movil, esos ejemplos se agregan con el atributo `placeholder`.

```html
<div class="form_field">
    <label for="direccion">Direccion</label>
    <input id="direccion" name="direccion" placeholder="Cra 01 C Bis # 01 - 01">
</div>
```

Este `placeholder` desaparece cuando el usuario ingresa algún valor.

## Valor por Defecto

Para agregar un valor predefinido para un elemento se utilizan diferentes atributos:

- Para el caso de un input se debe agregar el atributo `value` y su respectivo valor.

```html
<div class="form_field">
    <label for="direccion">Direccion</label>
    <input id="direccion" name="direccion" value="Cra 01 C Bis # 01 - 01">
</div>
```

- para el caso del *checkbox* y del *radio button* se utiliza la palabra `checked` para indicar cuál se la opción seleccionada por defecto.

```html
<div class="form_field--checkox">
		<input type="checkbox" id="newsletter" name="newsletter" checked>
		<label for="newsletter">Suscribirse a nuestro boletin</label>
</div>
```

```html
<fieldset class="form_fieldset">
  <legend>Seleccione su Genero</legend>
	<div class="form_field--radio">
	    <input type="radio" id="masculino" name="genero" value="Masculino" checked>
	    <label for="masculino">Masculino</label>
	</div>
  <div class="form_field--radio">
    <input type="radio" id="femenino" name="genero" value="Femenino">
    <label for="femenino">Femenino</label>
  </div>
  <div class="form_field--radio">
    <input type="radio" id="otro" name="genero" value="Otro">
    <label for="otro">Otro</label>
  </div>
</fieldset>
```

- Para el caso de la etiqueta `<select>` se agrega la palabra `selected` en la `<option>` que se desea sea el valor seleccionado por defecto.

```html
<div class="form_field">
    <label for="tipoDocumento">Tipo de Documento</label>
    <select name="tipoDocumento" id="tipoDocumento">
				<option value="ti">Tarjeta Identidad</option>
        <option value="cc" selected>Cédula De Ciudadania</option>
        <option value="pasaporte">Pasaporte</option>
    </select>
</div>
```

## Campos Obligatorios

Para que un campo sea obligatorio en un formulario se debe agregar el **atributo sin valor** `required`

```html
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

Los atributos `min` y `max` limitan un rango para inputs numericos (y Rango).

```html
<div class="form_field">
	<label for="filtro">Filtrar cantidad: </label>
	<input type="number" id="filtro" name="filtro" min="0" max="100">
</div>
```

## Longitud de Entrada

Se puede limitar la longitud de la entradad el usuario con los atributos;

- `minlength`: designa el tamaño minimo de caracteres admitidos
- `maxlength`: designa el tamaño máximo de caracteres admitidos

```html
<div class="form_field">
    <label for="password">Contraseña</label>
    <input type="password" id="password" name="password"
						minlength="8" maxlength="15">
</div>
```

## Formato

Se puede obligar al usuario a seguir un formato específico (así como para el telefono) en los inputs donde el usuario pueda digitar.

Estos formatos se definen con el atributo `pattern` y se utilzan expresiones regulares, algunos ejemplos son:

- **Telefono**:
    - `[0-9]{3}-[0-9]{3}-[0-9]{4}`
    - `^\s*(?:\+?(\d{1,3}))?([-. (](\d{3})[-. )])?((\d{3})[-. ](\d{2,4})(?:[-.x ](\d+))?)\s*$`

    [RegExr: Learn, Build, & Test RegEx](https://regexr.com/38pvb)

- **Correo:**
    - `^[a-zA-Z0-9.!#$%&’+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)$`
    - `\b[\w\.-]+@[\w\.-]+\.\w{2,4}\b`

    [RegExr: Learn, Build, & Test RegEx](https://regexr.com/2ri2c)

- **Contraseña**:
    - `^(?=.\d)(?=.[a-z])(?=.[A-Z])(?=.[a-zA-Z]).{8,}$`
    - `^(?=.[0-9]+.)(?=.[a-zA-Z]+.)[0-9a-zA-Z]{6,}$`

    [RegExr: Learn, Build, & Test RegEx](https://regexr.com/3bfsi)

## Deshabilitar

Se pueden deshabilitar cualquier input con los atributos:

- `disabled`: los inputs que tengan este atributo no se podrán llenar, quedan deshabilitados
- : los inputs que tengan este atributo no se podrán llenar, pero a diferencia del disabled, el contenido se podrá “seleccionar”

# Estilos CSS

Los elementos `<input>`, `<select>`, `<textarea>` y `<button>` tienen estilos predeterminados que se pueden personalizar tal como:

- **Tipografía**: font-size, font-wight
- **Color**: color, background-color, border-color.
- **Box Model**: padding, margin, width, height. border, ***outline***

Entre otros.

## Selector de Atributo

Para personalizar más los inputs, se puden utilizar los selectores de atributo para distinguir entre los diferentes tipos de inputs. Los selectores de atributos utilizan la estructura: 

- `[attr]`: Para elementos que tienen el atributo ***attr*** en su etiqueta*.*
- `[attr=value]`: Para elementos cuyo atributo ***attr*** tiene exactamente el valor ***value***.
- `[attr^=value]`: Para elementos cuyo atributo ***attr*** tiene un valor que comienza por ***value***.
- `[attr$=value]`: ****Para elementos cuyo atributo ***attr*** tiene un valor que termina con ***value***.
- `[attr*=value]`**:** Para elementos cuyo atributo ***attr*** tiene un valor que contenga ***value***.
- `[attr~=value]`: Para elementos cuyo atributo ***attr*** tiene una lista de palabras separadas por espacios, y una de esas es ***value***.
- `[attr|=value]`: ****Para elementos cuyo atributo ***attr*** tiene exactamente el valor ***value*** o empieca por ***value*** seguido de un guión `-`

Cualquier selector de atributo tiene una especificidad de (0,1,0), la misma especificidad de una clase.

[Selectores de atributo](https://developer.mozilla.org/es/docs/Web/CSS/Selectores_atributo)

[CSS Attribute Selector](https://www.w3schools.com/css/css_attribute_selectors.asp)

---

En ese sentido se puede utilizar el selector de atributo para discriminar los inputs según su tipo:

- `input[type=checkbox]`: Para dar estilos a inputs de tipo checkbox
- `input[type=radio]`: Para dar estilos a inputs de tipo checkbox
- etc..

## Pseudo-Clases

CSS tiene un conjunto de pseudo-clases específicas para manejar los estilos de los inputs (select, text-area):

---

- `:hover`: Se activa cuando el mouse pasa por encima un elemento.

    ```css
    .form-button:hover {
        background-color: #3a68ff;
    }
    ```

- `:active`: Se activa cuando el mouse hace click en un elemento.

    ```css
    .form-button:active {
        background-color: #002fc8;
    }
    ```

---

- `:focus`: Se activa cuando el elemento tiene el foco del usuario, esto es, cuando el usuario está escribiendo en el o seleccionandolo.

    ```css
    .form-input:focus {
        border-color: #003cff;
    }
    ```

- `:placeholder-shown`: Si un input está mostrando un placeholder
    - `::placeholder`: Se refiere al pseudo-elemento que representa al placeholder.

    ```css
    .form-input:placeholder-shown::placeholder {
        color: #323a53;
        opacity: 0.5;
    }
    ```

---

- `:required` / `:optional`: según si un campo es obligatorio u opcional.

    ```css
    .form-input:required {
        background-color: #cad1e9;
    }
    ```

    Esta pseudo clase es similar a `.form-input[required]`

- `:in-range` / `:out-of-range`: Si el valor de un campo numérico está dentro o fuera de los limites definidos con los atributos `min` y `max`.

    ```css
    .form-input:out-of-range {
        color: #ff0000;
    }
    ```

- `:valid` / `:invalid`: según si el campo es valido según las validaciones de html o no.

    ```css
    .form-input:valid {
        border-color: #1ec500;
    }

    .form-input:invalid {
        border-color: #ff0000;
    }
    ```

    La pseudo-clase :invalid se activa cuando el contenido no cumple con atributos de validación de HTML:

    - El input tiene `required` pero está vacio
    - Los número se pasan de los limites `min` y `max` (similar a `:out-of-range`)
    - Para longitud de textos no respeta los limites `minleght` y `maxlenght`
    - El valor que está ingresando el usuario no cumple con el `pattern` definido
    - Un campo con `type="email"` no contiene **@**
    - Un campo con `type="url"` no contiene **http://** o **https://**

---

- `:disabled` / `:enable`: según si un campo tiene el atributo `disabled` o no.

    ```css
    .form-input:disabled {
        background: linear-gradient(to right, #ddd, #eef, #fff);
    }
    ```

    Esta pseudo clase es similar a `.form-input[disabled]`

- `:read-only` / `:read-write`: Cuando un campo tiene el atributo `readonly` o no.

    ```css
    .form-input:read-only {
        background-color: #eff4ff;
    }
    ```

    Esta pseudo clase es similar a `.form-nput[readonly]`

---

- `:checked`: Se activa cuando un input de tipo checkbox o radio que esté seleccionado (on).

    ```css
    .form-input[type="checkbox"]~label,
    .form-input[type="radio"]~label {
        color: #5f5f5f;
    }

    .form-input:checked~label {
        color: black;
    }
    ```

---

Todas las pseudo-clases se pueden combinar una después de la otra para un elemento, se debe tener cuidado que no sean opuestas y que se complementen entre sí:

```css
.form-input:required:focus:valid {
    border-color: #1ec500;
}

.form-input:required:focus:invalid {
    border-color: #ff0000;
}

.form-input:required:focus:out-of-range {
    color: #ff0000;
}

.form-input:read-only:focus {
    border-color: transparent;
}
```

Así mismo se pueden combinar los selectores de atributos con las pseudo-clases:

```css
.form-input[type="checkbox"]:focus,
.form-input[type="radio"]:focus {
    outline: solid #88a4ff;
    outline-offset: -1px;
}
```

# Bootstrap

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
    <div class="col-md form-group">
      <input type="text" class="form-control" placeholder="First name">
    </div>
    <div class="col-md form-group">
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

## Botones

Bootstrap tiene predefinido un conjunto de botones usando la clase `.btn` ****en algún botón o link, esta clase define la estructura del botón, por lo que se usa en conjunto con `.btn-[color]` o `.btn-outline` para darle estilos usando las palabras clave de los colores de bootstrap.

Los links pueden tener estilos de botónes y los botones pueden tener estilos de links, sin embargo los links se deben usar cuando queremos ir a otra página y los botones cuando queremos realizar alguna acción con la interacción del usuario.

[Buttons](https://getbootstrap.com/docs/4.5/components/buttons/)

[Bootstrap 4 Buttons](https://www.w3schools.com/bootstrap4/bootstrap_buttons.asp)

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
