# Estructuras de datos

  1. Objetos
  2. Listas
  3. Pilas y colas
  4. Árboles binarios

Dentro de la programación es necesario tener una forma con la cual podamos representar los diferentes elementos que nos rodean y que podrían ser útiles a la hora de organizar nuestra información. Por eso, se crearon estas estructuras de datos, con ellas tenemos todas las posibilidades para que nuestros programas puedan reflejar perfectamente las situaciones que queremos codificar.

## Objetos

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
