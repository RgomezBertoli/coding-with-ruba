# Principios de los lenguajes

1. Tipos, Variables y Sentencias
2. Operadores
3. Estructuras de control de flujo
4. Bucles
5. Funciones
6. Objetos/Diccionarios
7. Arrays/Colecciones

Todos los lenguajes de programación de alto nivel se rigen más o menos por las mismas directrices aunque luego cada uno tenga sus propias peculiaridades. En esta sección vamos a intentar recoger aquellas partes que son practicamente comunes a todos y que forman la base de entender cómo funcionan los programas.

## 1. Tipos, Variables y Sentencias

Las __variables__ es la forma que tenemos en los lenguajes de almacenar un valor en nuestro programa. Esto es muy útil porque normalmente, en la programación lo que hacemos es hacer operaciones sobre datos, y para poder operar con ellos, lo primero que necesitamos poder hacer es almacenar esos datos para poder realizar operaciones sobre ellos sin perderlos.

Ahora que sabemos que es una variable, ¿a que nos referimos con tipos? Los __tipos__ son los diferentes tipos de valores que podemos llegar a almacenar dentro de una variable. Dentro de cada lenguaje hay muchos tipos, pero hay unos básicos que siempre se repiten de alguna forma dentro de ellos:

- __Number:__ cualquier número.
- __String:__ se llama así a una cadena de caractéres, esto llega desde una letra hasta a una frase completa.
- __Boolean:__ se usan principalmente para diferencia si una afirmación es verdadera o falsa. Sólo puede tener 2 valores: __true__ o __false__.
- __Null:__ indica cuando un valor es nulo o no es válido.

Además de estos hay una serie de tipos complejos que veremos más adelante.

Bien, ahora sabemos que son los tipos y las variables, ¿cómo se crean dentro de nuestro programa? Bueno pues dado que en este curso estamos dando Javascript, en este lenguaje, la forma correcta de definir estos tipos es:

```javascript
var index = 0; //Number

var word = "palabra"; //String

var isLoading = false; //Boolean

var valorNulo = null; //Null
```

Esto que acabais de ver es lo que en programación llamamos sentencia. Las __sentencias__ son las frases que van a ser interpretadas por el programa para realizar una acción. Normalmente vienen formadas por una palabra clave del lenguaje, que le permite al interprete saber que es lo que va a hacer. A través de las sentencias es como vamos a crear nuestras aplicaciones. Hay varios tipos de sentencias, en este caso hemos utilizado la sentencia de expresión.

Sólo para que os vayan sonando, os voy a explicar la existencia de dos tipos complejos:

- __Objeto:__ es un tipo de valor que te permite guardar varios valores si los indentificas a traves de una palabra que llamaremos key.
- __Array:__  en este caso, en vez de permitirte guardar cualquier tipo de valor de una forma ordenada y a la que puedes acceder indicando la posición en la que se encuentra.

## 2. Operadores

En cada lenguajes hay siempre una serie de signos clave que nos permiten a través de 2 valores obtener un tercero. Dependiendo del tipo del valor, los operadores pueden tener diferentes resultados.

### Operador Suma

Este es el semejante al operandor suma proveniente de la matemática y estos son varios ejemplos escritos en Javascript:

```javascript
5 + 6 = 11      //Number + Number = Number

'5' + 6 = '56'  //String + Number = String

6 + '5' = 11    //Number + String = String

'Hola' + 'Adios' = 'HolaAdios' // String + String = String

6 + true = 7    //Number + Boolean = Number

false + 6 = 6   //Boolean + Number = Number

true + false = 1   //Boolean + Boolean = Number

[1,2] + 3 = '123'  //Array de Number + Number = String

3 + [1,2] = '123'  //Number + Array de Number = String

{id:1} + {id:2} = '[object Object][object Object]'  //Objeto + Objeto = String
```

### Operador Resta

Igual que el anterior, es el simil a su homónimo matemático. Aquí unos ejemplos de lo que pasaría con cada tipo en JS:

