# Diagrama de Flujo retro y demas cosas interesantes :D

![image](https://github.com/Paulmak21/diagrama-flujo-retro/assets/140537985/07219daf-4968-44fd-be42-673d185f8ecd)

# **La programacion imperativa y declarativa**

Que son?

#### Empezaremos por la ***programacion imperativa*** explicando que es y para que se utiliza:

1. La programación imperativa es el enfoque de programación más antiguo y básico
2. Tu describes las instrucciones paso-a-paso para como se ejecutara un programa y te de los resultados deseados.
3. Con el control de flujo de tu codigo puedes seguir el codigo facilmente. Eso si cuanto mas añadas al codigo y mas avances, mas dificil y complejo sera comprenderlo y leerlo.
4. Tienes el control y adaptabilidad total de tu estructura para ejecutarlo como quieras para tu aplicacion.
5. Como tienes mas codigo con el que trabajar es mas probable que estes pasando mas tiempo debuggeando codigo que con la programacion declarativa

#### ***Programacion declarativa:***

1. La principal diferencia es que describe lo que desea que logre el programa en lugar de como debe ejecutarse
2. Aqui TU defines los resultados que deseas que se logren en un programa/aplicacion sin describir su flujo de control
3. Es menos complejo y requiere menos codigo(haciendolo mas facil de entender/leer)
4. Diseñar el codigo fuente es mas dificil por su sintaxis mas comlicada y los algoritmos que se deben implementar
5. Facil de optimizar
6. Codigo conciso y preciso lo que conlleva a un codigo mas eficiente

Aqui algunos ejemplos de `lenguajes imperativos`:
- Java
- C
- Python
- Ruby
- PHP

Aqui algunos ejemplos de `lenguajes declarativos:`

- Sql
- Lenguajes de marcado (e.g. HTML)
- JavaScript


## [***Lenguajes de programacion Basados en C y los 7 mas usados hoy en dia:***](https://survey.stackoverflow.co/2023/#technology-most-popular-technologies)

- JavaScript
- TypeScript
- Java
- C#
- C++
- PHP
- Rust

# ***Lenguajes compilados e interpretados***

### **Lenguajes compilados**

Los lenguajes compilados son convertidos directamente a codigo maquina que el procesador puede ejecutar. Como resultado, suelen ser mas rapidos y mas eficientes al ejecutarse en comparacion con los lenguajes interpretados. Para esto necesitamos el uso de un compilador

###### Lenguajes compilados puros son C, C++, Erlang, Haskell, Rust y Go.
### **Lenguajes interpretados**

Estos lenguajes ejecutan linea por linea el programa y a la vez ejecutan cada comando. Necesitamos de un interprete(Que es esto?) El interprete a la vez que va traduciendo lo que dice el texto para nosotros poder entenderlo. Si llega a encontrar un error se detiene.(Estos lenguajes pueden ser mas lentos que los compilados)

###### Lenguajes interpretados son PHP, Ruby, Python y JavaScript.

Una de las principales diferencias entre los lenguajes compilados e interpretados es cuando el compilado ejecutar todo el codigo mientras que el interpretado lo hace `JIT` (Just In Time) esto quiere decir que interpreta el codigo segun se necesita.


# Diferencia entre `var` y `let` 

El alcance de `var` las declaracion de `var` son de ambito golbal o local(de funcion). Para que entendais esto: `var` es de ambito global cuando esta declarada fuera de una funcion lo que quiere decir que se puede utilizar esa variable donde sea y es local cuando esta declarada dentro de una funcion y solo puede usarse dentro de esa funcion si intentaramos utilizarla fuera de la funcion nos daria error.


```javascript
    var peluche = "Hey world!";
    
    function newFunction() {
        var osito = "Hello";
    }
```

Aqui, la variable peluche esta de forma global pero la variable osito esta dentro de una funcion

```javascript
  var peluche = "Hey world!";
    
    function newFunction() {
        var osito = "Hello";
    }
    console.log(hello); // error: Hello no esta definido
```

Recibiremos un error diciendo que `osito` no esta disponible fuera de la funcion

###### Las variables `var` pueden ser redeclaradas y actualizadas

```javascript
var cerdo = "Jamon";
var cerdo = "Panceta mejor";
```

O podemos hacerlo de otra forma:

```javascript
var cerdo = "Jamon";
cerdo = "Panceta mejor";
```

"Mecanismo de Elevacion `var`"

Este mecanismo que tiene integrado JavaScript hace que las variables y funciones declaradas se muevan arriba del inicio de tus comandos antes de ejecutar.

Por ejemplo:

```javascript
console.log(R2D2);
var R2D2 = "Bip-Bop"
```

Lo interpreta algo asi como esto:

```javascript
var R2D2;
	console.log(R2D2); // R2D2 sin definir
R2D2 = "Bip=Bop"
```

Las variables `var` se elevan arriba del codigo y deja el valor como no definido.

### Problemas con `var` 

```javascript
var pregunta = "Oye que hora es?";
var minutos = 5;

if (minutos > 3) {
	var pregunta = "Pregunta cuanto queda para las..."
}

console.log(pregunta) // "Pregunta cuanto queda para las..." 
```

Aqui le decimos que en vez de que nos de la variable que indicamos primero si pasa que el valor que le damos a `minutos` es mayor a 3 nos diga otra cosa.

Esta claro que no pasa nada si quieres que la definicion principal no se diga si sucede tal cosa pero se vuelve un problema cuando no te das cuenta de que la variable `pregunta` ya ha sido definida antes

# Let 

Ahora es preferible la utilizacion de `let`  porque resuelve los problemas antes mencionados con `var`

La declaracion de `let` ahora es de ambito local o de funcion. Lo que nos quiere decir es que ahora `let` vive dentro de un bloque {}. Voy a explicar:

```javascript
let pregunta = "Oye que hora es?";
let minutos = 5;

if (minutos > 3) {
	let tiempo = "Pregunta cuanto queda para las..."
	console.log(tiempo); // "Pregunta cuanto queda para las..."
}

console.log(tiempo) // tiempo no esta definido
```

Aqui vemos que usar `tiempo` fuera del bloque nos da de vuelta un error. Esto es porque las variables de `let` estan dentro de una funcion y no pueden salir de ellas.

## Let puede ser actualizado pero no redeclararlo

Como `var` las variables `let` pueden ser actualizadas

```javascript
let R2D2 = "Bip=Bop";
R2D2 = "Bop-Bop";
```

Pero al redeclararlo nos dara error:

```javascript
let R2D2 = "Bip-Bop";
let R2D2 = "Bop-Bop"; // error: 'R2D2' ya ha sido declarado
```

De igual manera si la variable esta definida dentro de diferentes funciones no habra error:

```javascript
let R2D2 = "Bip-Bop";
if (true) {
	let R2D2 = "Bop-Bop";
	console.log(R2D2); //"Bop=Bop"
}
console.log(R2D2); //"Bip=Bop"
```

Lo que hace que `let` sea tu opcion mas adecuada comparado con `var` es que ya no te tienes que molestar en saber si has usado un nombre para una variable u otra ya que `let` existe solo dentro de su funcion.

# Diferencias entre `,' && "

Al intentar escribir algo en el console.log() nos encontraremos muchas veces con complicaciones al escribir el codigo y una de ellas son muchas de las palabras que hay en ingles y que usan ' para unir palabras por ejemplo:

```javascript
console.log('It's time to wake up guys!')// nos saldra un error de sintaxis porque tenemos 3 ' y el sistema no sabria identificar el prinipio y el final
```

Otro ejemplo para prevenir esto es la utilizacion de las `backtick literals` que tenemos a nuestra mano.

Para resolver el problema de arriba y en caso de combinacion de la otra forma de escribir nuestro string podemos resolverlo asi:
```javascript
console.log("My girlfriend's friend likes the word "Biblioklept"")// Esto resultaria en error
```
Que podemos hacer nosotros para evitar esto? Queda una solucion **`**.
```javascript
console.log(`My girlfriend's friend likes the word "Biblioklept"`)// Utilizando estas backtick literals podemos evitar los errores mencionados arriba
```
