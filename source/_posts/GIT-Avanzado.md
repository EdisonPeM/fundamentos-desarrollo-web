---
title: GIT Avanzado
categories:
    - Herramientas
---

# Ramas

Las ramas de Git representan líneas independientes de desarrollo, por lo que se puede trabajar en diferentes características de un proyecto de forma paralela sin que se crucen los cambios.

![Untitled.png](Untitled.png)

[rama de git | Atlassian Git Tutorial](https://www.atlassian.com/es/git/tutorials/using-branches)

[Git - Procedimientos Básicos para Ramificar y Fusionar](https://git-scm.com/book/es/v2/Ramificaciones-en-Git-Procedimientos-B%C3%A1sicos-para-Ramificar-y-Fusionar)

[Trabajar con ramas en Git: git branch](https://desarrolloweb.com/articulos/trabajar-ramas-git.html)

<!-- more -->

## Ver Ramas

```bash
$ git branch
$ git branch --list
$ git branch --all
```

## Crear Ramas

```bash
$ git branch [*NombreRama*]
```

## Cambiar de Rama

```bash
$ git checkout [*NombreRama*]
```

## Crear y Cambiar ramas al tiempo

```bash
$ git checkout -b [*NombreRama*]
```

## Eliminar Ramas

Una rama no se podrá eliminar si se tiene trabajo que no se ha fusionado.

```bash
$ git branch -d [*NombreRama*]
```

# Diferencias

Para ver qué diferencias existen entre ramas se puede usar el siguiente comando:

```bash
$ git diff [*NombreRama1*] [*NombreRama2*]
```

# Historial

Para ver las ramas en el historial de cambios se puede complementar el comando git log de la siguiente forma.

```bash
$ git log --all --graph --oneline
```

# Fusión (*Merge*)

Cuando se han terminado de desarrollar las diferentes características se deben mezclar los cambios en una rama principal. La rama principal de git es **master.**

Para fusionar ramas, se debe primero parar en la rama que recibirá los cambios y luego el comando ***git merge.*** por lo que los siguientes 2 serán diferentes.

```bash
$ git checkout master
$ git merge [*NombreRama1*]
```

```bash
$ git checkout [*NombreRama1*]
$ git merge master
```

Sin embargo según los archivos que se modifiquen y los commits que se hagan pueden haber diferentes tipos de mezclas (esto no requiere configuración adicional, git lo hace automáticamente).

## Avance Rápido (*Fast Forward*)

El tipo de merge fast forward se aplica cuando la rama que se modificó parte de la rama a la que se va a fusionar, y en la rama base no se realizaron cambios.

![Untitled1.png](Untitled1.png)

![Untitled2.png](Untitled2.png)

[Git Un-Merge](http://marksabino.com/defproc/blog/2012/git-un-merge/)

## Recursive

Esta estrategia se aplica cuando la rama que se modificó parte de la rama a la que se va a fusionar, pero en la rama base se realizaron cambios.

![Untitled3.png](Untitled3.png)

## Resolución de Conflictos

Cuando se realizan cambios tanto en la rama base como en la rama secundaria, al intentar mezclarlas se puede generar un conflicto si se trata de modificaciones en las **mismas líneas de código del mismo archivo**.

En ese caso el merge no se podrá hacer y se pedirá al usuario definir cuales cambios desea conservar en la mezcla, esto se verá así:

```html
<<<<<<< HEAD:index.html
<div id="footer">contact : email.support@github.com</div>
=======
<div id="footer">
 please contact us at support@github.com
</div>
>>>>>>> develop:index.html
```

Donde **HEAD** se refiere a la rama actual y **develop** en este caso es la rama secundaria.

El fragmento de código que hay entre los símbolos **<<<<<<<** y  **=======** son los cambios base y el fragmento de código que hay entre los símbolos **=======** y **>>>>>>>** son los cambios de la segunda rama. Aunque aparezcan estos símbolos, el usuario deberá eliminarlos y organizar el código manualmente, estos son solo informativos.

Una vez hecho los respectivos arreglos, el usuario deberá hacer un commit.

```bash
$ git add -A
$ git commit -m 'Mezcla con develop'
```

La resolución de conflictos en visual Studio Code es más simple, pues vscode ofrece las opciones de **mantener cambios actuales** (en la rama base), **mantener los cambios de la rama entrante**, o **mantener ambos cambios,** igualmente el usuario debe hacer un commit después de organizar el código.

![Untitled4.png](Untitled4.png)

[Ramas y resolución de conflictos en git](https://styde.net/ramas-y-resolucion-de-conflictos-en-git/)

[Git merge | Atlassian Git Tutorial](https://www.atlassian.com/es/git/tutorials/using-branches/git-merge)

[Git - Procedimientos Básicos para Ramificar y Fusionar](https://git-scm.com/book/es/v2/Ramificaciones-en-Git-Procedimientos-B%C3%A1sicos-para-Ramificar-y-Fusionar)

# Git-Flow

Gitflow es un diseño de flujo de trabajo de Git que define un modelo estricto de ramificación diseñado alrededor de la publicación del proyecto. Proporciona un marco sólido para gestionar proyectos más grandes.

![Untitled5.png](Untitled5.png)

- La rama **master** será la rama principal donde habitan las versiones estables de un proyecto.
- La rama **develop** será la rama principal de desarrollo, donde se integran cambios y se realizan pruebas.
- Las ramas **feature** corresponden a las diferentes características que se desarrollan de forma aislada e independientes, estas ramas se integran con develop usando fusiones recursivas (—no-ff)
- La rama **release** corresponde a las versiones de entrega, en esta rama se realizan pruebas y correcciones para desplegar una versión estable.
- En la rama **hotfix** se deben corregir errores **(*bugs*)** que existan en producción.

[A successful Git branching model](https://nvie.com/posts/a-successful-git-branching-model/)

[Flujo de trabajo de Gitflow | Atlassian Git Tutorial](https://www.atlassian.com/es/git/tutorials/comparing-workflows/gitflow-workflow)

# Github

Cuando se trabaja con plataformas como github se pueden crear y cambiar de ramas en la nube, sin embargo no es recomendable si no es necesario, es preferible subir los cambios de las ramas desde local, sin embargo las mezclas en la nube mejoran la gestión de un proyecto.

## Publicar nuevas ramas a la nube

Para publicar una nueva rama se realiza un ***push*** con la bandera **-u**

```bash
$ git push -u origin [*NombreRama*]
```

## Actualizar ramas en la nube

```bash
$ git checkout [*NombreRama*]
$ git push
```

## Actualizar ramas locales

```bash
$ git checkout [*NombreRama*]
$ git pull
```

## Bajar nuevas ramas

Para actualizar el repositorio con ramas existentes en github pero no en local, se pueden bajar las nuevas ramas con el siguiente comando.

```bash
$ git fetch --all 
```

## Eliminar ramas del repositorio remoto

Para publicar una nueva rama se realiza un ***push*** con la bandera **-d**

```bash
$ git push -d origin [*NombreRama*]
```

## Bajar un repositorio existente

Para bajar un repositorio existente debe hacerse fuera de VSCode, ya que esto **descargará** la carpeta donde se encuentra el proyecto, por lo que se deberá hacer por consola desde donde se desea descargar el proyecto.

Cuando un repositorio se baja por primera vez, se baja con todas las ramas.

```bash
$ git clone https://github.com/userName/repoName.git
```

# Gestión de Proyectos

## Pull Request

Una forma eficiente de mantener orden a las ramas de un repositorio es usando **pull resquest** aunque el nombre es confuso, un pull request es una petición para **mezclar ramas en la nube**, para esto se puede asignar un revisor para que valide los cambios que se desean incorporar al proyecto desde una rama secundaria.

![Untitled6.png](Untitled6.png)

![Untitled7.png](Untitled7.png)

### Resolución de Conflictos

Si no se presentan conflictos se podrá hacer el merge automáticamente una vez se apruebe el pull request. Si se presentan conflictos se pueden resolver inmediatamente en github o se puede actualizar la rama en local con los conflictos resueltos y hacer **push** a la nube**.**

Para esto se recomienda mezclar la rama remota en la rama que se desea mezclar (hacer un merge inverso desde la nube a local) de la siguiente forma

```bash
$ git checkout develop
$ git pull
$ git checkout rama1
$ git merge develop
# Se resuelven los conflictos en local desde vscode
$ git add -A
$ git commit -m 'Resolviendo conflictos con develop'
$ git push
```

El pull resquest se actualizará automáticamente.

```bash
$ git checkout rama1
$ git pull origin develop
# Se resuelven los conflictos en local desde vscode
$ git commit -am 'Integrando develop'
```

## Issues

Los **issues** de github es la forma en la que podemos gestionar tareas, entendiendo una tarea parte del desarrollo, los issues pueden referirse a nuevas funcionalidades, problemas de integración o errores de producción.

Los issues se pueden contener:

- Un **título** y una **descripción** describen de qué se trata el problema.
- Las **etiquetas** codificadas por colores lo ayudan a clasificar y filtrar sus problemas (al igual que las etiquetas en el correo electrónico).
- Un **milestone** actúa como un contenedor para problemas. Esto es útil para asociar problemas con características específicas o fases del proyecto (por ejemplo, *Weekly Sprint 9 / 5-9 / 16* o *Shipping 1.0* ).
- Asignar un responsable (**assignee**) para trabajar en el tema en un momento dado.
- **Los comentarios** permiten que cualquier persona con acceso al repositorio proporcione comentarios.

Para cerrar un issue se puede realizar de forma manual, o con palabras clave en los mensajes de los commits o en la descripción de los PR.

- close #x
- fix #x
- resolve #x

Aquí los **#x** se refiere al identificador del issue correspondiente.

[Mastering Issues](https://guides.github.com/features/issues/)

[Linking a pull request to an issue](https://docs.github.com/en/github/managing-your-work-on-github/linking-a-pull-request-to-an-issue)

## Labels

Tanto issues como pull request pueden tener asociados etiquetas, estas pueden ser personalizadas, sin embargo github provee unas etiquetas base:

- **[bug](https://github.com/EdisonPeM/repo-ramas/labels/bug):** Algo no funciona
- **[documentation](https://github.com/EdisonPeM/repo-ramas/labels/documentation):** Mejoras o adiciones a la documentación.
- **[duplicate](https://github.com/EdisonPeM/repo-ramas/labels/duplicate):** Este issue o pull request ya existe.
- **[enhancement](https://github.com/EdisonPeM/repo-ramas/labels/enhancement):** Solicitud de nuevas funciones.
- **[help wanted](https://github.com/EdisonPeM/repo-ramas/labels/help%20wanted):** Se necesita atención adicional.
- **[invalid](https://github.com/EdisonPeM/repo-ramas/labels/invalid):** Indica que un issue o Pull Request ya no es relevante.
- **[question](https://github.com/EdisonPeM/repo-ramas/labels/question):** Se solicita más información.
- **[wontfix](https://github.com/EdisonPeM/repo-ramas/labels/wontfix):** indica que no se trabajará en un issue o pull request.

[EdisonPeM/repo-ramas](https://github.com/EdisonPeM/repo-ramas/labels)

## Github Projects

Github provee de un gestor de proyectos con github projects, en donde se pueden crear Tableros Ágiles (**Agile Dashboard**) y se pueden crear tarjetas (como kanban) para representar tareas. 

Los tableros de proyectos están formados por notas, issues y pull requests que se clasifican como **tarjetas** en columnas de su elección. Puede arrastrar y soltar o usar métodos abreviados de teclado para reordenar las tarjetas dentro de una columna, mover tarjetas de una columna a otra y cambiar el orden de las columnas.

Existen diferentes modelos de tableros

- **Kanban básico:**  Realiza un seguimiento de sus tareas con las columnas To Do, In progress y Done.
- **Kanban automatizado:**	Las tarjetas se mueven automáticamente entre las columnas To Do, In progress y Done. Según el estado de los issues y pull requests.
- **Kanban automatizado con revisión**: Las tarjetas se mueven automáticamente entre las columnas To Do, In progress y Done, con activadores adicionales para el estado de revisión de pull requests.
- **Triage de Bugs**: Triage y priorice los errores con las columnas To Do, Alta prioridad, Baja prioridad y Cerrado

![Untitled8.png](Untitled8.png)

[About project boards](https://docs.github.com/en/github/managing-your-work-on-github/about-project-boards)
