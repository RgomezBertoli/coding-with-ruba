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
