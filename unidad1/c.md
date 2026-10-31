# PROGRAMACIÓN WEB / DISEÑO WEB

## GUÍA PRÁCTICA 1: ESTRUCTURA BÁSICA, ETIQUETAS, TABLAS Y FORMULARIOS (R_1)

* **Asignatura:** Programación Web / Diseño Web
* **Unidad N° 1:** Introducción a HTML y CSS: Fundamentos para el Desarrollo Web (Semana 1)
* **Objetivo:** Implementar la estructura básica de páginas web en HTML5 utilizando etiquetas semánticas, jerarquía de encabezados, organización tabular y formularios de interacción con controles de validación.

---

## 🧭 Tabla de Contenidos

1. [Visión General de la Actividad](#1-visión-general-de-la-actividad)
2. [Ejercicio 1: Jerarquía de Textos, Contenedores y Tabla de Datos](#2-ejercicio-1-jerarquía-de-textos-contenedores-y-tabla-de-datos)
3. [Ejercicio 2: Catálogo de Productos y Formulario de Contacto](#3-ejercicio-2-catálogo-de-productos-y-formulario-de-contacto)
4. [Ejercicio 3: Layout con Tablas y Formulario Avanzado de Registro](#4-ejercicio-3-layout-con-tablas-y-formulario-avanzado-de-registro)
5. [Análisis Técnico y Buenas Prácticas](#5-análisis-técnico-y-buenas-prácticas)

---

## 1. Visión General de la Actividad

La actividad práctica de la Semana 1 pone en práctica los conceptos fundamentales de marcado HTML5, enfocándose en tres aspectos esenciales del desarrollo front-end:

* **Estructura semántica del documento:** Uso adecuado de `<!DOCTYPE html>`, `<html>`, `<head>` (metadatos, charset) y `<body>`.
* **Organización de contenidos:** Empleo de títulos jerárquicos (`<h1>` a `<h4>`), párrafos (`<p>`), hipervínculos (`<a>`) y división por bloques (`<div>`).
* **Formatos tabulares y formularios:** Maquetación con `<table>`, `<tr>`, `<td>`, `<th>` e integración de campos de entrada (`<input>`), etiquetas descriptivas asociadas (`<label>`) y elementos de selección (`<select>`).

---

## 2. Ejercicio 1: Jerarquía de Textos, Contenedores y Tabla de Datos

### Propósito del Ejercicio
Estructurar un documento HTML5 estándar que agrupe encabezados jerárquicos descendentes con párrafos descriptivos dentro de un contenedor `<div>`, incorpore un campo de texto con su respectiva etiqueta asociada, un enlace externo y una tabla con encabezados (`<th>`) y datos (`<td>`).

### Código Fuente HTML (`ejercicio1.html`)

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Ejercicio de etiquetas HTML</title>
</head>
<body>
    <div>
        <h1>Título principal</h1>
        <p>Este es un párrafo dentro de un div.</p>
        
        <h2>Encabezado 2</h2>
        <p>Este es otro párrafo dentro de un div.</p>
        
        <h3>Encabezado 3</h3>
        <p>Este es otro párrafo dentro de un div.</p>
        
        <h4>Encabezado 4</h4>
        <p>Este es otro párrafo dentro de un div.</p>
        
        <label for="nombre">Nombre:</label>
        <input type="text" id="nombre">
        <a href="https://www.ejemplo.com">Enlace</a>
    </div>

    <table border="1">
        <tr>
            <th>Encabezado 1</th>
            <th>Encabezado 2</th>
        </tr>
        <tr>
            <td>Dato 1</td>
            <td>Dato 2</td>
        </tr>
        <tr>
            <td>Dato 3</td>
            <td>Dato 4</td>
        </tr>
    </table>
</body>
</html>
```

---

## 3. Ejercicio 2: Catálogo de Productos y Formulario de Contacto

### Propósito del Ejercicio
Modelar una sección de catálogo donde cada ítem posea un título y una descripción organizada en filas tabulares, complementado con un formulario que recolecta nombre y correo electrónico con validación de obligatoriedad (`required`), finalizando con un comentario de documentación en el código fuente.

### Código Fuente HTML (`ejercicio2.html`)

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Lista de productos</title>
</head>
<body>
    <div>
        <h1>Lista de productos</h1>
        
        <table border="1">
            <tr>
                <td>
                    <h3>Producto 1</h3>
                </td>
                <td>
                    <p>Descripción del Producto 1</p>
                </td>
            </tr>
            <tr>
                <td>
                    <h3>Producto 2</h3>
                </td>
                <td>
                    <p>Descripción del Producto 2</p>
                </td>
            </tr>
            <tr>
                <td>
                    <h3>Producto 3</h3>
                </td>
                <td>
                    <p>Descripción del Producto 3</p>
                </td>
            </tr>
        </table>

        <form action="" method="post">
            <label for="nombre">Nombre:</label>
            <input type="text" id="nombre" name="nombre" required>
            <br><br>
            
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>
            <br><br>
            
            <input type="submit" value="Enviar">
        </form>
    </div>
    
    <!-- Ejercicio creado para práctica de etiquetas de lista y formulario -->
</body>
</html>
```

---

## 4. Ejercicio 3: Layout con Tablas y Formulario Avanzado de Registro

### Propósito del Ejercicio
Distribuir el espacio de la página en dos columnas principales mediante celdas de una tabla (`<td>` izquierda y `<td>` derecha):
1. **Columna Izquierda:** Presentación institucional y destacados de productos clasificados.
2. **Columna Derecha:** Formulario completo de registro con múltiples tipos de entrada (`text`, `email`, `password`, `number`, `select`, `checkbox`, `submit`, `reset`) y restricciones de validación nativas.

### Código Fuente HTML (`ejercicio3.html`)

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Ejercicio de etiquetas HTML</title>
</head>
<body>
    <table border="0" width="100%">
        <tr>
            <!-- Columna Izquierda: Información y Secciones -->
            <td valign="top" width="50%">
                <h2>Presentación</h2>
                <p>Bienvenido a nuestro sitio web. Aquí encontrarás información sobre nuestros productos y servicios.</p>
                <p>Explora nuestras secciones y descubre todo lo que tenemos para ofrecerte.</p>
                
                <h2>Productos destacados</h2>
                <p>Descubre nuestros últimos productos y aprovecha nuestras ofertas especiales.</p>
                
                <h3>Tecnología innovadora</h3>
                <p>Conoce nuestros dispositivos de última generación que te brindarán una experiencia única.</p>
                
                <h3>Ropa y accesorios</h3>
                <p>Encuentra la moda más actualizada y los accesorios perfectos para complementar tu estilo.</p>
            </td>

            <!-- Columna Derecha: Formulario Completo -->
            <td valign="top" width="50%">
                <h2>Formulario</h2>
                <form action="" method="post">
                    <label for="nombre">Nombre:</label><br>
                    <input type="text" id="nombre" name="nombre"><br><br>

                    <label for="email">Email:</label><br>
                    <input type="email" id="email" name="email" required><br><br>

                    <label for="password">Contraseña:</label><br>
                    <input type="password" id="password" name="password" minlength="8" required><br><br>

                    <label for="edad">Edad:</label><br>
                    <input type="number" id="edad" name="edad" min="18" max="99"><br><br>

                    <label for="genero">Género:</label><br>
                    <select id="genero" name="genero">
                        <option value="masculino">Masculino</option>
                        <option value="femenino">Femenino</option>
                        <option value="otro">Otro</option>
                    </select><br><br>

                    <input type="checkbox" id="aceptar" name="terminos">
                    <label for="aceptar">Acepto los términos y condiciones</label><br><br>

                    <div>
                        <input type="submit" value="Enviar">
                        <input type="reset" value="Limpiar">
                    </div>
                </form>
            </td>
        </tr>
    </table>
</body>
</html>
```

---

## 5. Análisis Técnico y Buenas Prácticas

| Control / Atributo | Utilidad Práctica | Relevancia en el Ejercicio |
| :--- | :--- | :--- |
| `for` en `<label>` | Vincula el texto accesible con el `id` del `<input>`. | Al cliquear el texto o usar lectores de pantalla, el foco se activa en el campo correspondiente. |
| `type="email"` | Validación nativa de sintaxis de correo. | Exige formato válido (`usuario@dominio.com`) antes de permitir el envío del formulario. |
| `minlength="8"` | Longitud mínima requerida en contraseñas. | Bloquea el envío si la clave posee menos de 8 caracteres. |
| `min="18"` y `max="99"` | Rango numérico admitido en campos `type="number"`. | Controla que la edad registrada corresponda a mayores de edad dentro de límites válidos. |
| `<select>` y `<option>` | Menú desplegable de opción única. | Estandariza la entrada de opciones predefinidas (ej. género). |
| `type="reset"` | Limpieza de formulario. | Devuelve todos los campos y casillas de verificación a su estado inicial. |
