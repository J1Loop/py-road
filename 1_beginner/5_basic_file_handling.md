
# **Manejo Básico de Archivos en Python**

El manejo de archivos es una habilidad fundamental en la programación, permitiéndote **leer**, **escribir**, **actualizar** y **manipular datos** almacenados en archivos externos. **Python** facilita estas operaciones con su sintaxis clara y librerías poderosas. En este documento, exploraremos los conceptos básicos del manejo de archivos en **Python**, cubriendo 5 aspectos esenciales: **abrir archivos**, **leer archivos**, **escribir en archivos**, **manejar archivos con bloques `with`**, y prácticas recomendadas para el **manejo de errores**.

## **Abrir Archivos**

Para trabajar con archivos en **Python**, primero necesitas abrirlos. Esto se hace con la función incorporada `open()`, que devuelve un objeto archivo.

```python
archivo = open('mi_archivo.txt', 'r')
```

El segundo argumento de `open()` especifica el **modo** en el que el archivo será abierto:

- **`'r'`**: lectura (default)
- **`'w'`**: escritura (sobrescribe el contenido)
- **`'a'`**: anexar (agrega contenido al final)
- **`'r+'`**: lectura y escritura

Siempre recuerda cerrar el archivo después de abrirlo para liberar recursos del sistema:

```python
archivo.close()
```

## **Leer Archivos**

Una vez que tienes un archivo abierto, puedes leer su contenido de varias maneras:

- **`.read()`**: lee todo el contenido del archivo en una cadena de texto.
- **`.readline()`**: lee la próxima línea del archivo.
- **`.readlines()`**: lee todas las líneas del archivo y las devuelve como una lista.

Ejemplo de lectura completa:

```python
archivo = open('mi_archivo.txt', 'r')
contenido = archivo.read()
print(contenido)
archivo.close()
```

## **Escribir en Archivos**

Para escribir en un archivo, primero ábrelo en modo de escritura (`'w'`) o anexado (`'a'`). Luego, usa `.write()` para añadir texto al archivo.

```python
archivo = open('mi_archivo.txt', 'w')
archivo.write('Hola, mundo!')
archivo.close()
```

> **Nota**: El modo **`'w'`** **sobrescribirá** cualquier contenido existente en el archivo. Usa **`'a'`** para añadir contenido **sin eliminar** lo existente.

## **Manejo de Archivos con Bloques `with`**

Usar bloques **`with`** es la práctica recomendada para manejar archivos, ya que asegura que el archivo se cierre automáticamente después de salir del bloque, incluso si ocurren errores.

```python
with open('mi_archivo.txt', 'r') as archivo:
    contenido = archivo.read()
    print(contenido)
```

## **Prácticas Recomendadas y Manejo de Errores**

Manejar excepciones es crucial al trabajar con archivos para prevenir pérdidas de datos o crashes del programa. Utiliza bloques **`try-except`** para capturar errores relacionados con el manejo de archivos.

```python
try:
    with open('mi_archivo.txt', 'r') as archivo:
        contenido = archivo.read()
except FileNotFoundError:
    print("El archivo no fue encontrado.")
```

## **Conclusión**

El manejo eficiente de archivos en Python es una habilidad esencial para cualquier desarrollador. Siguiendo estas prácticas recomendadas, aseguras la integridad de tus datos y la estabilidad de tus aplicaciones. Experimenta con estos conceptos y comienza a incorporar el manejo de archivos en tus proyectos de Python.
