---
title: Control de Versiones
categories:
    - Herramientas
---

# Git

![Untitled.png](Untitled.png)

[Book](https://git-scm.com/book/es/v2)

[Manual de Git](https://desarrolloweb.com/manuales/manual-de-git.html)

[git - la guía sencilla](https://rogerdudler.github.io/git-guide/index.es.html)

[La guía básica de Git y Github para principiantes](https://medium.com/@sthefany/primeros-pasos-con-github-7d5e0769158c)

<!-- more -->

## Descarga

[Downloading Git](https://git-scm.com/download/win)

## Configuración

La configuración inicial de git es necesaria hacerla desde **git bash** o alguna **terminal.**

```bash
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

[Git - Configurando Git por primera vez](https://git-scm.com/book/es/v2/Inicio---Sobre-el-Control-de-Versiones-Configurando-Git-por-primera-vez)

### Configurar VSCode (*Windows*)

Para ejecutar la terminal de git (*git bash)* desde Visual Studio Code, se debe configurar de la siguiente forma:

1. Abrir la barra de comandos con las teclas **ctrl + shift + p**

    ![Untitled1.png](Untitled1.png)

2. Allí escribir **Select Default Shell**

    ![Untitled2.png](Untitled2.png)

3. Se selecciona **git bash**

    ![bash2.png](bash2.png)

4. Se abre una nueva terminal 

    ![Captura2.png](Captura2.png)

5. La terminal debería tener este aspecto

    ![screen.png](screen.png)

## Crear un Repositorio

```bash
$ git init
```

![screen_2.png](screen_2.png)

**`git init`** en consola

![panel.png](panel.png)

**`git init`** en panel de vscode

[Git - Obteniendo un repositorio Git](https://git-scm.com/book/es/v2/Fundamentos-de-Git-Obteniendo-un-repositorio-Git)

## Cambios

[Git - Guardando cambios en el Repositorio](https://git-scm.com/book/es/v2/Fundamentos-de-Git-Guardando-cambios-en-el-Repositorio)

### Ver Cambios

```bash
$ git status
```

![status.png](status.png)

`**git status**` en terminal y en panel de vscode

### Guardar Cambios

```bash
$ git add [*Nombre del archivo*]
$ git add -A
```

![addt.png](addt.png)

`**git add -A**` en terminal

![add.png](add.png)

`**git add index.html`** en panel de vscode

![adda.png](adda.png)

`**git add -A`** en panel de vscode

### Confirmar Cambios

```bash
$ git commit -m 'Mensaje'
```

![committe.png](committe.png)

commit en consola

![commitvsc.png](commitvsc.png)

commit en vscode

## Ver historial de Cambios

```bash
$ git log
$ git log --oneline
$ git log --name-only
```

![log.png](log.png)

El código amarillo también se llama **código SHA**, es el identificador único de los cambios registrados en cada commit.

[Git - Ver el Historial de Confirmaciones](https://git-scm.com/book/es/v2/Fundamentos-de-Git-Ver-el-Historial-de-Confirmaciones)

## Deshacer Cambios

[Git - Deshacer Cosas](https://git-scm.com/book/es/v2/Fundamentos-de-Git-Deshacer-Cosas)

### Sin Preparar (Working Directory)

```bash
$ git checkout -- [*Nombre del archivo*]
```

![restore.png](restore.png)

Deshacer cambios en terminal

![restore2.png](restore2.png)

Deshacer cambos en vscode

### Preparado (Stage)

```bash
$ git reset HEAD [*Nombre del archivo*]
```

![restorecomm.png](restorecomm.png)

Deshacer index en terminal

![restorecomm2.png](restorecomm2.png)

Deshacer index en vscode

### !Confirmados (Repository)

```bash
$ git reset --soft [*SHA*]
$ git reset --hard [*SHA*]
```

*`reset —hard`* elimina el commit y los cambios del código que se hicieron.

Se considera mala práctica eliminar los commits, es preferible arreglar el código y agregar un nuevo commit con el arreglo, ya que se pueden generar inconsistencias con los repositorios remotos.

## Resumen

![Untitled3.png](Untitled3.png)

# Repositorios en la Nube

## Github

Crear un nuevo repositorio vacío.

![crear_nuevo_repo.png](crear_nuevo_repo.png)

![repon.png](repon.png)

## Agregar un Repositorio

```bash
$ git remote add origin https://github.com/userName/repoName.git
```

![url.png](url.png)

Copiar el link para agregar el repo remoto

## Subir Cambios Locales a Remotos (Nube)

```bash
$ git push
$ git push origin master
$ git push -u origin master
```

![remote.png](remote.png)

`**git push**` en terminal

![push3.png](push3.png)

git push en vscode

![ok.png](ok.png)

## Bajar Cambios de Remoto (Nube) a Local

```bash
$ git pull origin master
```

![pull.png](pull.png)

**git pull** en terminal

![pull2.png](pull2.png)

git pull en vscode-

[Git - Trabajar con Remotos](https://git-scm.com/book/es/v2/Fundamentos-de-Git-Trabajar-con-Remotos)
