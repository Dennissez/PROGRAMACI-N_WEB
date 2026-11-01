# PROGRAMACIÓN WEB / DISEÑO WEB

## GUÍA PRÁCTICA 3: FUNDAMENTOS DE PYTHON (R_3)

* **Asignatura:** Programación Web / Diseño Web
* **Unidad N° 2:** Fundamentos de Python: Introducción al Lenguaje de Programación (Semana 3 / Actividad N°1)
* **Objetivo:** Aplicar los conceptos fundamentales de Python: entrada y salida estándar, tipos de datos, estructuras de control condicional (`if-elif-else`), bucles (`for`), funciones de rango (`range`), algoritmos clásicos de acumulación, búsqueda de máximos y filtrado de listas.

---

## 🧭 Tabla de Contenidos

1. [Visión General de la Guía](#1-visión-general-de-la-guía)
2. [Ejercicio 1.A: Suma de Dos Números con Entrada por Consola](#2-ejercicio-1a-suma-de-dos-números-con-entrada-por-consola)
3. [Ejercicio 1.B: Rango Numérico y Filtrado de Números Pares](#3-ejercicio-1b-rango-numérico-y-filtrado-de-números-pares)
4. [Ejercicio 1.C: Contador de Vocales en una Cadena de Texto](#4-ejercicio-1c-contador-de-vocales-en-una-cadena-de-texto)
5. [Ejercicio 1.D: Generador de Tablas de Multiplicar (1 al 10)](#5-ejercicio-1d-generador-de-tablas-de-multiplicar-1-al-10)
6. [Ejercicio 1.E: Conversión de Temperatura (Celsius a Fahrenheit)](#6-ejercicio-1e-conversión-de-temperatura-celsius-a-fahrenheit)
7. [Ejercicio 1.F: Calculadora Aritmética Básica con Bifurcación Condicional](#7-ejercicio-1f-calculadora-aritmética-básica-con-bifurcación-condicional)
8. [Ejercicio 1.G: Acumulador y Suma de Elementos de una Lista](#8-ejercicio-1g-acumulador-y-suma-de-elementos-de-una-lista)
9. [Ejercicio 1.H: Algoritmo de Búsqueda del Valor Máximo](#9-ejercicio-1h-algoritmo-de-búsqueda-del-valor-máximo)
10. [Ejercicio 1.I: Eliminación de Elementos Duplicados en una Lista](#10-ejercicio-1i-eliminación-de-elementos-duplicados-en-una-lista)
11. [Tabla Resumen de Conceptos Clave Evaluados](#11-tabla-resumen-de-conceptos-clave-evaluados)

---

## 1. Visión General de la Guía

La Actividad N°1 de la Semana 3 consolida los fundamentos algorítmicos mediante 9 ejercicios prácticos desarrollados en scripts individuales o modulares de Python. Aborda la sintaxis base, captura dinámica de datos mediante `input()`, conversión de tipos (*casting* con `float()` e `int()`), interpolación de cadenas mediante f-strings, estructuras repetitivas e iteración sobre listas.

---

## 2. Ejercicio 1.A: Suma de Dos Números con Entrada por Consola

### Descripción
Solicita al usuario ingresar dos valores numéricos a través del teclado, convierte las cadenas ingresadas a números de punto flotante (`float`) y calcula su suma mostrando el resultado formateado.

### Código Python (`ejercicio_1a.py`)
```python
num1 = float(input("Ingrese el primer número: "))
num2 = float(input("Ingrese el segundo número: "))
resultado = num1 + num2
print(f"La suma de {num1} y {num2} es: {resultado}")
```

### Ejemplo de Ejecución
```text
Ingrese el primer número: 12.5
Ingrese el segundo número: 7.5
La suma de 12.5 y 7.5 es: 20.0
```

---

## 3. Ejercicio 1.B: Rango Numérico y Filtrado de Números Pares

### Descripción
Recibe un límite inferior y superior ingresados por el usuario. Utiliza la función `range(inicio, fin + 1)` para recorrer la secuencia inclusiva y el operador módulo (`% 2 == 0`) para imprimir únicamente los números pares en una sola línea horizontal mediante el parámetro `end=" "`.

### Código Python (`ejercicio_1b.py`)
```python
inicio = int(input("Ingrese el número de inicio: "))
fin = int(input("Ingrese el número de fin: "))

for num in range(inicio, fin + 1):
    if num % 2 == 0:
        print(num, end=" ")
print()  # Salto de línea final
```

### Ejemplo de Ejecución
```text
Ingrese el número de inicio: 3
Ingrese el número de fin: 15
4 6 8 10 12 14 
```

---

## 4. Ejercicio 1.C: Contador de Vocales en una Cadena de Texto

### Descripción
Recibe una cadena arbitraria e inicializa un acumulador en cero. Itera carácter por carácter comprobando si pertenece a la colección de vocales (`"aeiouAEIOU"`) mediante el operador de pertenencia `in`.

### Código Python (`ejercicio_1c.py`)
```python
cadena = input("Ingrese una cadena de texto: ")
vocales = "aeiouAEIOU"
contador = 0

for letra in cadena:
    if letra in vocales:
        contador += 1

print(f"El número de vocales en la cadena es: {contador}")
```

### Ejemplo de Ejecución
```text
Ingrese una cadena de texto: Programación Web Iplacex
El número de vocales en la cadena es: 8
```

---

## 5. Ejercicio 1.D: Generador de Tablas de Multiplicar (1 al 10)

### Descripción
Genera la tabla de multiplicar tradicional para cualquier número entero ingresado, recorriendo un ciclo `for` desde el 1 hasta el 10 con `range(1, 11)`.

### Código Python (`ejercicio_1d.py`)
```python
num = int(input("Ingrese un número: "))

for i in range(1, 11):
    resultado = num * i
    print(f"{num} x {i} = {resultado}")
```

### Ejemplo de Ejecución
```text
Ingrese un número: 7
7 x 1 = 7
7 x 2 = 14
7 x 3 = 21
...
7 x 10 = 70
```

---

## 6. Ejercicio 1.E: Conversión de Temperatura (Celsius a Fahrenheit)

### Descripción
Aplica la fórmula matemática de conversión térmica:
$$F = (C \cdot \frac{9}{5}) + 32$$
Utiliza el especificador de formato `{fahrenheit:.2f}` dentro de una f-string para limitar la salida a dos cifras decimales.

### Código Python (`ejercicio_1e.py`)
```python
celsius = float(input("Ingrese la temperatura en grados Celsius: "))
fahrenheit = (celsius * 9/5) + 32
print(f"{celsius} grados Celsius son {fahrenheit:.2f} grados Fahrenheit")
```

### Ejemplo de Ejecución
```text
Ingrese la temperatura en grados Celsius: 24
24.0 grados Celsius son 75.20 grados Fahrenheit
```

---

## 7. Ejercicio 1.F: Calculadora Aritmética Básica con Bifurcación Condicional

### Descripción
Implementa un menú de selección operativa mediante bloques de decisión múltiple `if-elif-else`. Valida los cuatro operadores fundamentales (`+`, `-`, `*`, `/`) y provee un mensaje de contingencia en caso de operador no reconocido.

### Código Python (`ejercicio_1f.py`)
```python
num1 = float(input("Ingrese el primer número: "))
operacion = input("Ingrese la operación (+, -, *, /): ")
num2 = float(input("Ingrese el segundo número: "))

if operacion == "+":
    resultado = num1 + num2
elif operacion == "-":
    resultado = num1 - num2
elif operacion == "*":
    resultado = num1 * num2
elif operacion == "/":
    if num2 != 0:
        resultado = num1 / num2
    else:
        resultado = "ERROR: División por cero"
else:
    print("Operación no válida")
    resultado = "ERROR"

print(f"El resultado de la operación es: {resultado}")
```

### Ejemplo de Ejecución
```text
Ingrese el primer número: 45
Ingrese la operación (+, -, *, /): *
Ingrese el segundo número: 2
El resultado de la operación es: 90.0
```

---

## 8. Ejercicio 1.G: Acumulador y Suma de Elementos de una Lista

### Descripción
Demuestra el funcionamiento interno de un sumador iterativo recorriendo una lista de elementos enteros predefinida sin utilizar la función nativa `sum()`.

### Código Python (`ejercicio_1g.py`)
```python
numeros = [10, 20, 30, 40, 50]
suma = 0

for elemento in numeros:
    suma += elemento

print(f"La suma de los elementos de la lista es: {suma}")
```

### Ejemplo de Ejecución
```text
La suma de los elementos de la lista es: 150
```

---

## 9. Ejercicio 1.H: Algoritmo de Búsqueda del Valor Máximo

### Descripción
Determina el mayor elemento dentro de una colección numérica sin recurrir a la función `max()`. Asume como pivote inicial el primer valor de la lista (`numeros[0]`) y actualiza la referencia cada vez que encuentra un valor estrictamente superior.

### Código Python (`ejercicio_1h.py`)
```python
numeros = [10, 50, 20, 80, 30]
maximo = numeros[0]

for elemento in numeros:
    if elemento > maximo:
        maximo = elemento

print(f"El número máximo en la lista es: {maximo}")
```

### Ejemplo de Ejecución
```text
El número máximo en la lista es: 80
```

---

## 10. Ejercicio 1.I: Eliminación de Elementos Duplicados en una Lista

### Descripción
Filtra una lista que contiene valores repetidos preservando el orden de aparición original. Recorre la lista inicial e inserta los elementos en una nueva lista auxiliar únicamente si no han sido agregados con anterioridad (`if elemento not in lista_sin_duplicados:`).

### Código Python (`ejercicio_1i.py`)
```python
numeros = [1, 2, 2, 3, 4, 4, 5, 5, 5]
lista_sin_duplicados = []

for elemento in numeros:
    if elemento not in lista_sin_duplicados:
        lista_sin_duplicados.append(elemento)

print(f"La lista sin duplicados es: {lista_sin_duplicados}")
```

### Ejemplo de Ejecución
```text
La lista sin duplicados es: [1, 2, 3, 4, 5]
```

---

## 11. Tabla Resumen de Conceptos Clave Evaluados

| Ejercicio | Concepto Central | Estructuras Utilizadas |
| :--- | :--- | :--- |
| **1.A** | Conversión de tipos y suma | `input()`, `float()`, f-strings |
| **1.B** | Filtrado condicional y secuencias | `range()`, bucle `for`, operador `%`, `end=" "` |
| **1.C** | Conteo de ocurrencias y pertenencia | Operador `in`, acumulador `contador += 1` |
| **1.D** | Tablas y multiplicaciones | Bucle `for`, `range(1, 11)` |
| **1.E** | Operaciones aritméticas y formato | Operadores aritméticos, formato `:.2f` |
| **1.F** | Flujo condicional múltiple | `if - elif - else`, operadores de comparación `==` |
| **1.G** | Acumulación iterativa | Lista predefinida, bucle `for`, `suma += elemento` |
| **1.H** | Búsqueda de extremos (máximo) | Puntero inicial `numeros[0]`, comparación `>` |
| **1.I** | Limpieza de colecciones | `append()`, operador `not in`, lista auxiliar `[]` |
