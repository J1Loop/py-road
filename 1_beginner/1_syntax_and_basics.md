# **Sintaxis y conceptos básicos de Python**

Bienvenido al mundo de **Python**, un lenguaje de programación versátil y poderoso que se destaca por su claridad y simplicidad. Este documento te guiará a través de los fundamentos de **Python**, asegurándose de que comprendas la sintaxis básica y los conceptos esenciales para comenzar tu viaje en la programación.

## **Introducción**

**Python** es un lenguaje de programación de alto nivel, interpretado y de propósito general. Diseñado con énfasis en la legibilidad del código, permite a los programadores expresar conceptos en menos líneas de código en comparación con otros lenguajes, como **C++** o **Java**.

## **Comenzando con Python**

Para empezar a escribir tus primeros programas en **Python**, necesitarás tener **Python** instalado en tu máquina. Puedes descargar la última versión de **Python** desde el sitio web oficial: [**python.org**](https://www.python.org/downloads/).

Una vez instalado, puedes escribir tus programas de **Python** usando un editor de texto simple o un entorno de desarrollo integrado (**IDE**) como **PyCharm**, **Visual Studio Code**, o **Jupyter Notebooks**.

> Los archivos de Python tienen la extensión `.py`.  
> 
>  Por ejemplo, `hola_mundo.py`.

### **Hola Mundo**

El primer paso en casi todos los lenguajes de programación es crear un simple programa "Hola Mundo". Este programa en **Python** es tan sencillo como:

```python
print("Hola Mundo")
```

### **Comentarios**

Los comentarios son líneas en tu código que **Python** ignora y se utilizan para dejar notas o explicaciones sobre el código. Los comentarios en **Python** comienzan con un `#`:

```python
# Este es un comentario en Python
print("Hola Mundo")  # Esto también es un comentario
```

### **Variables y Tipos de Datos**

**Python** es un lenguaje de **tipado dinámico**, lo que significa que no necesitas declarar el tipo de variable antes de usarla. Los tipos de datos básicos en **Python** incluyen:

- **Enteros** (`int`): Números enteros, positivos o negativos, sin decimales.
- **Flotantes** (`float`): Números reales con decimales.
- **Cadenas de texto** (`str`): Texto encerrado en comillas simples (`'...'`) o dobles (`"..."`).

```python
edad = 30             # int
altura = 1.75         # float
nombre = "Juan"       # str
```

### **Operadores Básicos**

Python incluye varios operadores básicos para realizar operaciones matemáticas y lógicas:

- **Operadores aritméticos**:
  - `+` (suma)
  - `-` (resta)
  - `*` (multiplicación)
  - `/` (división)
  - `%` (módulo)
  - `**` (exponenciación)

```python
suma = 5 + 3          # 8
diferencia = 10 - 2   # 8
producto = 4 * 2      # 8
cociente = 16 / 2     # 8.0
resto = 10 % 3        # 1
exponente = 2 ** 3    # 8
```

- **Operadores de comparación**:
  - `==` (igual a)
  - `===` (idéntico a)
  - `!=` (diferente de)
  - `>` (mayor que)
  - `<=` (menor o igual que)
  - `<` (menor que)
  - `>=` (mayor o igual que)

```python
a = 10                # int
b = 20                # int
c = '10'              # str

print(a == b)         # False - 10 no es igual a 20
print(a === c)        # False - 10 no es idéntico a '10'
print(a != b)         # True  - 10 es diferente de 20
print(a > b)          # False - 10 no es mayor que 20
print(a >= b)         # False - 10 no es mayor o igual que 20
print(a <= b)         # True  - 10 es menor o igual que 20
print(a < b)          # True  - 10 es menor que 20
```

### **Control de Flujo**

Para controlar el flujo de tu programa, **Python** utiliza instrucciones **condicionales** y **bucles**.

- **Condiciones (`if`, `elif` (else if), `else`)**: Permiten ejecutar bloques de código basados en condiciones específicas.

```python
edad = 20

if edad > 18:
    print("Eres mayor de edad.")
elif edad == 18:
    print("Tienes 18 años exactos.")
else:
    print("No eres mayor de edad.")

# Resultado: "Eres mayor de edad."
```

- **Bucles (`for`, `while`)**: Permiten ejecutar un bloque de código múltiples veces en función de una condición específica.

```python
# Bucle for
for i in range(5):
    print(i)

# Bucle while
j = 0
while j < 5:
    print(j) 
    j += 1
```

## **Conclusión**

Este documento ha introducido los conceptos básicos y la sintaxis de **Python**. A medida que te familiarices con estos conceptos, estarás bien equipado para comenzar a explorar más características de **Python** y a desarrollar programas más complejos. Recuerda, la práctica es clave en el aprendizaje de la programación, así que experimenta con lo que has aprendido y no tengas miedo de cometer errores.
