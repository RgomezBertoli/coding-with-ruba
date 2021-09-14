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

| false | true |
| ----- | ---- |
| "" | Todo lo demás |
| 0 | |
| false | |
| undefined | |
| null | |

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