```javascript
5 - 6 = -1

true - false = 0

5 - true = 4

'5' - 6 = -1

6 - '5' = -1

'hola' - 6 = NaN //Como 'hola' no se puede transformar a número 
                 //esta operación devuelve NaN (Not a Number)
```

Al contrario que con la suma, este operador solo devuelve un valor coherente cuando los tipos pueden transformarse a un número.

### Multiplicación y División

Su funcionamiento es exactamente el mísmo que el visto en la resta, si se intenta multiplicar o dividir un valor que no se puede transforma de forma directa en un número, el resultado de esta operación sera NaN, por lo que los casos de uso son los mismos que los anteriores pero cambiando el operador.

```javascript
5 * 6 = 30

82 / 9 = 9
```

### Operador Resto (%)

El operador Resto (%) nos devolverá el valor restante de una división, por ejemplo:

```javascript
6 % 4 = 2       //Esto se debe a que 6 = 4 * 1 + 2

6 % 3 = 0       //Viene de que 6 = 3 * 2 + 0
```

Al igual que con los tres operadores anteriores, sólo devuelve valor diferente a NaN cuando los valores con los que se opera pueden ser transformados a un valor numérico. Es un operador bastante útil para saber si un número es múltiplo de otro o para saber si es un número par o no:

```javascript
6 % 2 = 0       //Número Par

7 % 2 = 1       //Número Impar
```

### Operadores Lógicos

Este conjunto de operadores permiten al programación poder identificar si dos variables son iguales entre si, o si una es mayor que la otra, incluso saber si tienen o no valor. El resultado suelen ser de tipo __Boolean__. Aqui tenéis una serie de ejemplos.

```javascript
 6 >= 7     //false

 7 < 10     //true

 'hola' <= 'HOLA'   //false, esto se debe a que hace una comparación 
                    //del valor de la cadena en ASCII --> minusculas > MAYUSCULAS

1 == '1'    //true
1 === 1     //true

1 != '1'    //false
1 !== 1     //false
```

Como podeís comprobar, hay dos formas de hacer una comparación de igualdad, '==' y '==='. La diferencia entre uno y otro es la resticción sobre que se comprueba.

- '==' comprueba unicamente si el valor es igual.

- '===' este comprueba tanto si el valor es el mismo como que los tipos tambien coincidan.

Dentro de los operadores lógicos estan el __AND ('&&')__ y el __OR ('||')__ que tienen un comportamiento bastante diferente al esperado por estos operadores.

```javascript
true && "1"     //"1"

'' && "1"       //""

false || {id:1}     //{id:1}

[] || 'hola'    //[]
```

Estos operadores lógicos son los únicos que no devuelven un valor Boolean, si no que devuelven un valor que depende de los valores que se están operando.

En el caso de __AND__ se comprueba si el primer valor se puede transformar a un valor que sea igual a true, y si es así, se devuelve el valor correspondiente al segundo operando, si no, se devolverá el primer operando.

En el caso del __OR__ es al contrario, si el primer operando se puede transformar a false, el valor devuelto será el del segundo operando, si no se devolverá el valor del primer operando.

Y, ¿cómo sabemos que valores son true y cuales false? Pues aquí teneís la tabla de verdad que os dirá cuales son:

| false     | true          |
| --------- | ------------- |
| ""        | Todo lo demás |
| 0         |               |
| false     |               |
| undefined |               |
| null      |               |

## 3. Estructuras de Control de Flujo

Son sentencias que permiten realizar acciones dependiendo de una condición. Son una de las herramientas más importantes dentro de la programación, ya que gracias a ellas podremos crear diferentes flujos en nuestra aplicación para las diferentes causisticas que necesitemos implementar. Los operadores más usados en los controles de flujo son los operadores lógicos, porque nos permiten crear esos valores booleanos que nos permiten diferenciar los casos.

### If...else

La sentencia más común usada para controlar el flujo es el __if__ y su sintaxis es la siguiente:

