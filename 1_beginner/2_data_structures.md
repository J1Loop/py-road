# Estructuras de Datos en Python

En este documento, exploraremos las estructuras de datos fundamentales ofrecidas por **Python**. Comprender estas estructuras es esencial para realizar operaciones de almacenamiento, acceso y manipulación de datos de manera eficiente en tus programas.

<br>

## Listas

Las listas en **Python** son colecciones ordenadas y mutables de elementos. Pueden contener elementos de diferentes tipos y son uno de los tipos de datos más versátiles en **Python**.

### Creación de Listas

Puedes crear una lista utilizando corchetes `[]`, separando los elementos con comas. También puedes crear listas con la función `list()`.

Las listas pueden estar vacías o contener elementos de un solo tipo o de diferentes tipos.

Aquí tienes algunos ejemplos que usaremos más adelante en este documento:

```python
vacio = []
numeros = list(1, 2, 3, 4, 5)
frutas = ["manzana", "banana", "cereza"]
mixta = ["texto", 10, True]
```

### Accediendo a Elementos

Para acceder a los elementos de una lista, puedes utilizar su índice entre corchetes `[]`. Los índices comienzan en `0`. Puedes acceder a elementos individuales o a un rango de elementos utilizando la notación de rebanadas.

```python
print(frutas[0])  # manzana
print(numeros[2])  # 3
```

Los índices negativos se utilizan para acceder a elementos desde el final de la lista. `-1` se refiere al último elemento, `-2` al penúltimo, y así sucesivamente.

```python
print(frutas[-1])  # cereza
print(numeros[-3:])  # [3, 4, 5]
```

Las rebanadas de listas devuelven una nueva lista con los elementos seleccionados. Si no se especifica un índice inicial o final, se asume el principio o el final de la lista, respectivamente.

```python
print(frutas[1:3])  # ['banana', 'cereza']
print(numeros[:3])  # [1, 2, 3]
```

### Modificación de Listas

Las listas son mutables, lo que significa que puedes cambiar sus elementos después de su creación.

```python
frutas[1] = "mango"
print(frutas)  # ['manzana', 'mango', 'cereza']
```

### Operaciones Comunes con Listas

Las listas son estructuras de datos versátiles y dinámicas en Python, que soportan una amplia variedad de operaciones. Aquí te presento algunas operaciones comunes que puedes realizar con listas:

- **Añadir elementos**:
  - `append(elemento)`: Añade un elemento al final de la lista.
  - `insert(indice, elemento)`: Inserta un elemento en la posición indicada.
  - `extend([elementos])`: Extiende la lista añadiendo todos los elementos del iterable proporcionado al final.

- **Eliminar elementos**:
  - `remove(elemento)`: Elimina el primer elemento de la lista cuyo valor sea el proporcionado. Arroja un error si el elemento no está presente.
  - `pop(indice=-1)`: Elimina y devuelve el elemento en la posición dada. Si no se especifica índice, `pop()` elimina y devuelve el último elemento de la lista.
  - `clear()`: Elimina todos los elementos de la lista.

- **Ordenar**:
  - `sort()`: Ordena los elementos de una lista (los elementos se ordenan en la propia lista).
    - Puede recibir un parámetro `reverse` para indicar si la lista debe ordenarse en sentido inverso.
  - `reverse()`: Invierte el orden de los elementos de la lista.

- **Búsqueda y más**:
  - `index(elemento)`: Devuelve el índice del primer elemento cuyo valor sea igual al proporcionado.
  - `count(elemento)`: Devuelve el número de veces que el elemento aparece en la lista.


```python
frutas = ["manzana", "banana", "cereza"]

# Añadir elementos
frutas.append("naranja")  # Añade 'naranja' al final
frutas.insert(1, "mango")  # Inserta 'mango' en la posición 1
frutas.extend(["pera", "uva"])  # Añade 'pera' y 'uva' al final

# Eliminar elementos
frutas.remove("banana")  # Elimina 'banana'
ultimo = frutas.pop()  # Elimina y devuelve el último elemento ('uva')
frutas.clear()  # Elimina todos los elementos

# Operaciones de ordenación
frutas = ["manzana", "banana", "cereza"]
frutas.sort()  # Ordena alfabéticamente
frutas.reverse()  # Invierte el orden de los elementos

# Búsqueda
indice = frutas.index("banana")  # Obtiene el índice de 'banana'
conteo = frutas.count("manzana")  # Cuenta cuántas veces aparece 'manzana'

print(frutas)
```

<br>

## Diccionarios

Los diccionarios en Python son colecciones no ordenadas de pares clave-valor. Son mutables y las claves deben ser únicas dentro de un diccionario.

### Creación de Diccionarios

