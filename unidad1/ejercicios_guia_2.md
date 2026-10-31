# PROGRAMACIÓN WEB / DISEÑO WEB

## GUÍA PRÁCTICA 2: INTEGRACIÓN DE HTML SEMÁNTICO Y CSS EXTERNO (R_2)

* **Asignatura:** Programación Web / Diseño Web
* **Unidad N° 1:** Introducción a HTML y CSS: Fundamentos para el Desarrollo Web (Semana 2)
* **Objetivo:** Aplicar estilos visuales mediante hojas de estilo CSS externas (`.css`), reconociendo selectores de etiqueta, clase, pseudo-clases, diseño adaptable y estructuración semántica con HTML5.

---

## 🧭 Tabla de Contenidos

1. [Visión General](#1-visión-general)
2. [Ejercicio 1: Sitio Comercial "Mi Tienda en Línea"](#2-ejercicio-1-sitio-comercial-mi-tienda-en-línea)
   * [2.1 Código HTML (`index.html`)](#21-código-html-indexhtml)
   * [2.2 Hoja de Estilos CSS (`styles.css`)](#22-hoja-de-estilos-css-stylescss)
3. [Ejercicio 2: Blog Gastronómico "Mis Recetas de Cocina"](#3-ejercicio-2-blog-gastronómico-mis-recetas-de-cocina)
   * [3.1 Código HTML (`index.html`)](#31-código-html-indexhtml-1)
   * [3.2 Hoja de Estilos CSS (`style.css`)](#32-hoja-de-estilos-css-stylecss)
4. [Conceptos Técnicos Aplicados](#4-conceptos-técnicos-aplicados)

---

## 1. Visión General

La actividad práctica de la Semana 2 se enfoca en la separación de estructura y presentación visual mediante el uso de **CSS Externo**, enlazando los archivos mediante la etiqueta `<link rel="stylesheet">` en el `<head>`.

### Requisito de Ubicación de Archivos
Para que los estilos se apliquen correctamente sin configurar rutas relativas complejas, ambos archivos deben residir en la misma carpeta:

```text
📁 proyecto_web/
├── index.html
└── styles.css (o style.css)
```

---

## 2. Ejercicio 1: Sitio Comercial "Mi Tienda en Línea"

### 2.1 Código HTML (`index.html`)

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Tienda en Línea</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Bienvenido a Mi Tienda en Línea</h1>
    </header>
    <main>
        <section>
            <p>En nuestra tienda en línea encontrarás una amplia variedad de productos de alta calidad.</p>
        </section>
        <section>
            <h2>Categorías de Productos</h2>
            <ul>
                <li>Ropa</li>
                <li>Zapatos</li>
                <li>Electrónicos</li>
                <li>Hogar y Jardín</li>
                <li>Juguetes</li>
            </ul>
        </section>
    </main>
</body>
</html>
```

### 2.2 Hoja de Estilos CSS (`styles.css`)

```css
/* styles.css */
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f5f5f5;
}

header {
    background-color: #333;
    color: #fff;
    padding: 1rem;
    text-align: center;
}

h1 {
    margin: 0;
    font-size: 36px;
    color: #ff6600;
}

main {
    max-width: 800px;
    margin: 0 auto;
    padding: 1rem;
}

section {
    margin-bottom: 2rem;
}

h2 {
    color: #333;
    border-bottom: 1px solid #ccc;
    padding-bottom: 0.5rem;
}

p {
    line-height: 1.6;
    background-color: #f9f9f9;
    padding: 10px;
}

ul {
    list-style: none;
    padding: 0;
}

li {
    margin-bottom: 0.5rem;
}
```

---

## 3. Ejercicio 2: Blog Gastronómico "Mis Recetas de Cocina"

### 3.1 Código HTML (`index.html`)

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mis Recetas de Cocina</title>
    <link href="style.css" rel="stylesheet" type="text/css"/>
</head>
<body>
    <header>
        <h1>Mis Recetas de Cocina</h1>
    </header>

    <div class="container">
        <!-- Receta 1: Pasta Alfredo -->
        <section class="recipe">
            <h1>Pasta Alfredo</h1>
            <img src="https://images.aws.nestle.recipes/original/432d4cbae30cd055066e6fa44cf0897c_Overhead_Pasta_Can_2020_HERO.jpg" alt="Pasta Alfredo">
            <ul>
                <li class="important">200g de pasta fettuccine</li>
                <li>1 taza de crema de leche</li>
                <li>1/2 taza de queso parmesano rallado</li>
                <li>2 cucharadas de mantequilla</li>
                <li>Sal y pimienta al gusto</li>
            </ul>
            <p>
                1. Cocina la pasta fettuccine en agua con sal hasta que esté al dente. Escúrrela y reserva.<br>
                2. En una sartén grande, derrite la mantequilla a fuego medio. Agrega la crema de leche y mezcla bien.<br>
                3. Incorpora el queso parmesano rallado y mezcla hasta que se derrita y se forme una salsa cremosa.<br>
                4. Añade la pasta cocida a la salsa y revuelve para que se impregne bien.<br>
                5. Sazona con sal y pimienta al gusto. Sirve caliente y disfruta.
            </p>
        </section>

        <!-- Receta 2: Ensalada de Frutas -->
        <section class="recipe">
            <h1>Ensalada de Frutas</h1>
            <img src="https://recetasdecocina.elmundo.es/wp-content/uploads/2021/09/macedonia-de-frutas.jpg" alt="Ensalada de Frutas">
            <ul>
                <li>1 piña</li>
                <li>2 mangos</li>
                <li>1 sandía</li>
                <li>2 plátanos</li>
                <li>Jugo de limón</li>
                <li>Miel al gusto</li>
            </ul>
            <p>
                1. Lava, pela y corta todas las frutas en trozos.<br>
                2. Mezcla las frutas en un tazón grande.<br>
                3. Exprime el jugo de limón sobre la ensalada de frutas para realzar el sabor.<br>
                4. Agrega miel al gusto y mezcla bien.<br>
                5. Refrigera por al menos 30 minutos antes de servir.
            </p>
        </section>

        <!-- Receta 3: Tarta de Manzana -->
        <section class="recipe">
            <h1>Tarta de Manzana</h1>
            <img src="https://imag.bonviveur.com/tarta-de-manzana.jpg" alt="Tarta de Manzana">
            <ul>
                <li>2 tazas de harina de trigo</li>
                <li>1/2 taza de mantequilla fría</li>
                <li>1/2 taza de azúcar</li>
                <li>3-4 manzanas peladas y cortadas en rodajas</li>
                <li>1 cucharada de canela en polvo</li>
            </ul>
            <p>
                1. Precalienta el horno a 180°C.<br>
                2. En un tazón, mezcla la harina, la mantequilla y el azúcar hasta obtener una masa quebradiza.<br>
                3. Forra un molde para tarta con la masa, presionando bien en el fondo y los lados.<br>
                4. Coloca las rodajas de manzana sobre la masa en el molde, espolvorea con canela en polvo.<br>
                5. Hornea por 30-35 minutos o hasta que la tarta esté dorada. Deja enfriar antes de servir.
            </p>
        </section>
    </div>

    <footer>
        <p>© 2023 - Todos los derechos reservados</p>
    </footer>
</body>
</html>
```

### 3.2 Hoja de Estilos CSS (`style.css`)

```css
/* style.css */
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f9f9f9;
}

h1 {
    text-align: center;
    color: #232323;
}

.recipe {
    max-width: 600px;
    margin: 20px auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 10px;
    background-color: #fff;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
}

ul {
    list-style: none;
    padding: 0;
    margin: 0;
}

li {
    margin-bottom: 5px;
}

p {
    line-height: 1.6;
    background-color: #f9f9f9;
    padding: 10px;
    border-radius: 5px;
}

/* Color alternado para recetas pares */
.recipe:nth-child(even) {
    background-color: #f5f5f5;
}

/* Estilos de cabecera y contenedor principal */
header {
    background-color: #007bff;
    color: #fff;
    text-align: center;
    padding: 1rem 0;
}

.container {
    max-width: 900px;
    margin: 0 auto;
}

footer {
    background-color: #333;
    color: #894848;
    text-align: center;
    padding: 1rem 0;
}

/* Enlaces */
a {
    color: #007bff;
    text-decoration: none;
}

a:hover {
    color: #0056b3;
}

/* Botones */
.btn {
    display: inline-block;
    background-color: #007bff;
    color: #fff;
    padding: 8px 16px;
    border-radius: 5px;
    text-decoration: none;
    transition: background-color 0.3s;
}

.btn:hover {
    background-color: #0056b3;
}

/* Ingrediente principal destacado */
.recipe li.important {
    font-weight: bold;
}

/* Imágenes de recetas */
.recipe img {
    display: block;
    margin: 0 auto;
    max-width: 200px;
    border-radius: 10px;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
}
```

---

## 4. Conceptos Técnicos Aplicados

| Regla / Propiedad | Utilidad Práctica |
| :--- | :--- |
| `margin: 0 auto;` | Centra horizontalmente un contenedor con ancho definido (`max-width`). |
| `box-shadow` | Agrega sombras suaves para dar sensación de profundidad (efecto tarjeta/card). |
| `border-radius` | Redondea las esquinas de contenedores e imágenes. |
| `:nth-child(even)` | Pseudo-clase que aplica estilos solo a elementos pares (efecto cebra). |
| `list-style: none;` | Remueve las viñetas predeterminadas de las listas desordenadas (`<ul>`). |
| `transition` | Genera transiciones suaves de color al interactuar con `:hover`. |
