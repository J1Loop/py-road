# **Funciones en Python**

Las funciones en **Python** son bloques de código reutilizables diseñados para realizar una tarea específica. Al utilizar funciones, puedes mejorar la legibilidad y la eficiencia de tu código, permitiéndote reutilizar código y organizar tu programa de manera más efectiva.

### **Creación de Funciones**

Para definir una función en **Python**, utilizas la palabra clave `def`, seguida del nombre de la función, paréntesis y dos puntos. Dentro de los paréntesis, puedes opcionalmente incluir uno o más parámetros.

```python
def saludo(nombre):
    print(f"Hola, {nombre}!")
```

Para llamar a una función, simplemente utiliza su nombre seguido de paréntesis. Si la función espera parámetros, debes pasar los argumentos correspondientes dentro de los paréntesis.

```python
saludo("Mundo")  # Hola, Mundo!
```

### **Valores de Retorno**

Las funciones pueden devolver valores utilizando la palabra clave `return`. Esto te permite capturar el resultado de una función para utilizarlo en otra parte de tu código.

```python
def sumar(a, b):
    return a + b

resultado = sumar(5, 3)
print(resultado)  # 8
```

Las funciones pueden aceptar varios parámetros y retornar múltiples valores usando tuplas, lo cual es útil para operaciones que necesitan procesar o devolver más de un valor.

```python
def operaciones_basicas(a, b):
    suma = a + b
    resta = a - b
    return suma, resta

resultado_suma, resultado_resta = operaciones_basicas(10, 5)
print(f"Suma: {resultado_suma}, Resta: {resultado_resta}") # Suma: 15, Resta: 5
```

<br>

## **Paso por Valor y Referencia**

En **Python**, el comportamiento de paso de argumentos a funciones puede parecer un poco diferente en comparación con otros lenguajes, debido a su modelo de "paso por asignación de objeto". 

- **Paso por valor**: Esto ocurre con tipos inmutables (como enteros, flotantes y cadenas). **Python** pasa una copia del valor, por lo que modificaciones dentro de la función no afectan al dato original.
- **Paso por referencia**: Con tipos mutables (como listas y diccionarios), se pasa una referencia al objeto real, por lo que cambios en el objeto dentro de la función se reflejan fuera de ella.

```python
def modificar_lista(lista):
    lista.append(4)

mi_lista = [1, 2, 3]
modificar_lista(mi_lista)
print(mi_lista)  # [1, 2, 3, 4]
```

Este ejemplo muestra cómo los cambios en una lista (tipo mutable) dentro de una función afectan a la lista fuera de la función, mientras que los cambios en un entero (tipo inmutable) no lo hacen.


```python
def modificar_lista(mi_lista):
    mi_lista.append(4)

def modificar_entero(mi_entero):
    mi_entero += 1
    print("Dentro de la función:", mi_entero)

lista = [1, 2, 3]
entero = 10

modificar_lista(lista)
print("Lista modificada:", lista)

modificar_entero(entero)
print("Entero no modificado:", entero)
```

<br>

## **Funciones Lambda**

Las funciones lambda en **Python** son funciones anónimas definidas con la palabra clave `lambda`. Son útiles para cuando necesitas una función por un corto período de tiempo, y generalmente se utilizan en combinación con funciones como `filter()`, `map()`, y `reduce()`.


```python
sumar = lambda a, b: a + b
print(sumar(5, 3))  # 8
```

```python
numeros = [1, 2, 3, 4, 5]
pares = list(filter(lambda x: x % 2 == 0, numeros))
cuadrados = list(map(lambda x: x**2, numeros))

print("Números pares:", pares)
print("Cuadrados:", cuadrados)
```

<br>

## **Uso de \*args y \*\*kwargs**

Estos argumentos permiten funciones más flexibles que pueden aceptar diferentes números de argumentos posicionales o de palabras clave.

- `*args` permite a una función aceptar un número arbitrario de argumentos posicionales.
- `**kwargs` permite aceptar un número arbitrario de argumentos de palabras clave.

```python
def mi_funcion(*args, **kwargs):
    print(args)  # Tupla de argumentos posicionales
    print(kwargs)  # Diccionario de argumentos de palabras clave

mi_funcion(1, 2, tres=3, cuatro=4)
```

```python
def mi_otra_funcion(*args, **kwargs):
    for arg in args:
        print(arg)
    for key, value in kwargs.items():
        print(f"{key}: {value}")

mi_otra_funcion(1, 2, tres=3, cuatro=4)
```

<br>

## **Decoradores**

Los decoradores permiten modificar el comportamiento de una función o método. Se definen con el símbolo `@` seguido por el nombre del decorador. Son útiles para agregar funcionalidad a funciones existentes de una manera limpia y legible.

```python
def mi_decorador(func):
    def envoltura():
        print("Algo antes de la función.")
        func()
        print("Algo después de la función.")
    return envoltura

@mi_decorador
def decir_hola():
    print("Hola!")

decir_hola()
```

Un decorador es una función que toma otra función y extiende su comportamiento sin modificarla explícitamente.

```python
def decorador_simple(func):
    def wrapper():
        print("¡Algo está sucediendo antes de la función!")
        func()
        print("¡Algo está sucediendo después de la función!")
    return wrapper

@decorador_simple
def decir():
    print("¡Mundo!")

decir()

```

<br>

## **Caching de Funciones**

El caching de funciones puede mejorar significativamente la eficiencia de funciones que realizan cálculos pesados almacenando los resultados de llamadas anteriores. El caching permite guardar los resultados de operaciones costosas para reutilizarlos en llamadas futuras.


```python
cache = {}

def fibonacci_cache(n):
    if n in cache:
        return cache[n]
    if n < 2:
        return n
    else:
        resultado = fibonacci_cache(n-1) + fibonacci_cache(n-2)
        cache[n] = resultado
        return resultado

print(fibonacci_cache(30))
```

Desde Python 3.2, puedes utilizar el decorador `@functools.lru_cache` para este propósito.

```python
from functools import lru_cache

@lru_cache(maxsize=None)
def fibonacci(n):
    if n < 2:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

print(fibonacci(30))
```

## **Programación Funcional**

La programación funcional es un paradigma de programación que trata las funciones como ciudadanos de primera clase, promoviendo el uso de funciones puras, inmutabilidad, y operaciones de alto orden. **Python** soporta conceptos de programación funcional, permitiéndote escribir programas más expresivos y concisos.

```python
numeros = [1, 2, 3, 4, 5]
cuadrados = list(map(lambda x: x**2, numeros))
print(cuadrados)  # [1, 4, 9, 16, 25]
```

La programación funcional enfatiza el uso de funciones puras y evita el estado compartido y los datos mutables.

```python
from functools import reduce

numeros = [1, 2, 3, 4, 5]
suma = reduce(lambda x, y: x + y, numeros)
print("Suma:", suma)

# Filtrar números impares
impares = list(filter(lambda x: x % 2 != 0, numeros))
print("Impares:", impares)
```

## **Conclusión**

Las funciones son una parte esencial de **Python**, y te permiten escribir código más modular, reutilizable y legible. Al comprender cómo funcionan las funciones en Python, puedes mejorar tu capacidad para escribir programas más efectivos y eficientes.