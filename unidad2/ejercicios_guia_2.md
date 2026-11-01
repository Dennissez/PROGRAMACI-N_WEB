# PROGRAMACIÓN WEB / DISEÑO WEB

## GUÍA PRÁCTICA 4: FUNCIONES, LISTAS Y MODULARIDAD EN PYTHON (R_4)

* **Asignatura:** Programación Web / Diseño Web
* **Unidad N° 2:** Fundamentos de Python: Introducción al Lenguaje de Programación (Semana 4 / Actividad N°1)
* **Objetivo:** Diseñar e implementar soluciones modulares mediante funciones personalizadas (`def`), combinando colecciones de datos avanzadas (listas anidadas y diccionarios de frecuencia), algoritmos de ordenamiento, menús iterativos continuos y gestión de estados lógicos.

---

## 🧭 Tabla de Contenidos

1. [Visión General de la Actividad](#1-visión-general-de-la-actividad)
2. [Ejercicio 1.A: Cálculo del Promedio de una Lista](#2-ejercicio-1a-cálculo-del-promedio-de-una-lista)
3. [Ejercicio 1.B: Búsqueda del Segundo Elemento Más Grande](#3-ejercicio-1b-búsqueda-del-segundo-elemento-más-grande)
4. [Ejercicio 1.C: Frecuencia de Elementos mediante Diccionarios](#4-ejercicio-1c-frecuencia-de-elementos-mediante-diccionarios)
5. [Ejercicio 1.D: Calculadora Modular Interactiva con Menú](#5-ejercicio-1d-calculadora-modular-interactiva-con-menú)
6. [Ejercicio 1.E: Sistema Gestor de Tareas Pendientes (To-Do List)](#6-ejercicio-1e-sistema-gestor-de-tareas-pendientes-to-do-list)
7. [Resumen de Técnicas y Estructuras Empleadas](#7-resumen-de-técnicas-y-estructuras-empleadas)

---

## 1. Visión General de la Actividad

La Semana 4 concluye la Unidad II afianzando el paradigma procedimental y modular en Python. Los ejercicios propuestos exigen trasladar la lógica directa a **funciones reutilizables con retorno (`return`)**, controlando flujos iterativos infinitos (`while True`), validaciones de frontera (listas vacías o divisiones por cero) y manipulación de listas bidimensionales para gestión de estado en memoria.

---

## 2. Ejercicio 1.A: Cálculo del Promedio de una Lista

### Propósito del Ejercicio
Diseñar una función `calcular_promedio(lista)` que reciba una lista de valores numéricos y retorne su promedio aritmético exacto. Incluye una cláusula de guarda inicial para evitar errores de división por cero si la lista está vacía (`len(lista) == 0`).

### Código Fuente Python (`ejercicio_1a.py`)

```python
def calcular_promedio(lista):
    if len(lista) == 0:
        return 0
    return sum(lista) / len(lista)


# Datos de prueba
numeros = [12, 34, 56, 23, 45, 67, 89]
promedio = calcular_promedio(numeros)

print("El promedio de la lista es:", promedio)
```

### Ejemplo de Salida en Consola
```text
El promedio de la lista es: 46.57142857142857
```

---

## 3. Ejercicio 1.B: Búsqueda del Segundo Elemento Más Grande

### Propósito del Ejercicio
Crear una función `segundo_mas_grande(lista)` que determine el segundo valor numérico más alto dentro de una colección. Se valida previamente que la lista posea al menos dos elementos; luego se ordena de forma descendente mediante `sorted(lista, reverse=True)` y se retorna el índice `[1]`.

### Código Fuente Python (`ejercicio_1b.py`)

```python
def segundo_mas_grande(lista):
    if len(lista) < 2:
        return None
    # Orden descendente (de mayor a menor)
    lista_ordenada = sorted(lista, reverse=True)
    return lista_ordenada[1]


# Datos de prueba
datos = [56, 23, 78, 45, 90, 12, 67]
segundo = segundo_mas_grande(datos)

print("El segundo elemento más grande es:", segundo)
```

### Ejemplo de Salida en Consola
```text
El segundo elemento más grande es: 78
```

---

## 4. Ejercicio 1.C: Frecuencia de Elementos mediante Diccionarios

### Propósito del Ejercicio
Implementar la función `contar_frecuencia(lista)` para computar cuántas veces se repite cada valor dentro de una colección heterogénea o numérica, organizando el resultado en un diccionario clave-valor (`{elemento: ocurrencias}`).

### Código Fuente Python (`ejercicio_1c.py`)

```python
def contar_frecuencia(lista):
    frecuencia = {}
    for elemento in lista:
        if elemento in frecuencia:
            frecuencia[elemento] += 1
        else:
            frecuencia[elemento] = 1
    return frecuencia


# Datos de prueba
elementos = [10, 20, 10, 30, 20, 10, 40, 30, 30]
frecuencia_elementos = contar_frecuencia(elementos)

print("Frecuencia de elementos:", frecuencia_elementos)
```

### Ejemplo de Salida en Consola
```text
Frecuencia de elementos: {10: 3, 20: 2, 30: 3, 40: 1}
```

---

## 5. Ejercicio 1.D: Calculadora Modular Interactiva con Menú

### Propósito del Ejercicio
Construir una suite de cálculo que descompone cada operación aritmética fundamental en funciones independientes (`suma`, `resta`, `multiplicacion`, `division`), controlada desde un bucle de menú continuo `while True` con validación ante división por cero e interrupción controlada con `break`.

### Código Fuente Python (`ejercicio_1d.py`)

```python
def suma(a, b):
    return a + b


def resta(a, b):
    return a - b


def multiplicacion(a, b):
    return a * b


def division(a, b):
    if b != 0:
        return a / b
    else:
        return "No se puede dividir por cero"


# Flujo interactivo en consola
while True:
    print("\nSelecciona una operación:")
    print("1. Suma")
    print("2. Resta")
    print("3. Multiplicación")
    print("4. División")
    print("5. Salir")

    opcion = int(input("Ingrese el número de la operación deseada: "))

    if opcion == 5:
        print("Saliendo...")
        break

    if opcion in [1, 2, 3, 4]:
        num1 = float(input("Ingrese el primer número: "))
        num2 = float(input("Ingrese el segundo número: "))

        if opcion == 1:
            print("Resultado:", suma(num1, num2))
        elif opcion == 2:
            print("Resultado:", resta(num1, num2))
        elif opcion == 3:
            print("Resultado:", multiplicacion(num1, num2))
        elif opcion == 4:
            print("Resultado:", division(num1, num2))
    else:
        print("Opción inválida. Intente de nuevo.")
```

### Ejemplo de Salida en Consola
```text
Selecciona una operación:
1. Suma
2. Resta
3. Multiplicación
4. División
5. Salir
Ingrese el número de la operación deseada: 1
Ingrese el primer número: 14.5
Ingrese el segundo número: 5.5
Resultado: 20.0
```

---

## 6. Ejercicio 1.E: Sistema Gestor de Tareas Pendientes (To-Do List)

### Propósito del Ejercicio
Diseñar un gestor de tareas en consola que maneje una lista bidimensional dinámica `[ [nombre_tarea, estado_booleano], ... ]`. Permite añadir registros, listar tareas indexadas correlativamente con `enumerate()` evaluando un operador ternario para el estado (`Completada` / `Pendiente`), y actualizar el valor booleano mediante acceso directo por índice.

### Código Fuente Python (`ejercicio_1e.py`)

```python
def agregar_tarea(lista_tareas):
    nombre_tarea = input("Ingrese el nombre de la tarea: ")
    # Estructura de registro: [nombre, completado]
    lista_tareas.append([nombre_tarea, False])
    print("Tarea agregada.")


def ver_tareas(lista_tareas):
    if not lista_tareas:
        print("No hay tareas registradas.")
        return

    print("\n--- LISTA DE TAREAS ---")
    for idx, tarea in enumerate(lista_tareas, start=1):
        # Evaluación del estado booleano tarea[1]
        estado = "Completada" if tarea[1] else "Pendiente"
        print(f"{idx}. {tarea[0]} - {estado}")


def marcar_completada(lista_tareas):
    ver_tareas(lista_tareas)
    if not lista_tareas:
        return

    num_tarea = int(input("\nIngrese el número de la tarea completada: ")) - 1
    if 0 <= num_tarea < len(lista_tareas):
        lista_tareas[num_tarea][1] = True
        print("Tarea marcada como completada.")
    else:
        print("Número de tarea inválido.")


def menu():
    lista_tareas = []
    while True:
        print("\nMenú:")
        print("1. Agregar tarea")
        print("2. Ver tareas")
        print("3. Marcar tarea como completada")
        print("4. Salir")

        opcion = input("Seleccione una opción: ")

        if opcion == "1":
            agregar_tarea(lista_tareas)
        elif opcion == "2":
            ver_tareas(lista_tareas)
        elif opcion == "3":
            marcar_completada(lista_tareas)
        elif opcion == "4":
            print("Saliendo del programa.")
            break
        else:
            print("Opción inválida. Intente nuevamente.")


# Punto de entrada
if __name__ == "__main__":
    menu()
```

### Ejemplo de Salida en Consola
```text
Menú:
1. Agregar tarea
2. Ver tareas
3. Marcar tarea como completada
4. Salir
Seleccione una opción: 1
Ingrese el nombre de la tarea: Estudiar para quiz de CSS
Tarea agregada.

Menú:
1. Agregar tarea
2. Ver tareas
3. Marcar tarea como completada
4. Salir
Seleccione una opción: 2

--- LISTA DE TAREAS ---
1. Estudiar para quiz de CSS - Pendiente
```

---

## 7. Resumen de Técnicas y Estructuras Empleadas

| Ejercicio | Algoritmo / Operación | Estructura Principal | Concepto Evaluado |
| :--- | :--- | :--- | :--- |
| **1.A** | Promedio aritmético | `sum()`, `len()` | Validación de listas vacías y retorno flotante. |
| **1.B** | Segundo máximo | `sorted(..., reverse=True)` | Ordenamiento y lectura por índice `[1]`. |
| **1.C** | Conteo de frecuencias | Diccionario `{}` | Pertenencia `in`, conteo y acumulación clave-valor. |
| **1.D** | Calculadora modular | Funciones aritméticas + `while True` | Menú interactivo, bifurcación `elif` y control de división por cero. |
| **1.E** | Gestor To-Do | Matriz / Lista de sublistas `[[str, bool]]` | `enumerate()`, operador ternario y mutación in-place. |
