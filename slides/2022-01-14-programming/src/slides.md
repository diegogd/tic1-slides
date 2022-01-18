---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/590961/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: true
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
---

# Programación

---
layout: image-right
image: https://source.unsplash.com/collection/590961/1080x1080
---

# Entorno de trabajo

Trabajaremos con el entorno CodeSandbox ya que permite trabajar con vscode en web y con Astro.

---

# Astro

Astro es un sistema que nos permite crear páginas estáticas muy complejas de una forma muy sencilla.

---
layout: center
---

# CodeSandbox y Astro

<div></div>

![Ejemplo](/codesandbox.jpg)

---

# Crear un proyecto de Astro en CodeSandbox

Para comenzar hay que hacer lo siguiente:

- Crear una cuenta en [github](https://www.github.com)
- Acceder al siguiente enlace [Crear proyecto en CodeSandbox](https://astro.new/minimal?on=codesandbox)
- Click on Sign In --> Sign in with Github
- Click on Fork
- En la pestaña de Github <mdi-github/> localizar el botón `Sign In` junto al texto "Enable Commits"
- En el apartado "Export to new Github repository" poner el texto con el nombre de vuestro proyecto. Por ejemplo en el mío es `ai-art-astro`.

A partir de ahora ya tenéis vuestro propio repositorio.

---

# Compartir vuestro proyecto

A partir del trabajo que habéis hecho tendréis una dirección única para trabajar desde vuestro proyecto.

Por ejemplo la mía es [`https://codesandbox.io/s/github/diegogd/ai-art-astro/tree/main/`](https://codesandbox.io/s/github/diegogd/ai-art-astro/tree/main/)

Ese repositorio estará público y accesible para todo el mundo. Mantenedlo así para garantizar el acceso.

<div class="warning">
<mdi-eye/> No es la página con la que trabajaremos.
</div>

<style>
  .warning {
    padding: 1em;
    border: 1px #ff8888 solid;
    border-radius: 0.1em
  }
</style>

---

# Guardar los cambios

En el momento que se crea o edita un archivo nuevo se creará un proyecto de trabajo.

Ese será el proyecto de trabajo. El mío es: [https://codesandbox.io/s/eager-shape-108gm](https://codesandbox.io/s/eager-shape-108gm) **Ese será el enlace que tenéis que compartir conmigo**

Una vez abierto este proyecto ir de nuevo al icono de github <mdi-github/>

Pulsar en `Link Sandbox`, a partir de ese momento ya podremos mandar los cambios a nuestro repositorio. 

---
class: text-center
---

# Commit

<mdi-warning/> Es muy importante que mandemos los cambios al repositorio para guardar y compartir el progreso.

![Github commit](/github-commit.jpg)

<style>
  img {
    max-height: 400px;
    margin: 0 auto
  }
</style>


---
layout: section
---

# Día 2

Nuestra primera página

Estructura HTML

---

# Objetivo de la sesión

Crear una web estática con 4 páginas y posibilitar la navegación entre ellas.

<div class="text-center p-10">
  <img src="/site-structure.drawio.svg" class="mx-auto" />
</div>

---

# Archivos de trabajo

Comenzamos creando 4 páginas en la carpeta `src/pages`

- home.astro
- about.astro
- contact.astro
- blog.astro

---

# Estructura de una página básica

Cada página básica consta de una cabecera, un cuerpo y un pie de página.

<div class="text-center">
  <img src="/page-layout.drawio.svg" class="mx-auto max-h-[400px]" />
</div>

---

# Estructura HTML

HTML es un conjunto de etiquetas que nos permite estructurar la información.

Un ejemplo básico de HTML es:

<div class="gap-4 grid grid-cols-[1fr,1fr]">

```html 
<html>
  <head>
    <title>Título de la página</title>
    <!-- Información de la página (no visible) -->
  </head>
  <body>
    <!-- Cuerpo del documento (visible) -->
  </body>
</html>
```

Este código sería el bloque básico para una página web en blanco.

</div>


---

# HTML

Más de 150 etiquetas usaremos unas pocas

Aprenderemos:

<v-clicks>

- `<title>`: Título del sitio
- `<meta>`: Usos especiales como `<meta charset="utf-8" />`
- `<div>`: Bloques
- `<h1>` `<h6>`: Diferentes tipos de título
- `<a>`: Enlaces y atributo `href`
- `<p>`: Párrafos.
- `<ul> <li>`: Listas de elementos.
- `<sytle>`: Estilos

</v-clicks>

<!--
Presentación de las etiquetas disponibles.

- div: bloque
- a: enlaces
- style: estilos
- title: nombre de página
-->


---
layout: center
class: text-center
---

<img class="mx-auto" src="https://catalog-prod-s3-gallerys3-r9e42uos3zkt.s3.amazonaws.com/production/header_images/216b8f2e9f4677058f6fd56fb733f83ffa55fd69.svg?1641833581"/>

En caso de necesidad se puede consultar la información de cada etiqueta en [https://www.w3schools.com/html/default.asp](https://www.w3schools.com/html/default.asp)

---
layout: center
---

# Etiquetas web

Las etiquetas web pueden aparecer de dos formas.

<div class="grid grid-cols-2 gap-4 mb-8">

<div>

Pareja de etiquetas: apertura y cierre

```html
<p> <!-- Etiqueta de apertura -->
  ... <!-- Contenido -->
</p> <!-- Etiqueta de cierre -->
```

</div>

<div>

Con cierre

```html
<!-- Etiqueta sin contenido -->
<img src="./image.png" /> 
  
```

</div>

</div>

### Importante usarlas bien
Es importante cerrar bien las etiquetas o te dará errores la generación de la página

---

# Sección `<header>`

Nos permite definir parámetros de la página, como el idioma, el formato (móvil, escritorio, televisión o impresora) y permite definir información importante para los buscadores, como el nombre de la web y una descripción del sitio web.

Por ahora tened en cuenta que siempre tendréis estas 3 etiquetas: meta, title y style.

```html
  ...
  <head>
      <!-- Permite usar fuentes no inglesas como la ñ o emojis ✨ -->
      <meta charset="utf-8" />
      <title>Título de la página</title>
      <style>
        <!-- Por ahora dejaremos en blanco esta sección -->
      </style>
  </head>
  ...
```



---
layout: section
---

# Página Home

Muestra el nombre del sitio y un resumen de las diferentes secciones

---

# Cabecera

Común en las tres páginas.

<div class="text-center p-10">
  <img src="/header.drawio.svg" class="mx-auto" />
</div>

Atención, por ahora nos centramos en los elementos no en cómo se dibujan.

---

# Bloque de cabecera

Todos los bloques se organizan en cajas independientes, así podremos darle un estilo común.

<div class="text-4xl pt-4 pb-4">

`<div>...</div>`

</div>

Y les damos nombre, para identificarlos.

```html
<div id="header">
  <div id="logo">
    <!-- Aquí irá el logo -->
  </div>
  <div id="menu">
    <!-- Aquí irá el listado de opciones -->
  </div>
</div> <!-- header -->
```

---

# Logo

Para poder mostrar una imagen primero tenemos que cargarla en la carpeta `public` recomiendo que sea de un tamaño pequeño por ejemplo 80px de alto y 200px de ancho.

Utilizamos la etiqueta 

<div class="text-4xl pt-4 pb-4">

`<img src="/logo.png" />`

</div>

- Observa que la etiqueta se autocierra.
- En el atributo src hay que poner la dirección a la imagen. 
- También observa que la dirección va entre comillas dobles <b>"</b>


---

# Menú superior

El menú superior tiene dos elementos a tener en cuenta. Por un lado organizamos los nombres en una lista. Y después cada elemento de la lista es además un enlace que nos permite acceder a otras páginas.

Comenzmos con la lista.

<div class="grid grid-cols-2 gap-8" >

  <div>

```html
    <ul>
      <li>Elemento 1</li>
      <li>Elemento 2</li>
      <li>Elemento 3</li>
    </ul>
```

  </div>

  <div>

<ul>
<li>Elemento 1</li>
<li>Elemento 2</li>
<li>Elemento 3</li>
</ul>

  </div>

</div>

- El nombre de la etiqueta `<ul>` viene de <b>unordered list</b> (lista desordenada)
- El nombre de la etiqueta `<li>` viene de <b>list item</b> (elemento de lista)

---

# Menú superior - Enlaces

Para crear un enlace en HTML usamos la etiqueta a.

<div class="text-4xl pt-4 pb-4">

`<a href="/about">Texto de enlace</a>`

</div>

Fíjate que ponemos dentro del atributo `href` el nombre de la página a la que queremos acceder.

<div class="grid grid-cols-2 gap-4" >

Aquí se muestra un ejemplo incompleto para que lo incluyas en tu página.

```html
    <ul>
      <li>
        <a href="/about">Acerca de</a>
      </li>
      <li>
        ...
      </li>
      <li>
        ...
      </li>
    </ul>
```

</div>

---

# Un menú en cada página

Asegúrate de conseguir que puedas navegar entre todas las páginas.

- Copia el html básico en todas las páginas.
- Crea la cabecera completa en la página `Home.astro` dentro de la sección `<body>`
- Para accede de nuevo a la página Home habrá que pinchar en el logotipo, puedes usar el siguiente código.
```html
<a href="/Home">
  <img src="/logo.png"/>
</a>
```
- Modifica en cada página el título de la página como en el ejemplo que pondríamos en la página `About.astro`.
```html
<title>AI! que arte! - Acerca de...</title>
```

---

# Sección de contenido

Cada página tendrá un bloque de contenido que irá a continuación de la cabecera.

```html
<div class="main">
  <h1>Página principal</h1>
  <p>Párrafo de la página principal</p>
</div>
```
- Incluye esta sección en cada página y modifica el texto que corresponda.

---

# Pie de página

Cada página tendrá un bloque de pie de página que irá a continuación del bloque principal.

```html
<div class="foot">
  <p>Proyecto para la asignatura de Tecnologías de la Información I de Escuela IDEO</p>
  <p>Autor de la página: Nombre e Inicial</p>
  
  <div class="links">
    <ul>
      <li>Acerca de</li>
      <li>Contacto</li>
      <li>Texto legal</li>
    </ul>
  </div>
</div>
```
- Modifica el texto que corresponda.
- Incluye esta sección en cada página.