```javascript
if(condicion){              //Si "condicion" se puede transformar a true
    doSomething();          //se ejecutará doSomething, si no pasará de ello
}
```

Dentro de nuestro código podemos tener situaciones en las cuales queramos que se haga una cosa si se cumple una condición y se haga otra en caso contrario. En estos casos podemos usar anidar estos __if__ usando la palabra __else__

```javascript
if(condicion2){             //Si "condición2" es true, se ejecutará otherStuff,
    otherStuff();           //si no, se ejecutará anotherStuff
} else {
    anotherStuff();
}
```

Y ya por último, si tenemos un caso en el que queremos que se ejecuten diferentes códigos con diferentes condiciones que estan relacionadas entre sí, podemos usar la siguiente sintaxis.

```javascript
if (condition3){            //Si "condition3" es true, se ejcutará something, 
    something();            //y si "condition3" es false y "condition4" es true
} else if(condition4){      //se ejecutará lastThing y si ambas son false,
    lastThing();            //se ejecutará ifThereIsNoOtherOption
} else {
    ifThereIsNoOtherOption();
}
```

### switch

Con esta estructura podemos hacer que se ejecute un bloque de codigo si el valor de la variable que le pasamos es igual a uno de los casos que definamos. Por ejemplo:

```javascript
switch(valor1){
    case 'a':              //Si valor1 == 'a' ejecutará doSomething y
       doSomething();      //saldrá del switch porque tiene un 'break' al final
       break;
   case 'b':
   case 'c':               //Si valor1 == 'b' || valor1 == 'c', se ejecutará
       doSomething2();     //doSomething2 y se saldrá
       break;
   case 'd':               //Si valor1 == 'd' se ejecutará doSomething3
       doSomething3();     //y doSomething4 porque no hay un break entre caso
   case 'e':               //y caso, pero si valor1 == 'e', solo ejecutará
       doSomething4();     //doSomething4 y se saldrá
       break;
   default:                //Este caso se ejecutará siempre que valor1 no sea
       finish();           //igual a ninguno de los caso por defecto
       break;
}
```

Como se puede observar en el ejemplo, todos esos son los casos de uso de esta estructura de control. El __switch__ irá ejecutando los casos de forma consecutiva desde el primer caso que sea true y parará en el momento en el que se encuentre un __break__ en alguno de los casos por los que pase.

---

### Sentencia Break

Esta sentencia sirve para romper un ciclo de ejecución, es decir si estamos en una estructura de control y llega un momento en el que se llega a ejecutar una sentencia break, automáticamente se saldrá de la estructura de control.

Es muy util para los casos en el que estamos dentro de un bucle y queremos que se pare ese bucle cuando se cumpla una condición.

```javascript
for(var i=0; i<10; i++){
    if(i === 7){           //Cuando i sea igual a 7, se ejecutará el break
        break;             //y se saldrá del bucle
    }
}
```

---

### try...catch...finally

El principal uso de esta estructura es el de controlar los errores que puedan surgir en nuestro código y evitar que estos acaben causando una parada en la ejecución de nuestro bloque de código.

```javascript
try {
    doSomething();      //Si en la ejecución de doSomething ocurre un error automáticamente
} catch (error){        //se ejecutará el bloque del catch que recibirá como parámetro
    console.log(error); //ese error.
} finally {             //El finally indica un bloque de código que siempre se va a ejecutar
    clear();            //haya habido un error o no
}
```

No es my recomendable el uso de esta estructura porque tiene un gran impacto en términos de rendimiento, por lo que suele encontrarse únicamente en zonas del código muy sensibles a errorres que no pueden ser controlados, fallos en peticiones a servidor debidos a problemas de red, errores causados por problemas con la falta de memoria, etc...

## 4. Bucles

