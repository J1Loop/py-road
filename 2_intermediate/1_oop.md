# **Programaicón orientada a objetos (POO)**

La **P**rogramación **O**rientada a **O**bjetos (**POO**) es un paradigma de programación introducido en los años 1970s que utiliza objetos y clases en su desarrollo. Se centra en los objetos que los desarrolladores quieren manipular en lugar de la lógica necesaria para manipularlos. Este enfoque es útil para proyectos grandes y complejos, y facilita la modularidad y reutilización del código.

Este paradigma nos permite organizar nuestro código de manera que se asemeje a como pensamos en la vida real. Crearemos **objetos**, que son **instancias de clases**. Las clases son plantillas que definen las propiedades y comportamientos de los objetos.

Cosas cotidianas como un perro o un coche pueden ser representadas como **clases** en un programa. Estas clases tienen diferentes **características**, que en el caso de un coche, podrían ser la marca, el modelo, el color, etc. También tienen **comportamientos**, como acelerar, frenar, etc. A estas **características** se les llama **atributos** y a los **comportamientos** se les llama **métodos**.

Por otro lado, los **objetos** son instancias de las **clases**. Por ejemplo, el *Ford Fiesta* amarillo de tu vecino, con su marca, modelo y color específicos, sería un **objeto** de la clase coche.

<br>

## **Motivación**

La evolución de la programación hacia la POO se fundamenta en la búsqueda de soluciones a la creciente complejidad en el desarrollo de software. Originalmente, no todos los lenguajes de programación admitían POO, lo que refleja su introducción progresiva en este ámbito.

La motivación para adoptar la POO se origina en el desafío de gestionar y reutilizar el código de manera eficiente en proyectos cada vez más complejos. A medida que se desarrollaban aplicaciones con funcionalidades similares, se hizo evidente la necesidad de identificar y reutilizar patrones de diseño comunes, evitando así la redundancia en la creación de soluciones.

Inicialmente, la programación se apoyaba en las funciones para modularizar y reutilizar el código. Las funciones permiten encapsular secuencias de instrucciones bajo un nombre específico, facilitando su invocación repetida sin necesidad de duplicar código. A pesar de su utilidad, las funciones por sí solas presentan limitaciones, especialmente en lo que respecta a la gestión del estado y la conservación de datos a lo largo del tiempo.

- La **POO** aborda estos problemas permitiendo:
  - [**Herencia**](/2_intermediate/1.1_inheritance.md): Facilita la creación de nuevas clases a partir de otras existentes, reutilizando código y creando relaciones jerárquicas.
  - [**Cohesión**](/2_intermediate/1.2_composition.md): Agrupa datos y métodos relacionados en una sola entidad.
  - [**Abstracción**](/2_intermediate/1.3_abstraction.md): Permite enfocarse en lo que hace un objeto sin necesidad de conocer cómo lo logra.
  - [**Acoplamiento**](/2_intermediate/1.4_association.md): Reduce la dependencia entre módulos, permitiendo cambios en uno sin afectar al otro.
  - [**Polimorfismo**](/2_intermediate/1.5_polymorphism.md): Permite que objetos de diferentes clases sean tratados como instancias de una clase común.
  - [**Encapsulamiento**](/2_intermediate/1.6_encapsulation.md): Cada objeto en **POO** puede contener datos y métodos para manipular esos datos, escondiendo su complejidad interna al exterior.

<br>

## **Definiendo Clases**

Una clase en POO es un plano o prototipo a partir del cual los objetos son creados. Define las propiedades y comportamientos que los objetos creados a partir de la clase tendrán.

Lo primero que debemos hacer para comenzar con la POO en Python es definir una clase. Por convención, los nombres de clases en Python son `CamelCase`, es decir, la primera letra de cada palabra en mayúscula.

```python
# Mínima expresión de una clase en Python
class Vehiculo:
    pass
```

Se trata de una clase vacía. Cabe destacar el `pass` para evitar errores de sintaxis. Si después de los `:` no se escribe nada, Python lanzará un error.

Ahora que ya tenemos una clase, podemos crear un objeto de la misma. Para ello, podemos crear una variable y asignarle la clase como valor. En el caso de que tuviese un constructor, deberíamos pasarle los argumentos necesarios entre los `()`.

```python
# Creando un objeto de la clase Vehiculo
coche = Vehiculo()
```

<br>

## **Definiendo Atributos**

Al diseñar clases en la POO, es crucial reconocer la distinción entre dos categorías de atributos:

- **Atributos de Instancia**: Son únicos para cada instancia de una clase. Se definen dentro del método `__init__` y se accede a ellos a través de la instancia.
- **Atributos de Clase**: Son compartidos por todas las instancias de una clase. Se definen fuera de los métodos de la clase y se accede a ellos a través de la clase en lugar de a través de una instancia.

