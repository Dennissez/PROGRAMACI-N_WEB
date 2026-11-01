# PROGRAMACIÓN WEB / DISEÑO WEB

## MANUAL DE ESTUDIO 4: FUNDAMENTOS DE PYTHON: MÉTODOS DE LISTAS, CONTROL DE FLUJO Y FUNCIONES (ME_4)

* **Asignatura:** Diseño Web / Programación Web
* **Unidad N° 2:** Fundamentos de Python: Introducción al Lenguaje de Programación (Semana 4)
* **Temario:** Control de interrupción de flujo (`break`, `exit()`, `continue`), sumadores y acumuladores, contadores de eventos, administración avanzada de listas (`append`, `list()`, `pop()`, `remove()`), recorrido, acceso por índices, actualización in-place con `enumerate()` / `range()`, y diseño modular de funciones personalizadas (`def`, parámetros por defecto, sentencias de control anidadas y `return`).

---

## 🧭 Tabla de Contenidos

1. [Control de Flujo de Ejecución en Bucles](#1-control-de-flujo-de-ejecución-en-bucles)
   * [1.1 Sentencia `break`](#11-sentencia-break)
   * [1.2 Función `exit()`](#12-función-exit)
   * [1.3 Sentencia `continue`](#13-sentencia-continue)
2. [Lógica de Acumulación: Sumadores y Contadores](#2-lógica-de-acumulación-sumadores-y-contadores)
   * [2.1 El Patrón Sumador (Acumulador)](#21-el-patrón-sumador-acumulador)
   * [2.2 El Patrón Contador (Frecuencia de Ocurrencias)](#22-el-patrón-contador-frecuencia-de-ocurrencias)
3. [Administración de Datos con Listas y Métodos Integrados](#3-administración-de-datos-con-listas-y-métodos-integrados)
   * [3.1 Inserción Dinámica al Final: Método `append()`](#31-inserción-dinámica-al-final-método-append)
   * [3.2 Conversión Explícita a Listas: Constructor `list()`](#32-conversión-explícita-a-listas-constructor-list)
   * [3.3 Eliminación y Extracción por Posición: Método `pop()`](#33-eliminación-y-extracción-por-posición-método-pop)
   * [3.4 Eliminación por Coincidencia de Valor: Método `remove()`](#34-eliminación-por-coincidencia-de-valor-método-remove)
4. [Técnicas de Recorrido y Extracción de Elementos](#4-técnicas-de-recorrido-y-extracción-de-elementos)
   * [4.1 Iteración Directa con `for`](#41-iteración-directa-con-for)
   * [4.2 Indexación y Slicing (Rebanado)](#42-indexación-y-slicing-rebanado)
   * [4.3 Bucle `while` con Puntero de Control](#43-bucle-while-con-puntero-de-control)
   * [4.4 Iteración Indexada con `enumerate()`](#44-iteración-indexada-con-enumerate)
5. [Actualización y Mutación de Listas durante el Recorrido](#5-actualización-y-mutación-de-listas-durante-el-recorrido)
   * [5.1 Mutación con `for` y `range(len())`](#51-mutación-con-for-y-rangelen)
   * [5.2 Mutación con `enumerate()`](#52-mutación-con-enumerate)
   * [5.3 Mutación con `while`](#53-mutación-con-while)
6. [Funciones Definidas por el Usuario (`def`)](#6-funciones-definidas-por-el-usuario-def)
   * [6.1 Anatomía y Sintaxis](#61-anatomía-y-sintaxis)
   * [6.2 Parámetros, Argumentos y Retorno con `return`](#62-parámetros-argumentos-y-retorno-con-return)
   * [6.3 Parámetros con Valores Predeterminados](#63-parámetros-con-valores-predeterminados)
   * [6.4 Funciones con Lógica Condicional](#64-funciones-con-lógica-condicional)
   * [6.5 Composición y Modularidad entre Funciones](#65-composición-y-modularidad-entre-funciones)
7. [Cuadro Comparativo de Métodos de Lista](#7-cuadro-comparativo-de-métodos-de-lista)
8. [Preguntas de Autoevaluación y Reflexión](#8-preguntas-de-autoevaluación-y-reflexión)

---

## 1. Control de Flujo de Ejecución en Bucles

Durante la ejecución de estructuras repetitivas (`for` y `while`), es común necesitar alterar el flujo normal de iteración en respuesta a eventos o condiciones del programa.

```
                  ┌───────────────────────────────┐
                  │       Ciclo de Iteración      │
                  └──────────────┬────────────────┘
                                 │
                 ¿Se cumple condición de control?
                                 │
     ┌───────────────────────────┼───────────────────────────┐
     ▼                           ▼                           ▼
  [ break ]                 [ continue ]                  [ exit() ]
Detiene y sale del         Salta al siguiente        Termina la ejecución
bucle inmediatamente.      paso de iteración.        total del intérprete.
```

### 1.1 Sentencia `break`

Interrumpe y da por finalizado el bucle en el punto exacto donde es ejecutado, continuando con la primera instrucción posterior al bloque repetitivo:

```python
# Ejemplo de uso de break en un bucle while
numero = 0
while numero < 10:
    if numero == 5:
        break  # Se detiene el bucle cuando numero es igual a 5
    print(numero)
    numero += 1

# Salida en consola: 0, 1, 2, 3, 4
```

### 1.2 Función `exit()`

Finaliza inmediatamente la ejecución completa del intérprete de Python, deteniendo el programa sin importar la profundidad del flujo o llamada en que se encuentre:

```python
# Ejemplo de uso de exit() para detener el script
nombre = input("Ingrese su nombre: ")
if nombre == "admin":
    print("Acceso concedido.")
else:
    print("Acceso denegado.")
    exit()  # El programa se detendrá aquí por completo

print("Cargando panel de control...")
```

> [!WARNING]
> La función `exit()` debe emplearse con prudencia, ya que aborta el hilo de ejecución sin procesar bloques posteriores ni garantizar el guardado de datos en memoria no sincronizados.

### 1.3 Sentencia `continue`

Omite el resto de las instrucciones de la iteración en curso y transfiere el control de inmediato al inicio del siguiente ciclo:

```python
# Ejemplo de uso de continue en un bucle for
for numero in range(1, 6):
    if numero == 3:
        continue  # Se omite el procesamiento cuando numero es igual a 3
    print(numero)

# Salida en consola: 1, 2, 4, 5 (el 3 no se imprime)
```

---

## 2. Lógica de Acumulación: Sumadores y Contadores

### 2.1 El Patrón Sumador (Acumulador)

Un **sumador** acumula cantidades numéricas variables en una variable acumuladora, que debe inicializarse usualmente en cero (`0`):

```python
valores = [10, 5, 8, 3, 7]
total = 0

for valor in valores:
    total += valor  # Equivalente a: total = total + valor

print("El resultado de la suma es:", total)
# Salida: El resultado de la suma es: 33
```

### 2.2 El Patrón Contador (Frecuencia de Ocurrencias)

Un **contador** incrementa su valor en una cantidad fija (generalmente $+1$) cada vez que se satisface una condición lógica de filtrado:

```python
numeros = [2, 5, 2, 8, 2, 10, 2]
elemento_a_contar = 2
ocurrencias = 0

for elemento in numeros:
    if elemento == elemento_a_contar:
        ocurrencias += 1

print(f"El elemento {elemento_a_contar} aparece {ocurrencias} veces.")
# Salida: El elemento 2 aparece 4 veces.
```

---

## 3. Administración de Datos con Listas y Métodos Integrados

Las listas en Python son colecciones dinámicas, mutables y ordenadas que permiten almacenar cualquier tipo de dato u objeto.

### 3.1 Inserción Dinámica al Final: Método `append()`

Inserta un nuevo elemento en la última posición disponible de la lista:

```python
# Inserción de enteros
numeros = [1, 2, 3, 4]
numeros.append(5)
print(numeros)  # [1, 2, 3, 4, 5]

# Inserción de cadenas de texto
frutas = ["manzana", "naranja", "plátano"]
frutas.append("uva")
print(frutas)  # ['manzana', 'naranja', 'plátano', 'uva']

# Inserción de listas anidadas (matriz / sublista)
lista_anterior = [1, 2, 3]
lista_nueva = [4, 5, 6]
lista_anterior.append(lista_nueva)
print(lista_anterior)  # [1, 2, 3, [4, 5, 6]]

# Inserción de valores booleanos
valores = [True, False]
valores.append(True)
print(valores)  # [True, False, True]

# Inserción de diccionarios (objetos complejos)
datos = [{"nombre": "Juan", "edad": 25}, {"nombre": "Maria", "edad": 30}]
datos.append({"nombre": "Pedro", "edad": 22})
print(datos)
```

### 3.2 Conversión Explícita a Listas: Constructor `list()`

Permite transformar secuencias o iterables (cadenas, tuplas, rangos, colecciones clave-valor) en una lista independiente:

```python
# De cadena de texto a lista de caracteres
cadena = "Hola, mundo!"
lista_caracteres = list(cadena)
print(lista_caracteres)
# ['H', 'o', 'l', 'a', ',', ' ', 'm', 'u', 'n', 'd', 'o', '!']

# De tupla inmutable a lista mutable
tupla_numeros = (1, 2, 3, 4, 5)
lista_numeros = list(tupla_numeros)
print(lista_numeros)  # [1, 2, 3, 4, 5]

# De rango numérico a lista
rango_numeros = range(1, 6)
lista_rango = list(rango_numeros)
print(lista_rango)  # [1, 2, 3, 4, 5]

# De diccionario a lista de claves o lista de valores
diccionario_frutas = {"manzana": 3, "naranja": 2, "plátano": 5}
lista_claves = list(diccionario_frutas.keys())
lista_valores = list(diccionario_frutas.values())
print("Claves:", lista_claves)    # ['manzana', 'naranja', 'plátano']
print("Valores:", lista_valores)  # [3, 2, 5]
```

### 3.3 Eliminación y Extracción por Posición: Método `pop()`

Elimina el elemento ubicado en un **índice numérico específico** y **retorna el valor eliminado** para que pueda ser almacenado o procesado:

```python
numeros = [10, 20, 30, 40, 50]

# Extrae el elemento en el índice 2 (valor 30)
elemento_eliminado = numeros.pop(2)

print("Lista resultante:", numeros)             # [10, 20, 40, 50]
print("Elemento extraído:", elemento_eliminado)  # 30

# Si no se indica índice, pop() elimina y retorna el último elemento por defecto
nombres = ["Ana", "Juan", "Maria", "Pedro", "Luis"]
primero = nombres.pop(0)  # Elimina el primer elemento
print(nombres)            # ['Juan', 'Maria', 'Pedro', 'Luis']
print("Eliminado:", primero)
```

### 3.4 Eliminación por Coincidencia de Valor: Método `remove()`

Elimina la **primera aparición** de un valor determinado en la lista. No utiliza índices de posición y no retorna el elemento eliminado:

```python
numeros = [10, 20, 30, 40, 30, 50]

# Remueve la primera ocurrencia del valor 30
numeros.remove(30)
print(numeros)  # [10, 20, 40, 30, 50] (el segundo 30 permanece)

colores = ["rojo", "verde", "azul", "verde"]
colores.remove("verde")
print(colores)  # ['rojo', 'azul', 'verde']
```

> [!CAUTION]
> Si el valor solicitado en `remove(valor)` no existe dentro de la lista, Python arrojará un error `ValueError: list.remove(x): x not in list`. Es buena práctica validar su existencia previamente con `if valor in lista:`.

---

## 4. Técnicas de Recorrido y Extracción de Elementos

### 4.1 Iteración Directa con `for`

Es la forma más legible cuando solo se necesita leer el valor de cada elemento:

```python
numeros = [1, 2, 3, 4, 5]
for numero in numeros:
    print(numero)
```

### 4.2 Indexación y Slicing (Rebanado)

Acceso directo a posiciones fijas o rangos subyacentes mediante corchetes:

```python
frutas = ["manzana", "naranja", "plátano"]

# Índice simple (comienza en 0)
fruta1 = frutas[1]
print(fruta1)  # 'naranja'

# Rebanado desde el índice 1 hasta el final
desde_indice1 = frutas[1:]
print(desde_indice1)  # ['naranja', 'plátano']

# Rango cerrado a la izquierda y abierto a la derecha [inicio:fin]
frutas_rango = frutas[1:3]
print(frutas_rango)  # ['naranja', 'plátano']
```

### 4.3 Bucle `while` con Puntero de Control

Recorrido manual gobernado por una variable índice y la función de tamaño `len()`:

```python
letras = ["a", "b", "c", "d", "e"]
indice = 0

while indice < len(letras):
    letra = letras[indice]
    print(letra)
    indice += 1
```

### 4.4 Iteración Indexada con `enumerate()`

Permite obtener simultáneamente el índice de la posición y el valor del elemento en cada ciclo:

```python
colores = ["rojo", "verde", "azul"]

for indice, color in enumerate(colores):
    print(f"Índice {indice}: {color}")

# Salida:
# Índice 0: rojo
# Índice 1: verde
# Índice 2: azul
```

---

## 5. Actualización y Mutación de Listas durante el Recorrido

Para modificar los valores de una lista *in-place* (sobre la misma estructura) durante una iteración, se debe escribir sobre su índice posicional.

### 5.1 Mutación con `for` y `range(len())`

```python
numeros = [1, 2, 3, 4, 5]

for i in range(len(numeros)):
    numeros[i] *= 2  # Duplica cada elemento de la lista

print(numeros)  # [2, 4, 6, 8, 10]
```

### 5.2 Mutación con `enumerate()`

```python
palabras = ["Hola", "mundo", "Python"]

for i, palabra in enumerate(palabras):
    palabras[i] = palabra.upper()  # Transforma el elemento a mayúsculas

print(palabras)  # ['HOLA', 'MUNDO', 'PYTHON']
```

### 5.3 Mutación con `while`

```python
numeros = [1, 2, 3, 4, 5]
indice = 0

while indice < len(numeros):
    numeros[indice] += 1  # Incrementa cada valor en 1
    indice += 1

print(numeros)  # [2, 3, 4, 5, 6]
```

---

## 6. Funciones Definidas por el Usuario (`def`)

Las funciones son bloques de código nombrados y reutilizables creados para estructurar algoritmos, evitar duplicación de código y aislar la lógica del sistema.

### 6.1 Anatomía y Sintaxis

```python
def nombre_funcion(parametro1, parametro2):
    # Cuerpo de instrucciones identadas
    resultado = parametro1 + parametro2
    return resultado
```

### 6.2 Parámetros, Argumentos y Retorno con `return`

La instrucción `return` finaliza la ejecución de la función y devuelve un resultado al contexto donde fue llamada:

```python
# Función simple sin parámetros ni retorno
def saludar():
    print("¡Hola! Bienvenido/a a la función.")

saludar()

# Función con parámetros posicionales y retorno explícito
def suma(a, b):
    resultado = a + b
    return resultado

resultado_suma = suma(5, 3)
print("Resultado suma:", resultado_suma)  # 8
```

### 6.3 Parámetros con Valores Predeterminados

Permiten fijar argumentos por defecto en caso de que la invocación no los provea:

```python
def saludar_usuario(nombre="Usuario"):
    print(f"Hola, {nombre}!")

saludar_usuario()        # Utiliza el valor por defecto: "Hola, Usuario!"
saludar_usuario("Juan")  # Reemplaza el parámetro: "Hola, Juan!"
```

### 6.4 Funciones con Lógica Condicional

```python
def es_positivo(numero):
    if numero > 0:
        return True
    else:
        return False

print(es_positivo(5))   # True
print(es_positivo(-2))  # False
```

### 6.5 Composición y Modularidad entre Funciones

Una función puede delegar subtareas en otras funciones ya declaradas para componer algoritmos estructurados:

```python
def cuadrado(numero):
    return numero ** 2

def suma_cuadrados(a, b):
    cuadrado_a = cuadrado(a)
    cuadrado_b = cuadrado(b)
    return cuadrado_a + cuadrado_b

resultado = suma_cuadrados(2, 3)  # (2^2) + (3^2) = 4 + 9 = 13
print("Suma de cuadrados:", resultado)
```

---

## 7. Cuadro Comparativo de Métodos de Lista

| Método / Función | Criterio de Acción | Retorna Valor | Modifica Lista Original | Comportamiento ante Fallo |
| :--- | :--- | :---: | :---: | :--- |
| **`append(elemento)`** | Agrega al final de la lista. | No (`None`) | Sí | No genera errores en tipos habituales. |
| **`list(iterable)`** | Constructor que convierte a lista. | Sí (nueva lista) | No (crea copia nueva) | `TypeError` si no es iterable. |
| **`pop(indice)`** | Elimina según la posición indicada. | **Sí** (el valor extraído) | Sí | `IndexError` si el índice no existe. |
| **`remove(valor)`** | Elimina la 1ª ocurrencia por valor. | No (`None`) | Sí | `ValueError` si el valor no está. |
| **`clear()`** | Vacía la lista completa. | No (`None`) | Sí | Deja la lista como `[]`. |

---

## 8. Preguntas de Autoevaluación y Reflexión

1. **¿Cuál es la diferencia de comportamiento entre `break` y `continue` dentro de un bucle?**
   * `break` rompe y termina la ejecución total del bucle saliendo de él, mientras que `continue` interrumpe únicamente la iteración en curso y pasa de inmediato a la siguiente.

2. **¿En qué casos es preferible utilizar `pop()` sobre `remove()` para eliminar datos de una lista?**
   * `pop()` es la elección adecuada cuando se conoce la posición física del dato (el índice) o cuando se necesita guardar el dato eliminado en una variable para un uso posterior. `remove()` solo sirve cuando se conoce el valor exacto a buscar.

3. **¿Por qué una función que retorna un valor (`return`) otorga mayor flexibilidad que una que simplemente lo imprime (`print`)?**
   * Porque el valor retornado por `return` puede almacenarse en variables, pasarse a otras funciones como argumento o formar parte de expresiones lógicas y cálculos adicionales, mientras que `print()` solo muestra el valor en pantalla y desecha el dato.
