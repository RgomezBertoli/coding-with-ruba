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

## 2. Clases y Objetos

Las clases es la representación de un elemento de nuestro programa. En ella está contenida toda la información y funcionalidad de ese elemento. Cuando hablamos de objetos en OOP nos referimos a las instancias creadas a partir de una clase. Veamos un ejemplo simple para diferenciarlos:

```javascript
// Con la palabra class declaramos que vamos a crear una clase
class Persona {
  nombre;
  apellidos;

  // Todas las clases necesitan declarar un método llamado "constructor" para que sea llamado cuando se crea un objeto de esa clase
  constructor(name, surname){
    super(...arguments);
    this.nombre = name;
    this.colorOjos = name;
  }

  function getFullName() { return this.nombre + " " + this.apellidos; }
}

const persona1 = new Persona("Carla", "Martínez");    // Con está sentencia estamos creando un objeto de la clase Persona

console.log(persona1.getFullName());    // Imprime "Carla Martinez"
```
A través de las clases somos capaces de ir abstrayendo nuestro programa creando todas las clases que creamos necesarias para representar la situación que se nos requiere. Saber trabajar bien con estas clases va a ser clave para que nuestras aplicaciones sean más fáciles de entender y de explicar.

Ahora veamos elementos importantes que encontramos en las clases.

  - El __constructor__ es el metodo que se invoca cuando se crea un objeto de esa clase. Si queremos dar valores iniciales a nuestro objeto es el mejor momento, pero si no queremos hacer nada en el momento de creación, podemos no declarar ningún constructor y se nos creará el objeto con los valores por defecto que hayamos indicado.
  
  - Los __atributos__ son el conjunto de propiedades de las que está compuesta nuestra clase. Pueden ser de cualquier tipo que queramos, incluso del tipo de otra clase. Estos attributos suelen contener la información importante para que nuestra clase funcione a la perfección.

  - Los __métodos__ son el conjunto de funciones que tiene nuestra clase que podemos usar una vez tengamos un objeto. Normalmente nos permiten manipular los atributos de la clase y agrupar una serie de funcionalidad que nos es interesante dentro de nuestra clase. Cuanto más concretos y menos responsabilidades tengan mejor, porque así será mas fácil que sean reutilizables.

---

## El This

Este elemento existe dentro de las clases para poder tener acceso a los attributos y a los métodos declarados dentro de nuestra clase de forma sencilla. En la mayoría de lenguajes, este this siempre apunta a la clase, pero en Javascript tiene una peculariedad que veremos más adelante cuando demos conceptos más avanzados.

---

Estos métodos y attributos pueden declararse de forma que puedan usarse y accederse desde los objetos que creemos de la clase o podemos hacer que sean __privadas__. Con esto conseguimos lo que hemos llamado __encapsulación__, permitiendonos decidir que cosas de nuestra clase queremos que se puedan usar y cuales de ellas las queremos para nuestro propio uso y que no estén disponibles para nadie más. Vamos a ver como se hace esta privatización:

```javascript
class Person {
  name;
  surname;
  #indentityNumber;

  #digest(){
    console.log("Haciendo la digestión");
  }

  eat(){
    this.#digest();
  }
}

const person1 = new Person();

person1.#indentityNumber;    //  Esta linea lanzará un TypedError porque no se puede acceder a esa propiedad

person1.#digest();           // Esto lanzará un TypedError porque igual que antes no se puede acceder a este método

person1.eat();               // Esto imprimirá "Haciendo la digestión" porque el método se ha llamado desde dentro de un metodo de la misma clase
```
Y luego existen los atributos __static__, que como la palabra indica, significa que son estáticos, por lo que siempre tendrán el mismo valor se acceda desde donde se acceda e incluso podrán usarse sin tener que crear un objeto de la clase, porque al ser estáticos, se entiende que da igual el objeto, siempre deberían dar el mismo resultado.

```javascript
class Person {
  static legs = 2;

  static move(){
    console.log("Moviendo");
  }
}

console.log(Person.legs);   // Se imprimiría un 2 ya que es su valor estático

Person.move();              // Se imprimiría "Moviendo"
```
Este típo de métodos son utiles para crear utilidades y agruparlas bajo una misma abstracción, como podría tratarse de objetos como el Math de javascript que te expone una serie de propiedades y métodos que pueden ser utilizados sin crear un objeto.