Procedamos con la incorporación de **atributos de instancia** a nuestra clase "**Vehículo**", enfocándonos inicialmente en **atributos** como el modelo y el color. Para ello, utilizaremos el **método** **`__init__`**, también conocido como el **constructor** de la clase, que se ejecuta automáticamente al instanciar un objeto.

```python
class Vehiculo:
    # Constructor de la clase
    def __init__(self, modelo, color):
        # Atributos de instancia
        self.modelo = modelo
        self.color = color
```

Con el método **`__init__`** definido, podemos crear objetos de la clase "**Vehículo**" pasando los valores específicos para modelo y color. La función **`type()`** nos permite verificar que el objeto pertenece a la clase "**Vehículo**".

```python
# Creando vehículo Ford Fiesta, Azul

mi_vehiculo = Vehiculo("Ford Fiesta", "Azul")
print(type(mi_vehiculo)) # <class '__main__.Vehiculo'>
```

La variable **`self`** en el método **`__init__`** es un parámetro que representa la instancia actual de la clase, siendo un requisito en la definición del método.

Los métodos que comienzan y terminan con doble guión bajo, como **`__init__`** son especiales en Python; se les conoce como **métodos mágicos** o **dunder methods** (***d**ouble **under**score*).

Ahora podemos acceder a los atributos de la instancia mediante la notación de punto:

```python
print(mi_vehiculo.modelo)  # Ford Fiesta
print(mi_vehiculo.color)   # Azul
```

Hasta ahora, hemos trabajado con atributos de instancia. Ahora introduciremos un atributo de clase, el cual será compartido por todas las instancias de la clase "**Vehículo**". Un ejemplo podría ser la categoría de todos los vehículos, que podría ser "**Coche**".

```python
class Vehiculo:
    # Atributo de clase
    categoria = "Coche"

    # Constructor de la clase
    def __init__(self, modelo, color):
        # Atributos de instancia
        self.modelo = modelo
        self.color = color
```

El atributo de clase se puede acceder directamente desde la clase, sin necesidad de crear una instancia:

```python
print(Vehiculo.categoria)  # Coche
```

También es accesible desde cualquier instancia de la clase:

```python
mi_vehiculo = Vehiculo("Ford Fiesta", "Azul")
print(mi_vehiculo.categoria) # Coche
```

De esta manera, todos los vehículos creados comparten el atributo de clase, reflejando una propiedad común a la categoría de "Vehículo".

<br>

## **Definiendo Métodos**

El uso del método __init__ que hemos explorado previamente es en realidad una introducción a la definición de métodos en una clase, siendo __init__ un método especial conocido como constructor. Ahora, avanzaremos desarrollando métodos adicionales que proporcionen funcionalidades específicas a nuestra clase "Vehículo", utilizando como referencia el modelo de vehículo.

Proponemos definir dos métodos: arranca y mueve. El primero será un método simple sin parámetros de entrada, que simulará el arranque del vehículo. El segundo aceptará un parámetro que indica la distancia en kilómetros que el vehículo debe moverse. Es importante recordar que self referencia a la instancia actual de la clase y debe preceder a cualquier otro parámetro en la definición del método.

```python
class Vehiculo:
    # Atributo de clase
    categoria = 'Transporte'

    # Constructor de la clase
    def __init__(self, modelo, color):
        print(f"Creando vehículo {modelo}, {color}")

        # Atributos de instancia
        self.modelo = modelo
        self.color = color

    def arranca(self):
        print("El vehículo ha arrancado")

    def mueve(self, distancia):
        print(f"Moviendo el vehículo {distancia} km")
```

Con esta estructura, al crear una instancia de "Vehículo" y utilizar sus métodos, interactuamos con la instancia mediante la llamada de sus métodos, de manera similar a como invocamos funciones, aunque estos métodos pueden aceptar parámetros y ser llamados específicamente sobre instancias de la clase.

```python
mi_vehiculo = Vehiculo("Ford Fiesta", "Azul")
mi_vehiculo.arranca()
mi_vehiculo.mueve(20)

# Creando vehículo Ford Fiesta, Azul
# El vehículo ha arrancado
# Moviendo el vehículo 20 km
```
Este enfoque permite que cada instancia de "Vehículo" tenga comportamientos específicos mediante la invocación de sus métodos, los cuales pueden manipular o hacer uso de los atributos de instancia para realizar acciones, como iniciar el vehículo o moverlo una cierta distancia. Implementar métodos dentro de las clases provee una interfaz clara para interactuar con los objetos, encapsulando la lógica específica del objeto y promoviendo la reusabilidad y organización del código.


## **Conclusión**
La POO es un pilar fundamental en la programación moderna, facilitando el desarrollo y mantenimiento de sistemas complejos al promover un diseño más intuitivo y reutilizable. Con estas bases, puedes comenzar a explorar más a fondo la programación orientada a objetos, experimentando y ampliando tus conocimientos con proyectos más complejos.