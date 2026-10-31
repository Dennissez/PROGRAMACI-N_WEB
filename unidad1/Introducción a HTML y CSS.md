# DISEÑO WEB / PROGRAMACIÓN WEB

## Unidad N° 1: INTRODUCCIÓN A HTML Y CSS: FUNDAMENTOS PARA EL DESARROLLO WEB (Manual ME_1)

* **Asignatura:** Diseño Web / Programación Web
* **Unidad N° 1:** Introducción a HTML y CSS (Semana 1)
* **Temario:** Definición de HTML, Editores e IDE, Estructura básica de un documento, Etiquetas fundamentales, Formularios, Tablas y Comentarios.

---

## 🧭 Tabla de Contenidos

1. [¿Qué es HTML?](#1-qué-es-html)
2. [Herramientas de Desarrollo: Editores de Texto e IDEs](#2-herramientas-de-desarrollo-editores-de-texto-e-ides)
3. [Estructura Básica de un Documento HTML5](#3-estructura-básica-de-un-documento-html5)
4. [El Encabezado: Elemento `<head>`](#4-el-encabezado-elemento-head)
5. [El Cuerpo: Elemento `<body>`](#5-el-cuerpo-elemento-body)
6. [Etiquetas Básicas de Estructuración y Contenido](#6-etiquetas-básicas-de-estructuración-y-contenido)
   - [6.1 Contenedor Genérico `<div>`](#61-contenedor-genérico-div)
   - [6.2 Párrafos `<p>`](#62-párrafos-p)
   - [6.3 Encabezados Jerárquicos `<h1>` a `<h6>`](#63-encabezados-jerárquicos-h1-a-h6)
   - [6.4 Hipervínculos `<a>`](#64-hipervínculos-a)
7. [Datos Tabulares: `<table>`, `<tr>`, `<td>` y `<th>`](#7-datos-tabulares-table-tr-td-y-th)
8. [Formularios Web: `<form>`, `<input>`, `<label>` y Botones](#8-formularios-web-form-input-label-y-botones)
9. [Comentarios en HTML](#9-comentarios-en-html)
10. [Reflexión y Buenas Prácticas de Accesibilidad](#10-reflexión-y-buenas-prácticas-de-accesibilidad)

---

## 1. ¿Qué es HTML?

**HTML** son las siglas de **HyperText Markup Language** (*Lenguaje de Marcado de Hipertexto*). Es el estándar universal desarrollado originalmente por Tim Berners-Lee en 1990 para dar estructura, formato y sentido al contenido disponible en la World Wide Web (WWW).

* **Hipertexto:** Permite enlazar documentos, recursos multimedia, páginas externas o anclas internas de forma no lineal a través de hipervínculos.
* **Lenguaje de Marcado:** No es un lenguaje de programación (no maneja algoritmos ni lógica imperativa directa); funciona delimitando fragmentos de texto mediante **etiquetas** (*tags*) encerradas entre corchetes angulares (`<` y `>`).
* **Regla general de sintaxis:** Casi todos los elementos se componen de:
  1. Etiqueta de apertura: `<nombre_etiqueta>`
  2. Contenido del elemento
  3. Etiqueta de cierre: `</nombre_etiqueta>`

---

## 2. Herramientas de Desarrollo: Editores de Texto e IDEs

Para escribir y probar código HTML se utilizan diversas herramientas clasificadas en editores ligeros e IDEs completos:

| Herramienta | Tipo | Características Principales |
| :--- | :--- | :--- |
| **Apache NetBeans** | IDE Completo | Entorno integrado, autocompletado avanzado, gestión de proyectos y servidor embebido para pruebas locales. Requiere tener instalado el JDK (ej. Amazon Corretto). |
| **Notepad++** | Editor Ligero | Software libre para Windows, coloreado de sintaxis, muy rápido para inspección o edición rápida de archivos `.html`. |
| **Visual Studio Code** | Editor Moderno | Ampliamente utilizado en la industria, ecosistema extensible con plugins de previsualización en vivo (ej. Live Server). |

---

## 3. Estructura Básica de un Documento HTML5

Todo documento HTML moderno sigue una estructura jerárquica obligatoria compuesta por el doctype, la raíz `<html>`, la cabecera `<head>` y el cuerpo `<body>`:

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi primera página web</title>
</head>
<body>
    <div>Hola Mundo</div>
</body>
</html>
```

* `<!DOCTYPE html>`: Informa al navegador web que el documento debe interpretarse bajo el estándar moderno de **HTML5**.
* `<html lang="es">`: Elemento raíz que envuelve todo el documento e indica el idioma principal del contenido.

---

## 4. El Encabezado: Elemento `<head>`

El elemento `<head>` alberga los **metadatos** (información sobre la página) y las referencias a recursos externos que el navegador necesita para renderizar la página. Su contenido **no es visible directamente** dentro de la ventana de visualización:

```html
<head>
    <!-- Define la codificación de caracteres (tildes, caracteres especiales y ñ) -->
    <meta charset="UTF-8">
    
    <!-- Configura la escala y el viewport para diseño adaptable (Responsive) -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- Texto visible en la pestaña del navegador -->
    <title>Título de la página</title>
    
    <!-- Vinculación a hoja de estilos CSS externa -->
    <link rel="stylesheet" href="styles.css">
</head>
```

---

## 5. El Cuerpo: Elemento `<body>`

El elemento `<body>` contiene **todo el contenido visual e interactivo** que el usuario final visualiza e interactúa en el navegador: títulos, párrafos, tablas, imágenes, enlaces y formularios.

```html
<body>
    <h1>Título Principal</h1>
    <p>Este es un párrafo de bienvenida a la plataforma.</p>
    <a href="https://www.iplacex.cl">Ir al sitio institucional</a>
</body>
```

---

## 6. Etiquetas Básicas de Estructuración y Contenido

### 6.1 Contenedor Genérico `<div>`
* Elemento de bloque sin carga semántica intrínseca.
* Se emplea para agrupar otros elementos relacionados, aplicar estilos CSS conjuntos o manipular fragmentos de la interfaz mediante JavaScript:

```html
<div id="contenedor-principal">
    <h2>Encabezado de Sección</h2>
    <p>Párrafo contenido dentro del bloque agrupador.</p>
</div>
```

### 6.2 Párrafos `<p>`
* Elemento de bloque diseñado para presentar bloques de texto continuo.
* Genera un margen o espacio vertical predeterminado antes y después del elemento para separar el flujo de lectura.

```html
<p>Este es el primer párrafo de descripción del producto.</p>
<p>Este es un segundo párrafo separado semánticamente del anterior.</p>
```

### 6.3 Encabezados Jerárquicos `<h1>` a `<h6>`
Proporcionan una estructura jerárquica clara para los usuarios y los motores de búsqueda (SEO):
* `<h1>`: Título de máxima jerarquía (generalmente uno solo por documento).
* `<h2>` a `<h6>`: Subtítulos en orden descendente de importancia.

```html
<h1>Reporte General de Ventas</h1>
<h2>Región Metropolitana</h2>
<h3>Sucursal Santiago Centro</h3>
```

### 6.4 Hipervínculos `<a>`
Crea enlaces hacia otras páginas web, documentos o anclas en la misma página mediante el atributo `href`:

```html
<!-- Enlace externo -->
<a href="https://www.ejemplo.com" target="_blank">Visitar Sitio Externo</a>

<!-- Enlace interno a una sección de la misma página mediante ID -->
<a href="#contacto">Ir al formulario de contacto</a>
...
<h2 id="contacto">Formulario de Contacto</h2>
```

---

## 7. Datos Tabulares: `<table>`, `<tr>`, `<td>` y `<th>`

Para organizar y desplegar información estructurada en filas y columnas se emplean las etiquetas tabulares:

* `<table>`: Contenedor principal de la tabla.
* `<tr>` (*Table Row*): Define una fila completa.
* `<th>` (*Table Header*): Celda de encabezado (texto en negrita y centrado por defecto).
* `<td>` (*Table Data*): Celda con datos estándar.

```html
<table border="1">
    <tr>
        <th>Nombre</th>
        <th>Edad</th>
        <th>Ciudad</th>
    </tr>
    <tr>
        <td>John Doe</td>
        <td>30</td>
        <td>Santiago</td>
    </tr>
    <tr>
        <td>Jane Smith</td>
        <td>25</td>
        <td>Valparaíso</td>
    </tr>
</table>
```

---

## 8. Formularios Web: `<form>`, `<input>`, `<label>` y Botones

Los formularios permiten recolectar datos introducidos por el usuario y enviarlos a un servidor para su procesamiento:

```html
<form action="/procesar-datos" method="POST">
    <!-- Etiqueta vinculada al campo mediante el atributo 'for' e 'id' -->
    <label for="nombre">Nombre de Usuario:</label>
    <input type="text" id="nombre" name="nombre_usuario" placeholder="Ej: Juan Pérez" required>
    
    <label for="correo">Correo Electrónico:</label>
    <input type="email" id="correo" name="correo_electronico" required>
    
    <!-- Botones de control del formulario -->
    <input type="submit" value="Enviar Datos">
    <input type="reset" value="Restablecer">
</form>
```

### Atributos Clave de Formularios:
* `for` (en `<label>`): Enlaza el texto descriptivo con el `id` del `<input>`, permitiendo que al hacer clic en el texto el cursor se posicione en la casilla.
* `type`: Define la naturaleza del control (`text`, `email`, `password`, `submit`, `reset`, `checkbox`, `radio`).
* `required`: Obliga al usuario a completar el campo antes de permitir el envío.
* `placeholder`: Texto tenue de sugerencia dentro de la casilla antes de escribir.

---

## 9. Comentarios en HTML

Los comentarios sirven para documentar el código o deshabilitar temporalmente fragmentos sin eliminarlos. **No se renderizan en la pantalla del navegador**:

```html
<!-- Este es un comentario de una sola línea -->

<!-- 
    <div>
        <p>Este bloque está temporalmente deshabilitado</p>
    </div>
-->
```

---

## 10. Reflexión y Buenas Prácticas de Accesibilidad

1. **Uso de etiquetas `<label>`:** Garantiza que los lectores de pantalla para usuarios con discapacidad visual puedan describir correctamente el propósito de cada campo.
2. **Semántica apropiada:** No usar encabezados (`<h1>` - `<h6>`) solo para cambiar el tamaño visual del texto; para el diseño se debe utilizar CSS, reservando las etiquetas HTML para su propósito semántico y estructural.
