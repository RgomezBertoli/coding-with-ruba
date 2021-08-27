# Principios de los lenguajes

1. Tipos, Variables y Sentencias
2. Operadores
3. Estructuras de control de flujo
4. Bucles

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