Utiliza llaves `{}` para crear un diccionario, separando claves y valores con `:`.

```python
persona = {
    "nombre": "Juan",
    "edad": 30,
    "ciudad": "Madrid"
    }
```

### Accediendo a Elementos

Puedes acceder a los valores en un diccionario utilizando sus claves.

```python
print(persona["nombre"])  # Juan
```

### Modificación de Diccionarios

Añade o modifica elementos asignando un valor a una clave.

```python
persona["edad"] = 31
persona["profesión"] = "Ingeniero"
```

### Operaciones Comunes con Diccionarios

Los diccionarios son estructuras de datos esenciales en Python que permiten almacenar pares de clave-valor. A continuación, se presentan algunas operaciones comunes que puedes realizar con diccionarios:

- **Agregar o modificar elementos**: Directamente asignando un valor a una clave. Si la clave ya existe, su valor se actualiza; de lo contrario, se agrega el par clave-valor al diccionario.

- **Eliminar elementos**:
  - `pop(clave)`: Elimina la clave especificada y devuelve su valor. Si la clave no existe, se genera un error a menos que se especifique un valor predeterminado.
  - `del diccionario[clave]`: Elimina el par clave-valor especificado por la clave.
  - `clear()`: Elimina todos los elementos del diccionario.

- **Acceder a claves y valores**:
  - `keys()`: Devuelve un objeto de vista que muestra una lista de todas las claves en el diccionario.
  - `values()`: Devuelve un objeto de vista que muestra una lista de todos los valores en el diccionario.
  - `items()`: Devuelve un objeto de vista que contiene pares de tuplas (clave, valor), permitiendo iterar sobre ambos simultáneamente.

- **Copiar un diccionario**:
  - `copy()`: Devuelve una copia superficial del diccionario.

- **Actualización de diccionarios**:
  - `update([otro])`: Actualiza el diccionario con los pares clave-valor de otro diccionario o iterables de pares clave-valor. Las claves existentes se actualizan y las nuevas claves se añaden.


```python
persona = {
    "nombre": "Juan",
    "edad": 30,
    "ciudad": "Madrid"
}

# Agregar un nuevo par clave-valor
persona["hobby"] = "fotografía"

# Modificar un elemento existente
persona["edad"] = 31

# Eliminar un elemento
persona.pop("ciudad")

# Eliminar un elemento con del
del persona["edad"]

# Limpiar el diccionario
persona.clear()

# Copiar un diccionario
otra_persona = persona.copy()

# Actualizar un diccionario
persona.update({"nombre": "Ana", "edad": 25, "ciudad": "Barcelona"})

# Iterar sobre claves y valores
for clave, valor in persona.items():
    print(f"{clave}: {valor}")
```

<br>

## Conjuntos

Los conjuntos en Python son colecciones no ordenadas de elementos únicos. Son útiles para operaciones de conjunto como la unión, intersección y diferencia.

### Creación de Conjuntos

Utiliza llaves `{}` para crear un conjunto. Dado que son colecciones de elementos únicos, duplicar elementos se ignorará.

```python
colores = {"rojo", "verde", "azul"}
```

### Operaciones Comunes con Conjuntos

Los conjuntos en Python son colecciones no ordenadas de elementos únicos, y proporcionan una amplia gama de operaciones para trabajar con ellos.

- **Añadir elementos**:
  - `add(elemento)`: Añade un elemento al conjunto. Si el elemento ya existe, no se añade de nuevo.

- **Eliminar elementos**:
  - `remove(elemento)`: Elimina el elemento especificado del conjunto. Si el elemento no existe, se lanza un `KeyError`.
  - `discard(elemento)`: Similar a `remove`, pero no lanza un error si el elemento no existe.
  - `pop()`: Elimina y devuelve un elemento aleatorio del conjunto. Lanza un `KeyError` si el conjunto está vacío.
  - `clear()`: Elimina todos los elementos del conjunto.

- **Operaciones de conjunto**:
  - `union(otro_conjunto)`: Retorna un nuevo conjunto que contiene todos los elementos de ambos conjuntos.
  - `intersection(otro_conjunto)`: Retorna un nuevo conjunto con los elementos comunes a ambos conjuntos.
  - `difference(otro_conjunto)`: Retorna un nuevo conjunto con los elementos del primer conjunto que no están en el segundo.
  - `symmetric_difference(otro_conjunto)`: Retorna un nuevo conjunto con los elementos que están en uno de los conjuntos, pero no en ambos.
  - `update(otro_conjunto)`: Actualiza el conjunto, añadiendo elementos de otro conjunto.
  - `intersection_update(otro_conjunto)`: Actualiza el conjunto con la intersección de sí mismo y otro conjunto.
  - `difference_update(otro_conjunto)`: Actualiza el conjunto, eliminando los elementos encontrados en otro conjunto.
  - `symmetric_difference_update(otro_conjunto)`: Actualiza el conjunto con la diferencia simétrica entre él y otro conjunto.