Este tipo de sentencías es de las más usadas ya que permite recorrer todo tipo de colecciones o arrays. Hay varias formas de crear un bucle pero la idea es la misma. Primero se declara que tipo de operador se usa, se le pone una condición a evaluar en cada ciclo, y en el caso de que no se cumpla la condición se saldrá del bucle y en caso de que se cumpla seguirá ejecutando ciclos. Las condiciones que se ponen en estas sentencias es muy importante porque se podría generar un bucle infinito de forma que tu programa se quedara bloqueado y acabara dando un error fatal. Ahora veremos las diferentes formas:

### for

Esta es sin duda la más usada y la más común ya que su sintaxis es muy sencilla y es muy eficiente. Se escribiría así:

```javascript
for (let i=0; i< array.lenght; i++){
    doSomething()
}
```

Cómo se ve en el ejemplo, en un __for__ se declaran 3 cosas: la primera es el iterador que se va a usar en el bucle, la segunda es la condición que se debe cumplir para seguir ejecutando ciclos y por último una sentencia que modifica el iterador para ir delimitando los ciclos que quedan por ejecutar.

El __for__ tiene variantes que son útiles en ciertas ocasiones para algunas estructuras de datos, pero ya las veremos cuando conozcamos estas estructuras.

### while y do...while

Estas son otra manera de crear un bucle que son muy parecidas entre sí, pero tienen una pequeña diferencia. En el caso del __while__ el bucle se ejecutará despues de hacer una primera comprobación de si la condición se cumple; sin embargo, el __do...while__ ejecutará siempre el primer ciclo antes de hacer la comprobación. Veamos unos ejemplos:

```javascript
while (condition) {     // Aquí, antes de ejecutar la función doSomething, se hará la comprobación de si la condición
    doSomething()       // se cumple, y de ser así, se ejecutará hasta que deje de cumplirse. Sino, no se ejecutará.
}

do {                    // En este caso la función doSomething2 se ejecutará antes de comprobarse la condición
    doSomething2()      // Y si la condición se cumple se seguira ejecutando hasta el momento en el que no se cumpla
} while (condition)     // pero si tras ejecutar la primera vez, ya no se cumple la condición, no se volverá a ejecutar.
```

Todos los bucles se pueden expresar de una de estas 2 formas, incluso puedes llegar a poder transformar un __for__ en un __while__ y vicecersa si quisieras.

## Funciones

Uno de vuestros grandes amigos y enemigos a la vez en el mundo de la programación. Las funciones son bloques de código, a las que damos en la mayoría de casos un nombre, que nos permite organizar varias sentencias dentro del mismo bloque semántico que está aislado del resto. Veamos una función sencilla y cuales son los elementos que las definen:

```javascript
function sum(a, b){
  return a + b;
}
```
En este caso estamos declarando una función que nos permite sumar 2 elementos. Las funciones pueden recibir parámetros que podemos usar como si fueran una variable mas de la función. Por otro lado, a través de la sentencia __return__ podemos indicar el valor que va a devolver esa función en el momento de que hagamos uso de ella, pero, ¿cómo se usa una función?

```javascript
const result = sum(10, 2);    // De esta forma estamos llamando a la función y almacenando el valor que devuelve en una variable
```
En muchos casos, podemos querer que la función no reciba parámetros o que no devuelva nada, pero deberían de ser casos excepcionales.

---
### Sentencia Return

Esta, al igual que el __break__ es una sentencia que además de cortar la ejecución de código en el punto en el que esté, ademas nos permite devolver un valor que se quiera dentro de una función. El uso del __return__ fuera de una función puede tener sentido pero no suele ser habitual encontrarlo, ya que haría la misma función que un __break__. Veamos algunos ejemplos útiles del __return__:

```javascript
function divide(dividend,divider){
  if(divider === 0) {
    return Infinity;
  }

  return dividend / divider;
}

function getIndexOfElementInArray(arr, value) {
  for(const index = 0; index < arr.length; index++){
    if(arr[index] === value) {
      return index;
    }
  }

  return -1;
}
```
En nuestra primera función, hacemos una comprobación de si el divisor es 0 para hacer que devuelva infinito y evitar que haga la operación (En programación, dividir un número entre 0 da error en la mayoría de lenguajes).

