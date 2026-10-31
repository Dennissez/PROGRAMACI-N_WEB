# PROGRAMACIÓN WEB / DISEÑO WEB

## MANUAL DE ESTUDIO 3: FUNDAMENTOS DE PYTHON (ME_3)

* **Asignatura:** Diseño Web / Programación Web
* **Unidad N° 2:** Fundamentos de Python: Introducción al Lenguaje de Programación (Semana 3)
* **Temario:** Características del lenguaje, entorno PyCharm, variables, funciones nativas (`print`, `input`), operadores, sentencias condicionales (`if-elif-else`), manejo de excepciones (`try-except-else-finally`), estructuras de datos (listas, tuplas, diccionarios), bucles (`while`, `for`, `range`) y Programación Orientada a Objetos (clases, `__init__`, `self` y encapsulamiento por convención).

## 🧭 Tabla de Contenidos

1. [¿Qué es Python?](#1-qué-es-python)
2. [Entorno de Desarrollo: Instalación y PyCharm](#2-entorno-de-desarrollo-instalación-y-pycharm)
3. [Elementos Básicos y Funciones Integradas](#3-elementos-básicos-y-funciones-integradas)
   * [3.1 Variables y Tipado Dinámico](#31-variables-y-tipado-dinámico)
   * [3.2 Salida por Pantalla: `print()`](#32-salida-por-pantalla-print)
   * [3.3 Entrada de Datos: `input()`](#33-entrada-de-datos-input)
4. [Operadores en Python](#4-operadores-en-python)
   * [4.1 Operadores Aritméticos](#41-operadores-aritméticos)
   * [4.2 Operadores Lógicos](#42-operadores-lógicos)
   * [4.3 Operadores Relacionales o de Comparación](#43-operadores-relacionales-o-de-comparación)
5. [Estructuras de Control Condicional](#5-estructuras-de-control-condicional)
6. [Manejo Robusto de Excepciones (`try-except`)](#6-manejo-robusto-de-excepciones-try-except)
7. [Colecciones y Estructuras de Datos](#7-colecciones-y-estructuras-de-datos)
   * [7.1 Listas (Mutables e Indexadas)](#71-listas-mutables-e-indexadas)
   * [7.2 Tuplas (Inmutables e Indexadas)](#72-tuplas-inmutables-e-indexadas)
   * [7.3 Diccionarios (Pares Clave-Valor)](#73-diccionarios-pares-clave-valor)
8. [Sentencias Iterativas (Bucles)](#8-sentencias-iterativas-bucles)
   * [8.1 Bucle `while`](#81-bucle-while)
   * [8.2 Bucle `for` y Función `range()`](#82-bucle-for-y-función-range)
9. [Programación Orientada a Objetos (POO)](#9-programación-orientada-a-objetos-poo)
   * [9.1 Definición de Clases e Instanciación](#91-definición-de-clases-e-instanciación)
   * [9.2 Constructor `__init__` y Referencia `self`](#92-constructor-__init__-y-referencia-self)
   * [9.3 Atributos Privados y Encapsulamiento](#93-atributos-privados-y-encapsulamiento)
10. [Preguntas de Autoevaluación y Reflexión](#10-preguntas-de-autoevaluación-y-reflexión)

---

## 1. ¿Qué es Python?

**Python** es un lenguaje de programación de alto nivel, interpretado, multiparadigma y multiplataforma, reconocido por su sintaxis clara y legible.

* **Interpretado:** No requiere un proceso previo de compilación a código máquina binario; el intérprete de Python procesa y ejecuta las instrucciones línea por línea.
* **Legibilidad:** Utiliza la indentación (sangría obligatoria) para delimitar bloques de código en lugar de llaves (`{}`) o palabras clave como `BEGIN`/`END`.
* **Propósito general:** Empleado ampliamente en desarrollo web back-end, ciencia de datos, machine learning, scripting y automatización de procesos.

---

## 2. Entorno de Desarrollo: Instalación y PyCharm

1. **Intérprete de Python:** Se descarga desde su portal oficial ([python.org](https://www.python.org/)). Durante la instalación en Windows es fundamental marcar la casilla **"Add python.exe to PATH"** para habilitar su invocación desde cualquier terminal.
2. **PyCharm Community Edition:** IDE desarrollado por JetBrains enfocado exclusivamente en Python. Ofrece gestión de entornos virtuales (`venv`), autocompletado inteligente, depurador interactivo y terminal integrada.
3. **Flujo de configuración:** Se instala primero el motor de Python y luego PyCharm, asociando el intérprete base (`python.exe`) al crear un nuevo proyecto.

---

## 3. Elementos Básicos y Funciones Integradas

### 3.1 Variables y Tipado Dinámico

En Python no se declara el tipo de dato explícitamente; el intérprete infiere el tipo según el valor asignado:

```python
edad = 25              # Entero (int)
nombre = "Juan"        # Cadena de caracteres (str)
saldo_cuenta = 1000.50 # Decimal de coma flotante (float)
activo = True          # Booleano (bool)
```

* Los nombres de variables distinguen entre mayúsculas y minúsculas (*case-sensitive*).
* Deben iniciar con una letra o guion bajo (`_`), sin espacios ni caracteres especiales.

### 3.2 Salida por Pantalla: `print()`

Muestra mensajes y valores por consola:

```python
nombre = "Ana"
edad = 30

# Concatenación con comas (agrega un espacio automáticamente)
print("Nombre:", nombre, "| Edad:", edad)

# Parámetros opcionales: sep (separador) y end (carácter final)
print(nombre, edad, sep=" - ", end=".\n")
```

### 3.3 Entrada de Datos: `input()`

Captura la entrada escrita por el usuario. **Siempre retorna un dato de tipo cadena (`str`)**:

```python
nombre = input("Ingresa tu nombre: ")

# Conversión de tipo (casting) obligatoria para cálculos numéricos
edad = int(input("Ingresa tu edad: "))
altura = float(input("Ingresa tu altura en metros: "))

print(f"Hola {nombre}, tienes {edad} años y mides {altura}m.")
```

---

## 4. Operadores en Python

### 4.1 Operadores Aritméticos

| Operador | Operación | Ejemplo | Resultado |
| :---: | :--- | :---: | :---: |
| `+` | Suma | `5 + 3` | `8` |
| `-` | Resta | `7 - 2` | `5` |
| `*` | Multiplicación | `4 * 6` | `24` |
| `/` | División decimal | `10 / 2` | `5.0` |
| `%` | Módulo (resto entero de la división) | `7 % 3` | `1` |
| `**` | Potencia / Exponente | `2 ** 3` | `8` |

### 4.2 Operadores Lógicos

| Operador | Condición de Verdad | Ejemplo |
| :---: | :--- | :--- |
| `and` | Retorna `True` únicamente si **ambas** expresiones son verdaderas. | `True and False` $\rightarrow$ `False` |
| `or` | Retorna `True` si **al menos una** expresión es verdadera. | `True or False` $\rightarrow$ `True` |
| `not` | Invierte el valor booleano de la expresión. | `not True` $\rightarrow$ `False` |

### 4.3 Operadores Relacionales o de Comparación

| Operador | Significado | Ejemplo |
| :---: | :--- | :---: |
| `==` | Igual a | `5 == 5` $\rightarrow$ `True` |
| `!=` | Distinto de | `3 != 5` $\rightarrow$ `True` |
| `>` | Mayor que | `8 > 6` $\rightarrow$ `True` |
| `<` | Menor que | `4 < 2` $\rightarrow$ `False` |
| `>=` | Mayor o igual que | `7 >= 7` $\rightarrow$ `True` |
| `<=` | Menor o igual que | `9 <= 6` $\rightarrow$ `False` |

---

## 5. Estructuras de Control Condicional

Permiten bifurcar el flujo del programa evaluando expresiones booleanas:

```python
edad = int(input("Ingresa tu edad: "))

if edad < 18:
    print("Menor de edad.")
elif edad < 65:
    print("Adulto activo.")
else:
    print("Adulto mayor.")
```

---

## 6. Manejo Robusto de Excepciones (`try-except`)

Previene la interrupción abruptly del software ante fallas de ejecución en tiempo de corrida:

```python
try:
    numero = int(input("Ingresa un número: "))
    resultado = 10 / numero
except ZeroDivisionError:
    print("Error: No se permite la división entre cero.")
except ValueError:
    print("Error: Debes ingresar un número entero válido.")
else:
    # Se ejecuta solo si NO hubo ninguna excepción
    print("Operación exitosa. Resultado:", resultado)
finally:
    # Se ejecuta SIEMPRE (ideal para cerrar archivos o conexiones)
    print("Fin del bloque de control.")
```

---

## 7. Colecciones y Estructuras de Datos

### 7.1 Listas (Mutables e Indexadas)

Secuencias ordenadas de elementos modificables delimitadas por corchetes `[]`:

```python
frutas = ["manzana", "naranja", "plátano"]

# Métodos fundamentales
frutas.append("uva")          # Agrega al final
frutas.insert(1, "pera")      # Inserta en el índice indicado
frutas.remove("naranja")      # Elimina por valor
elemento = frutas.pop()       # Extrae y retorna el último elemento
frutas.sort()                 # Ordena alfabéticamente/numéricamente
longitud = len(frutas)        # Cantidad de elementos
```

### 7.2 Tuplas (Inmutables e Indexadas)

Colecciones ordenadas no modificables delimitadas por paréntesis `()`:

```python
dimensiones = (1920, 1080)
print(dimensiones[0])  # Acceso por índice: 1920

# dimensiones[0] = 1280  # TypeError: no se pueden reasignar valores
```

### 7.3 Diccionarios (Pares Clave-Valor)

Colecciones mutables organizadas por claves únicas delimitadas por llaves `{}`:

```python
estudiante = {
    "nombre": "Francisca",
    "edad": 22,
    "carrera": "Informática"
}

# Acceso y modificación
print(estudiante["nombre"])
estudiante["edad"] = 23            # Modificación
estudiante["ciudad"] = "Santiago"  # Nuevo par clave-valor
del estudiante["carrera"]          # Eliminación
```

---

## 8. Sentencias Iterativas (Bucles)

### 8.1 Bucle `while`

Repite un bloque mientras la condición lógica sea `True`:

```python
contador = 1
while contador <= 5:
    print("Iteración:", contador)
    contador += 1
```

### 8.2 Bucle `for` y Función `range()`

Recorre secuencias directamente o rangos numéricos:

```python
# Recorrido de una lista
colores = ["rojo", "verde", "azul"]
for color in colores:
    print("Color:", color)

# Bucle con range(inicio, fin_excluido, paso)
for i in range(1, 6):
    print("Número:", i)  # Imprime del 1 al 5
```

---

## 9. Programación Orientada a Objetos (POO)

### 9.1 Definición de Clases e Instanciación

Una clase es un modelo o plantilla para crear objetos que encapsulan datos (atributos) y comportamientos (métodos):

```python
class Coche:
    def __init__(self, marca, modelo):
        self.marca = marca
        self.modelo = modelo

    def acelerar(self):
        print(f"El coche {self.marca} {self.modelo} está acelerando.")

# Instanciación
mi_coche = Coche("Toyota", "Corolla")
mi_coche.acelerar()
```

### 9.2 Constructor `__init__` y Referencia `self`

* **`__init__`:** Método constructor especial invocado automáticamente al instanciar el objeto para inicializar su estado.
* **`self`:** Representa explícitamente a la instancia en concreto que invoca el método o atributo.

### 9.3 Atributos Privados y Encapsulamiento

En Python el encapsulamiento se gestiona por **convención**:

* Un guion bajo inicial (`_saldo`) denota un miembro protegido que **no debe accederse directamente desde el exterior** de la clase:

```python
class CuentaBancaria:
    def __init__(self, saldo_inicial):
        self._saldo = saldo_inicial  # Atributo protegido/privado por convención

    def consultar_saldo(self):
        return self._saldo

    def depositar(self, monto):
        if monto > 0:
            self._saldo += monto

cuenta = CuentaBancaria(50000)
print("Saldo actual:", cuenta.consultar_saldo())
```

---

## 10. Preguntas de Autoevaluación y Reflexión

1. **¿Qué diferencia fundamental existe entre una lista y una tupla en Python?**
   * Las listas son **mutables** (pueden agregar, remover o alterar sus elementos), mientras que las tuplas son **inmutables** y su contenido permanece constante tras crearse.
2. **¿Por qué la función `input()` requiere habitualmente de un casting explícito con `int()` o `float()`?**
   * Porque siempre devuelve un string (`str`), impidiendo realizar operaciones aritméticas directas.
3. **¿Cuál es el rol del parámetro `self` dentro de las funciones de una clase?**
   * Permite vincular y acceder a los atributos y métodos pertenecientes a la instancia puntual que se está ejecutando.