- **Pruebas de pertenencia**:
  - `issubset(otro_conjunto)`: Determina si el conjunto es un subconjunto de otro conjunto.
  - `issuperset(otro_conjunto)`: Determina si el conjunto es un superconjunto de otro conjunto.
  - `isdisjoint(otro_conjunto)`: Determina si dos conjuntos son disjuntos (no tienen elementos en común).

### Ejemplos

```python
# Creación de conjuntos
numeros = {1, 2, 3, 4, 5}
otros_numeros = {4, 5, 6, 7}

# Añadir elementos
numeros.add(6)  # {1, 2, 3, 4, 5, 6}

# Eliminar elementos
numeros.discard(6)  # {1, 2, 3, 4, 5}

# Operaciones de conjunto
union = numeros.union(otros_numeros)  # {1, 2, 3, 4, 5, 6, 7}
interseccion = numeros.intersection(otros_numeros)  # {4, 5}
diferencia = numeros.difference(otros_numeros)  # {1, 2, 3}
diferencia_simetrica = numeros.symmetric_difference(otros_numeros)  # {1, 2, 3, 6, 7}

# Pruebas de pertenencia
es_subconjunto = numeros.issubset({1, 2, 3, 4, 5, 6, 7})  # True
es_superconjunto = numeros.issuperset({2, 3})  # True
es_disjunto = numeros.isdisjoint({8, 9})  # True
```

<br>

## Tuplas

Las tuplas en Python son colecciones ordenadas e inmutables de elementos. Ofrecen una forma de agrupar datos juntos de una manera que los hace no modificables.

### Creación de Tuplas

Para crear una tupla, se utilizan paréntesis `()`, y los elementos se separan por comas.

```python
mi_tupla = (1, "Hola", True)
```

Es posible crear una tupla sin paréntesis, simplemente separando los elementos con comas.

```python
otra_tupla = 3.14, "Python", False
```

Para tuplas de un solo elemento, es necesario incluir una coma al final para que Python reconozca la variable como una tupla.

```python
tupla_un_elemento = (5,)
```

### Accediendo a Elementos

Puedes acceder a los elementos de una tupla usando el índice, similar a como lo haces con las listas. Los índices en Python comienzan en 0.

```python
print(mi_tupla[1])  # Hola
```

### Operaciones con Tuplas

Aunque las tuplas son inmutables, puedes realizar varias operaciones de consulta y combinación:

- **Concatenación**: Puedes usar el operador `+` para unir tuplas y formar una nueva.

```python
tupla1 = (1, 2, 3)
tupla2 = (4, 5, 6)
tupla3 = tupla1 + tupla2
print(tupla3)  # (1, 2, 3, 4, 5, 6)
```

- **Repetición**: El operador `*` te permite repetir una tupla un número especificado de veces.

```python
tupla_repetida = (1, 2, 3) * 2
print(tupla_repetida)  # (1, 2, 3, 1, 2, 3)
```

- **Métodos disponibles**:
  - `count(valor)`: Retorna el número de veces que un valor específico aparece en la tupla.
  - `index(valor)`: Retorna el índice del primer elemento con el valor especificado. Arroja un error si el valor no se encuentra.

```python
mi_tupla = (1, 2, 3, 2, 4, 2)
print(mi_tupla.count(2))  # 3
print(mi_tupla.index(3))  # 2
```

- **Desempaquetado de tuplas**: Puedes desempaquetar los elementos de una tupla en variables separadas.

```python
x, y, z = mi_tupla[:3]
print(x)  # 1
print(y)  # 2
print(z)  # 3
```

### Inmutabilidad

Recuerda que no puedes cambiar, añadir o eliminar elementos de una tupla una vez que está creada. Esto incluye no poder cambiar elementos dentro de objetos mutables como listas que puedan estar contenidas dentro de la tupla.

### Usos Comunes

Las tuplas son particularmente útiles en situaciones donde necesitas asegurar que los datos no sean modificados. Son comúnmente usadas para hacer que el código sea más seguro desde el punto de vista de la integridad de los datos, y a menudo se utilizan para devolver múltiples valores desde una función.

<br>

## Conclusión

Las estructuras de datos son fundamentales para manejar eficientemente los datos en tus programas de Python. Cada estructura tiene sus propias características y usos ideales, desde almacenar elementos de manera secuencial en listas hasta asociar datos en forma de pares clave-valor en diccionarios. Experimenta con estas estructuras para entender mejor sus comportamientos y cómo pueden servirte en diferentes situaciones de programación.
