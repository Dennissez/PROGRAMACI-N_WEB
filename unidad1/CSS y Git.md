# PROGRAMACIÓN WEB / DISEÑO WEB

## MANUAL DE ESTUDIO 2: INTRODUCCIÓN A CSS Y CONTROL DE VERSIONES CON GIT (ME_2)

* **Asignatura:** Diseño Web / Programación Web
* **Unidad N° 1:** Introducción a HTML y CSS: Fundamentos para el Desarrollo Web (Semana 2)
* **Temario:** Conceptos de CSS, formas de inclusión (interno, externo, en línea), selectores (etiqueta, ID, clase, negación), propiedades básicas de diseño y texto, e introducción práctica a Git y plataformas en la nube.

---

## 🧭 Tabla de Contenidos

1. [¿Qué es CSS?](#1-qué-es-css)
2. [Formas de Incorporar CSS en HTML](#2-formas-de-incorporar-css-en-html)
   * [2.1 CSS Interno o Incrustado](#21-css-interno-o-incrustado)
   * [2.2 CSS Externo (Recomendado)](#22-css-externo-recomendado)
   * [2.3 CSS en Línea](#23-css-en-línea)
3. [Selectores en CSS](#3-selectores-en-css)
   * [3.1 Selector de Etiqueta](#31-selector-de-etiqueta)
   * [3.2 Selector por ID (`#`)](#32-selector-por-id-)
   * [3.3 Selector por Clase (`.`)](#33-selector-por-clase-)
   * [3.4 Selector por Clase Negada (`:not()`)](#34-selector-por-clase-negada-not)
4. [Propiedades Básicas de Estilo y Formato](#4-propiedades-básicas-de-estilo-y-formato)
   * [4.1 Propiedades Estructurales](#41-propiedades-estructurales)
   * [4.2 Propiedades de Texto y Tipografía](#42-propiedades-de-texto-y-tipografía)
   * [4.3 Comentarios en CSS](#43-comentarios-en-css)
5. [Control de Versiones con Git](#5-control-de-versiones-con-git)
   * [5.1 Conceptos Fundamentales](#51-conceptos-fundamentales)
   * [5.2 Comandos Esenciales de Git](#52-comandos-esenciales-de-git)
6. [Plataformas de Repositorios en la Nube](#6-plataformas-de-repositorios-en-la-nube)
7. [Reflexión y Buenas Prácticas](#7-reflexión-y-buenas-prácticas)

---

## 1. ¿Qué es CSS?

**CSS** (*Cascading Style Sheets* o Hojas de Estilo en Cascada) es el lenguaje estándar utilizado para definir la presentación y el aspecto visual de un documento estructurado en HTML.

* **Separación de responsabilidades:** Permite desacoplar la estructura y semántica de los datos (HTML) de la capa visual y estética (CSS).
* **Consistencia:** Facilita la aplicación uniforme de colores, fuentes, márgenes y distribuciones espaciales en todo un sitio web desde una única hoja centralizada.
* **Control selectivo:** A través de selectores, identifica con precisión los elementos específicos a estilizar.

---

## 2. Formas de Incorporar CSS en HTML

### 2.1 CSS Interno o Incrustado

Se declara dentro de la etiqueta `<style>` en el `<head>` del documento HTML. Es útil para páginas individuales, pero poco escalable para sitios de múltiples vistas.

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Ejemplo CSS Interno</title>
    <style>
        body {
            background-color: lightblue;
        }
        h1 {
            color: red;
            text-align: center;
        }
    </style>
</head>
<body>
    <h1>Título de la página</h1>
    <p>Este es un párrafo de ejemplo.</p>
</body>
</html>
```

### 2.2 CSS Externo (Recomendado)

Las reglas se redactan en un archivo independiente con extensión `.css` y se vinculan al documento HTML mediante la etiqueta `<link>` en el `<head>`. Es la buena práctica por excelencia en el desarrollo profesional.

**Archivo `index.html`:**
```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Ejemplo CSS Externo</title>
    <link rel="stylesheet" type="text/css" href="estilos.css">
</head>
<body>
    <h1>Título de la página</h1>
    <p>Este es un párrafo de ejemplo.</p>
</body>
</html>
```

**Archivo `estilos.css`:**
```css
body {
    background-color: lightblue;
}

h1 {
    color: red;
    text-align: center;
}
```

### 2.3 CSS en Línea

Se asigna de forma directa a una etiqueta HTML mediante el atributo global `style`. Tiene la máxima prioridad de cascada, pero dificulta la mantenibilidad del proyecto.

```html
<h1 style="color: red; text-align: center;">Título de la página</h1>
<p style="font-size: 16px;">Este es un párrafo de ejemplo.</p>
```

---

## 3. Selectores en CSS

### 3.1 Selector de Etiqueta

Afecta a todos los elementos del documento que coincidan con la etiqueta indicada.

```css
p {
    color: green;
}
```

### 3.2 Selector por ID (`#`)

Apunta a un único elemento mediante su atributo `id`. Se escribe antecedido por el símbolo `#`. Debe ser exclusivo dentro del mismo documento HTML.

```html
<div id="titulo">
    <h1>Bienvenido</h1>
</div>
```

```css
#titulo {
    background-color: blue;
    color: white;
    padding: 10px;
}
```

### 3.3 Selector por Clase (`.`)

Apunta a uno o más elementos que compartan la misma clase en su atributo `class`. Se escribe antecedido por un punto (`.`).

```html
<p class="destacado">Párrafo destacado 1</p>
<p>Párrafo común</p>
<p class="destacado">Párrafo destacado 2</p>
```

```css
.destacado {
    color: red;
    font-weight: bold;
}
```

### 3.4 Selector por Clase Negada (`:not()`)

Aplica estilos a todos los elementos que no posean la clase especificada.

```css
p:not(.destacado) {
    font-style: italic;
}
```

---

## 4. Propiedades Básicas de Estilo y Formato

### 4.1 Propiedades Estructurales

| Propiedad | Propósito | Valores y Formatos | Ejemplo |
| :--- | :--- | :--- | :--- |
| `background-color` | Color de fondo del elemento. | Nombres (`yellow`), Hexadecimal (`#FF0000`), RGB (`rgb(0, 128, 255)`). | `background-color: #f4f4f4;` |
| `border` | Define contorno del elemento. | `[grosor] [estilo] [color]` (solid, dashed, dotted, double). | `border: 2px dashed blue;` |

### 4.2 Propiedades de Texto y Tipografía

| Propiedad | Propósito | Valores y Formatos | Ejemplo |
| :--- | :--- | :--- | :--- |
| `color` | Color del texto. | Nombres, Hexadecimal, RGB. | `color: red;` |
| `text-align` | Alineación horizontal del texto. | `left`, `right`, `center`, `justify`. | `text-align: center;` |
| `font-family` | Familia tipográfica. | Nombres de fuente con respaldo genérico. | `font-family: "Arial", sans-serif;` |
| `font-size` | Tamaño de la fuente. | Píxeles (`px`), puntos (`pt`), unidades relativas (`em`, `rem`). | `font-size: 16px;` |

### 4.3 Comentarios en CSS

Permiten documentar o inhabilitar reglas temporales. Son ignorados por el navegador:

```css
/* Este es un comentario en CSS */
.caja {
    /* border: 1px solid black; */
    padding: 20px;
}
```

---

## 5. Control de Versiones con Git

**Git** es un sistema de control de versiones distribuido (*DVCS*) creado por Linus Torvalds en 2005. Registra el historial evolutivo de los archivos y permite el trabajo paralelo mediante ramas (*branches*).

```
Directorio de Trabajo  ──►  [ git add ]  ──►  Área de Preparación (Staging)  ──►  [ git commit ]  ──►  Historial (.git)
```

### 5.2 Comandos Esenciales de Git

| Comando | Acción Principal |
| :--- | :--- |
| `git init` | Inicializa un repositorio Git local vacío. |
| `git clone <url>` | Clona un repositorio remoto en el equipo local. |
| `git status` | Muestra el estado del árbol de trabajo (archivos modificados o pendientes). |
| `git add <archivo>` | Agrega archivos al área de preparación (*staging area*). |
| `git commit -m "mensaje"` | Registra permanentemente los cambios en el historial local. |
| `git log` | Muestra la cronología de commits realizados. |
| `git branch` | Lista las ramas disponibles en el repositorio. |
| `git checkout <rama>` | Cambia de rama de trabajo. |
| `git pull` | Descarga e integra cambios desde el repositorio remoto. |
| `git push` | Envía los commits locales confirmados al repositorio remoto. |

---

## 6. Plataformas de Repositorios en la Nube

* **GitHub:** La mayor plataforma para proyectos de código abierto y privados, con soporte para issues, pull requests y GitHub Actions.
* **GitLab:** Enfocada en soluciones integrales de desarrollo con potentes pipelines de CI/CD nativos.
* **Bitbucket:** Plataforma de Atlassian pensada para el trabajo corporativo e integración con Jira y Trello.
* **Azure DevOps:** Suite integral de desarrollo de Microsoft para gestión del ciclo de vida de software en la nube.

---

## 7. Reflexión y Buenas Prácticas

1. **Priorizar CSS externo:** Mantener los estilos en archivos `.css` independientes para reducir redundancia y permitir que el navegador guarde en caché las reglas.
2. **Uso responsable de IDs y clases:** Usar clases (`.`) para estilos reutilizables y reservar los IDs (`#`) únicamente para identificadores estructurales únicos o anclas.
3. **Frecuencia de commits en Git:** Realizar commits pequeños y con mensajes descriptivos para que el historial sea claro y fácil de auditar o revertir.