En la segunda función, estamos utilizando el __return__ para que en cuanto encuentre el valor buscado, devuelva el indice en el que se encuentra en el array y de esta forma evitar que siga recorriendo todas las posiciones que le falten. Este caso es muy común ya que por ejemplo, si tenemos una colección de 1000 elementos, pero justo el valor que queremos encontrar está en la posición 10, al pasarlo por esta función procesaría únicamente haría 10 ciclos en vez de los 1000 que tiene todo el array.

Y algo muy importante es que si tu pones codigo despues de un __return__, ese código no se ejecutará nunca porque una vez llegue al __return__ dejará de ejecutar ese código.

```javascript
function example(){
  const a,b;
  ...
  return;     // Cuando no indicamos nada despues del return, por defecto se devolverá undefined

  const result = a + b;   // Esta línea nunca se ejecutará porque se encuentra despues de un return
}
```
---

Hay algo especial en como funcionan los lenguajes de programación que permiten que las funciones puedan usar las variables y las funciones declaradas fuera de ellas siempre que compartan el mismo bloque. Es parecida a una jerarquia unidireccional de padre/hijo, una función declarada en el padre puede usar dentro del hijo pero algo declarado en el hijo no puede ser usado en el padre.

```javascript
function vader(){
  var darth = 'Luke, Yo soy tu padre';

  function luke(){
    var son = 'NOOOOOOOOO!!';

    console.log(darth);       //No da error, mostrará 'Luke, Yo soy tu padre'
  }

  console.log(son);           //Devolverá un error de variable no definida
}
```

## Objetos/Diccionarios

### 1 - Declaración y accesos a propiedades

Es la estructura más fácil de entender y la que más se suele utilizar. Un objecto simplemente es un conjunto de claves y valores que están agrupados bajo un mismo ente. En Javascript, todo lo que puedas imaginarte realmente es un objeto por debajo. La forma mas sencilla de declarar un objeto es la siguiente:

```javascript
const ejemplo = {
    clave: "valor"
};
```

El tamaño de los objetos es variable ya que podemos ir añadiendo más claves y valores según necesitemos, incluso una vez ya estén declarados.

```javascript
const ejemplo = {};      // Asi declaramos un objeto inicialmente vacio

ejemplo["clave"] = "valor";
// Con esta línea estaríamos asignando ese valor a esa clave y el resultado sería igual que el ejemplo anterior
```
Ha muchas 2 notaciones de acceder a esos valores a través de las claves. Una es la notación __"."__, que te permite acceder conociendo el nombre de la clave, y la otra es la notación __[]__ que te permite pasarle un valor con el cual acceder a esa clave. Veamoslo con ejemplos:

```javascript
const foo = {
    bar: "valor",
};

console.log(foo.bar);
console.log(foo["bar"]);
// Ambas lineas imprimirían "valor" en la consola.

console.log(foo.fu);    // Como esta clave no existe en el objeto, se imprimiría "undefined"
```
Estas notaciones funcionan tanto a la hora de acceder al valor como cuando queremos asignarle un valor a esa clave:

```javascript
const foo = {};

foo.bar = "valor";
foo["fu"] = "valor";
// Ambas lienas asignarian esos valores a las clavles que hemos declarado
```
Los valores que podemos asignar pueden ser de cualquier tipo que nosotros queramos, incluso otro objeto.

```javascript
const foo = {
    bar: 1,
    bar2: "valor",
    bar3: true,
    bar4: function () {},
    bar5: { foo: "ja" },
    ["bar6"]: 4,          // La notacion [] tambien se puede usar al crear el objeto para darle una clave dinámica
};
```
Hay un caso cuando se intenta acceder o asignar un valor sobre un objeto que no está definido, el error que en otros lenguajes es conocido como NullPointerException.

```javascript
const foo = {};

foo.bar.foo = "error"
console.log(foo.bar.fu);
// Ambas lineas darían un error al ejecutarse ya que la propiedad bar no está definida en el objeto foo
```

