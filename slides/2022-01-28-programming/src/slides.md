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

# Programación de CSS

---
layout: two-cols
---

# Tarea anterior

Construcción de una web con 4 páginas enlazadas entre sí.

Es posible acceder al código completo del proyecto tal y como debería estar en el repositorio:

[https://github.com/diegogd/tic-end-session1](https://github.com/diegogd/tic-end-session1)

::right::

![](/web_session1.jpg)

---

# Cambio de CodeSandbox a Stackblitz

[Instrucciones](https://youtu.be/peWQEfJ1l0U) enviadas por correo electrónico para transferir tu proyecto.

Puede usarse este enlace para comenzar a trabajar desde la versión de github de como debería estar el proyecto.

[https://stackblitz.com/github/diegogd/tic-end-session1](https://stackblitz.com/github/diegogd/tic-end-session1)


### Motivos del cambio:
- Problemas al recuperar trabajo previo.
- Complicación en la integración de github, más sencillo con Stackblitz.
- Problemas al refrescar los cambios en el visor.

---
layout: quote
---

# Objetivo de la semana

Hacer uso de css para controlar la estética de la web

---
layout: quote
---

# Producto al final de la semana

- Plantilla base de CSS para comenzar a crear nuestro diseño.
- 4 páginas con estilo
- Diferenciar cabecera/cuerpo/pie

---
layout: two-cols
---

# ¿Qué es CSS?

Cascade Style Sheets

[Referencia CSS](https://www.w3schools.com/css/default.asp)

Permite configurar todos los aspectos visuales de un elemento HTML: color, borde, márgenes, fuente, espacios, tamaño...

```html
<p class="p1">Párrafo 1</p>
<p class="p2">Párrafo 2</p>
<p class="p3">Párrafo 3</p>
<p class="p4">Párrafo 4</p>
```

<p class="p1">Párrafo 1</p>
<p class="p2">Párrafo 2</p>
<p class="p3">Párrafo 3</p>
<p class="p4">Párrafo 4</p>

::right::

La definición de estilos sería: 

```css
<style>
  .p1 {
    font-size: 0.5em;
    text-align: center;
  }
  .p2 {
    font-size: 0.7em;
    border: 1px solid gray;
  }
  .p3 {
    font-size: 1em;
    color: #ff0000;
  }
  .p4 {
    font-size: 1.2em;
    font-weight: bolder;
  }
</style>
```

<style>
  .p1 {
    font-size: 0.5em;
    text-align: center;
  }
  .p2 {
    font-size: 0.7em;
    border: 1px solid gray;
  }
  .p3 {
    font-size: 1em;
    color: #ff0000;
  }
  .p4 {
    font-size: 1.2em;
    font-weight: bolder;
  }
</style>

---

# ¿Cómo sé que etiqueta usar?

- Busca con google cuando lo tengas claro.
- Usa figma cuando tengas un diseño.
- Utiliza el inspector del navegador cuando quieras copiar un estilo de una web. (click con el botón derecho en navegador)

<img src="/css_inspector.jpg" style="max-height: 300px" class="mx-auto" />

---

# Dónde usar los estilos

- Uso directo sobre una etiqueta.

<div class="grid grid-cols-2 gap-4">

```html
<div style="background: #333; color: white">
Texto con fondo gris
</div>
```

<div style="background: #333; color: white; padding: 1em;">
Texto con fondo gris
</div>

</div>

- Nombrar un elemento con clase o id (detalle a continuación) y darle estilo después.
  
```html
<div class="article">...</div>
```
  
```html
<div id="foot">...</div>
```

- No modificar el código HTML y aplicar el estilo sobre etiquetas concretas.

---

# Nombres con clase `class`

Se utiliza cuando en la página hay muchos elementos similares, como un artículo, botón, enlace o párrafo.

<div class="grid grid-cols-2 gap-4">

```html
<div>
  <div class="button">Botón 1</div>
  <div class="button">Botón 2</div>
  <div class="button">Botón 3</div>
</div>
```

```css
.button {
  padding: 1em;
  background: #eee;
  border: 1px solid #aaa;
}
```

</div>

<div class="flex flex-row gap-4 mt-4">
  <div class="button">Botón 1</div>
  <div class="button">Botón 2</div>
  <div class="button">Botón 3</div>
</div>

<style>
  .button {
    padding: 1em;
    background: #eee;
    border: 1px solid #aaa;
  }
  
</style>

---

# Nombres con ID

Se utiliza cuando en la página hay un único elemento de ese tipo: cabecera, pie de página, bloque principal.

<div class="flex flex-row gap-6">

```html
<div id="menu">
  <div class="button">Botón 1</div>
  <div class="button">Botón 2</div>
  <div class="button">Botón 3</div>
</div>
```

```css
#menu {
  border: 4px dashed red;
  background: linear-gradient(0deg, #46725a 0%, #558b6d 100%);
  padding: 2em;
}
```

</div>

<div id="menu" class="flex flex-row gap-4 mt-4">
  <div class="button">Botón 1</div>
  <div class="button">Botón 2</div>
  <div class="button">Botón 3</div>
</div>

<style>
  .button {
    padding: 1em;
    background: #eee;
    border: 1px solid #aaa;
  }

  #menu {
    border: 4px dashed red;
    background: linear-gradient(0deg, #46725a 0%, #558b6d 100%);
    padding: 2em;
  }
  
</style>

---

# Nombres sobre elementos HTML

Se utiliza cuando se quiere cambiar el estilo de un elemento.

<div class="flex flex-row gap-6">

```html
<a href="link">Enlace a página</a>
```

```css
a {
    font-family: courier;
    border-color: #C2CC00;
    color: #FF934F;
    border-style: dashed;
    border-bottom-width: 4px;
}
```
</div>

- <a href="" class="reset">Enlace con formato por defecto</a>
- <a href="" class="change">Enlace con formato personalizado</a>

<style>
  a.reset {
    color: blue;
    border-style: inherit;
  }
  a.change {
    font-family: courier;
    border-color: #C2CC00;
    color: #FF934F;
    border-style: dashed;
    border-bottom-width: 4px;
  }
  
</style>

---

# ¿Dónde poner el css cuando no se pone en la etiqueta?

Cuando no usamos el atributo `style` como en el siguiente caso

```html
<p style="font-size: 2em">Texto grande</p>
```
Tenemos que poner el código css en uno de estos dos sitios, o en ambos:

- Archivo `styles.css` (nos permite compartirlo)
- Etiqueta `style` en el HTML (sólo aplica en la página)

---
layout: cover
---

# Manos a la obra
Dando estilo a nuestra página

---

# Centramos el trabajo en blog

Blog es una página que tiene todos los elementos que podremos dar formato.

En la 3ª sesión de diseño comenzaréis a desarrollar la hoja de estilos para incluir en la página y que podamos usar en diferentes sitios. Pero por ahora trabajamos en un bloque `<style>`

En la cabecera de blog localiza este bloque

```html
<style>

</style>
```

A partir de ahora vamos a trabajar todo en este bloque.

---

# Receta mágica

HTML ha evolucionado mucho en las últimos años, pero sigue heredando algunos estilos raros por compatibilidad.

Para evitar problemas futuros comienza usando este bloque, ponlo arriba del todo y lo que vayamos incluyendo debajo.

```css
*, body {  
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

Este pequeño cambio verás que influye en el texto de la web.

---

# Bloque de cabecera - color

Comenzamos dando formato al bloque de la cabecera. Si recuerdas es un bloque que queremos ver en horizontal y que se diferencie del resto.

```css
#header {
  background-color: #eee;
  width: 100%;
}
```

<img src="/header_1.jpg"/>

---

# Bloque de cabecera - orientación

Comenzamos dando formato al bloque de la cabecera. Si recuerdas es un bloque que queremos ver en horizontal y que se diferencie del resto.

```css
#header {
  ...
  display: grid;
  grid-template-columns: 250px 1fr;
}
```

<img src="/header_2.jpg" class="mt-2 mx-auto" />

---

# Bloque de menú - orientación

Editamos en combinación el bloque menú y la etiqueta ul.

```css
#menu ul {
  display: flex;
  justify-content: end;
  gap: 1em;
}
```

<img src="/header_3.jpg" class="mt-2 mx-auto" />

---

# Bloque de menú - ajustes

Quitamos el bullet que viene por defecto y damos algo de espacio.

```css
#menu ul li {
  list-style: none;
  padding: 0.5em;
}
```

<img src="/header_4.jpg" class="mt-2 mx-auto" />

---

# Pie de página

Bloque similar a la cabecera, pero fíjate que el código usar class.

```html
...
<div class="foot">
  <p>Proyecto para la asignatura de Tecnologías de la Información I de Escuela IDEO</p>
  ...
