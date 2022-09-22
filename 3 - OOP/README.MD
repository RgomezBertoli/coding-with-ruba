# Programación Orientada a Objetos (OOP)

  1. Principios Básicos.
  2. Clases y Objetos
  3. Constructores
  4. Atributos públicos y privados
  5. Herencia
  6. Composición
  7. This
  8. Interfaces (Polimorfismo)

La programación orientada a objetos ha sido y sigue siendo uno de los paradigmas de programación más usados desde su aparición. La idea detrás de este paradigma es que todo lo que nosotros hagamos debería estar reflejado en una abstracción que se la llama __Objeto__, en el cual representamos un elemento de nuestro programa. Estos objetos tendrán en su interior una serie de propiedades y métodos que tienen sentido en su conjunto. Y dentro de nuestra app iremos creando esos objetos para usar las capacidades que tienen implementadas.

## Principios Básicos

Hay 4 principios básicos que vamos a ir viendo durante este tema:

  - Abstracción
  - Encapsulación
  - Herencia
  - Polimorfismo

### Abstracción

Entendemos como abstracción a la capacidad de coger un ente y ser capaz de desmigarlo de forma que acabe pudiendo ser definida en un conjunto de elementos característicos con los cuales podamos distinguir de forma inequivoca este ente. Cuanto mejor sea nuestra capacidad de abstraer, mejor podremos gestionar la complejidad y reducirla hasta el nivel que cualquier persona pueda entender el funcionamiento del conjunto.

Veamos un ejemplo para entender mejor la idea. Cojamos un sistema complejo como puede ser el de la conducción de un coche, si para conducir necesitaramos conocer el funcionamiento del total del sistema, nunca seríamos capaces de conducir, pero si en vez de entender el sistema entendemos como funcionan sus elementos característicos no nos hace falta conocer los detalles del funcionamiento. Por ejemplo, algunos elementos característicos de este sistema son los pedales, el volante, el motor, las ruedas y la palanca de cambios; conociendo estos elementos y cómo interactuan con el sistema podremos entender como se conduce.

### Encapsulación

La encapsulación nos permite decidir que partes de nuestros elementos característicos son accesibles y cuales de ellos son totalmente privados y no pueden ser manipulados por ninguna fuente externa. De esta forma limitamos las capacidades de nuestros elementos a las que nosotros queramos dejar expuestas. 

Si seguimos con el ejemplo de nuestro coche como antes, si nosotros cojemos únicamente el volante, lo único que se nos permite hacer es girarlo (esta acción es la pública), pero obviamente, dentro del volante, fuera del acceso del usuario, hay ciertas piezas y mecanísmos que hacen posibles que hagamos esos giros pero están totalmente ocultos (son privados).

### Herencia

La herencia es el proceso por el cual un objeto obtiene cualidades que vienen de otro objeto. Por ejemplo, si hablamos de herencia genetica, un hijo obtendría las cualidades genéticas de sus padres. En el mundo de la programación, cuando nos referimos a herencia nos solemos enfocar en como un elemento característico hereda las propiedades y funciones de otro.

Imaginemos que en nuestro programa definimos un objeto Mamifero que tiene las propiedades de numero de patas y si tiene cola o no y que tiene la capacidad de andar. Por otro lado definimos un objeto Perro que hereda del objeto Mamifero, por lo tanto ese perro tambien tendrá esas propiedades y la capacidad de andar.

### Polimorfismo

Este es un concepto bastante más complicado de explicar. La idea inicial es que el polimorfismo es la capacidad de un objeto de ser único pero de tener diferentes formas. Por lo que nuestro objeto sería capaz de actuar como cualquiera de sus formas si fuera necesario. Para este ejemplo podríamos pensar en que definimos nuestro objeto Persona, y que las formas podrían ser oficios que es capaz de desemplear esa persona, como Cocinero, Carpintero, Mecánico, etc. Así nuestra Persona podría trabajar dentro de nuestro sistema como cualquiera de esos oficios (cualquiera de sus formas).