### 2 - Funciones útiles de los objetos y operadores

Cómo esta es una estructura básica de javascript, viene con una serie de funciones que hace que trabajar con ellos sea más sencillo. Las funciones que más usaremos vienen definidas en un objeto base que viene ya incluido en el entorno llamado __Object__. Veamos un par de funciones:

```javascript
const ejemplo = {
    foo: "bar",
    foo2: 3,
    foo3: true,
};

const keys = Object.keys(ejemplo);   // Esta función devuelve una colección con las claves del objeto

const values = Object.values(ejemplo);  // En este caso se devuelve una coleccion con los valores

console.log(keys);      // Imprimiría ["foo", "foo2", "foo3"];
console.log(values);    // Imprimiría ["bar", 3, true];
```

Además de estas funciones, podemos usar unos operadores de bucle para recorrer estas propiedades en vez de usar las funciones:

```javascript
const ejemplo = {
    foo: "bar",
    foo2: 3,
    foo3: true,
};

for(const value of ejemplo) {...}     // Aquí value iria teniendo el valor de cada uno de los valores del objeto

for(const key in ejemplo) {...}       // key en este caso tendría las keys del objeto
```

### Arrays/Colecciones

Estas estructuras se utilizan principalmente para hacer una agrupación de elementos similares, de ahí su nombre de Colección. En una colección, ya sea de libros, películas u otra cosa, lo que tenemos es una serie de elementos todos del mismo caracter que están organizados en un sitio con cierto orden, que ahí cada uno pues tiene su idea de orden. Pues los arrays son la representación de esa idea en el mundo de la codificación. Si tienes una serie de items que encajan todos dentro de una misma idea o colección, su mejor forma de representarlos será con un array. Veamos algunos ejemplos:

```javascript
const collection = [10, 23, 50];

const collection2 = new Array(10, 23, 50);
```
Estas son dos formas de inicializar un array, y con ambas se obtendría el mismo resultado. Ahora que sabemos como incializarlos, veamos como podemos setear valores y obtenerlos. La idea es muy parecida a la de los objetos si pensamos en los arrays como objetos cuyas claves son índices númericos, por lo que a la hora de setear u obtener el valor de un índice, los mecanísmos serían muy parecidos a los de un objeto:

```javascript
const collection = [];

collection[0] = "valor1";     // De esta forma estamos indicando que queremos introducir ese valor en el índice 0

console.log(collection[0]);   // Y con esta linea estaríamos imprimiendo ese valor que obtenemos en el índice 0
```
Algo muy importante respecto a los arrays y que a veces es confuso; __el primer indice de un array siempre va a ser 0__. Siempre, la primera posición del array se corresponde con el indice 0, y según vamos añadiendo elementos el índice va aumentando. Gracias a esta idea los arrays nos pueden proporcionar cuantos elementos tenemos dentro de nuestra colección.

```javascript
const collection = [10, 23, 50];  // Esta colección tiene una longitud de 3 elementos

console.log(collection.length);   // Con esta propiedad de los arrays podemos saber cual es la longitud del mismo, en este caso 3
```
Esto es de gran ayuda en muchas ocasiones, ya que en gran variedad de momentos vamos a necesitar saber las longitudes de estas colecciones para poder hacer diferentes lógicas, de las cuales la más común es para hacer la condición que tenemos que poner a un __for__ para recorrer todas las posiciones de nuestro array.

```javascript
const collection = [10, 23, 50];

//  Con este pequeño bucle estaríamos imprimiento todos los valores de nuestra colección
for (const index = 0; index < collection.length; index++){
  console.log(collection[index]);
}
```
Hay un problema con este atributo __length__ y es que como se calcula a través del último indice del array, podemos "trucarlo" para que de una longitud erronea:

```javascript
const collection = [10, 23, 50];

console.log(collection.length);   // Ahora mismo imprimiría 3

collection[32] = 5;

console.log(collection.length)    //Y ahora daría una longitud de 33 porque el último indice que se tiene en el array es 32
```