```

Intenta cambiar el color de fondo a un color oscuro. Como el de la ilustración.

<img src="/foot_1.jpg" class="mt-2 mx-auto" />

---

# Pie de página - Contraste de texto

Añadimos contraste para que quede mejor el texto.

```css
.foot {
  ...
  color: white;
}

.foot a {
  color: yellow;
}
```

<img src="/foot_2.jpg" class="mt-2 mx-auto" />

---

# Pie de página - Espacio

Ahora prueba con el atributo `padding` y el ejemplo del listado de la cabecera dar estilo a tu pie para que se parezca a algo parecido a esto.

<img src="/foot_3.jpg" class="mt-2 mx-auto" />

Para saber cómo [alinear el texto accede al ejemplo](https://www.w3schools.com/cssref/pr_text_text-align.asp). 

---

# Margen

Por último investiga sobre estas propiedades para dar estilo al bloque principal del blog.

- [Fuentes de caracteres](https://www.w3schools.com/cssref/pr_font_font-family.asp)
- [Márgenes en párrafos](https://www.w3schools.com/css/css_margin.asp)
- [Colores en elementos](https://www.w3schools.com/css/css_colors.asp)
- [Unidades de medida](https://www.w3schools.com/css/css_units.asp)

---

# Resultado final

<img src="/page_1.jpg" class="mt-2 mx-auto" style="max-height: 400px" />

---

# Mejoras valorables

- Incluir los estilos en todas las páginas.
- Explorar nuevos elementos css
