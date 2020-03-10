## APUNTES CURSO JS
- En javascript todos los tipos primitivos son pasados por valor y todos los Objetos son pasados por preferencia

- Destructuracion de argumentos.
Spread : https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Operadores/Sintaxis_Spread


### Métodos arrays
**Propiedades**
* Array.constructor
Especifica la función que crea un prototipo de Objeto.
* Array.length
Refleja el número de elementos en una matriz unidimensional.
* Array.prototype
Permite la adición de propiedades a todos los objetos.

**Métodos**
* Array.from()
Crea un nuevo Array de un objeto iterable o parecido a un array.
* Array.isArray()
Devuelve true si una variable es un Array, de lo contrario devuelve false.
* Array.observe() 
Observa los cambios del Array asincronicamente, similar a Object.observe() para los objetos. Provee un flujo de cambio en orden.
* Array.of()
Crea un nuevo Array con un numero de argumentos variable, sin importar numero o tipo de argumentos.

**Métodos transformadores [Mutator]**
Estos métodos modifican la matriz unidimensional:

* Array.prototype.pop()
Elimina el último elemento de una matriz unidimensional y retorna este elemento.
* Array.prototype.push()
Añade uno o más elementos al final de una matriz unidimensional y retorna la nueva longitud de una matriz unidimensional.
* Array.prototype.reverse()
Invierte el orden de los elementos de una matriz unidimensional - el primero llega a ser el último y el último llega aser el primero.
* Array.prototype.shift()
Elimina el primer elemento de una matriz unidimensional y retorna este elemento.
* Array.prototype.sort()
Ordena los elementos de una matriz unidimensional.
* Array.prototype.splice()
Añade y/o elimina elementos de una matriz unidimensional.
* Array.prototype.unshift()
Añade uno o más elementos al comienzo de una matriz unidimensional y retorna la nueva longitud de la matriz unidimensional.

**Métodos accesores [Accessor methods]**

Estos métodos no modifican una matriz unidimensional y retornan alguna representación de la matriz unidimensional.

* Array.prototype.concat()
Devuelve un nueva matriz unidimensional que comprende esta matriz unidimensional unida con otras matriz unidimensionales y/o valores.
* Array.prototype.join()
Une todos los elementos de una matriz unidimensional en una cadena.
* Array.prototype.slice()
Extrae una sección de una matriz unidimensional y devuelve una nueva matriz unidimensional.
* Array.prototype.toSource()
Devuelve una matriz unidimensional literal representando la matriz unidimensional especificada; puede utilizar este valor para crea una nueva matriz unidimensional. Sobre escribe al método Object.toSource().
* Array.prototype.toString()
Devuelve una cadena representando la matriz unidimensional y sus elementos. Sobre escribe el método Object.toString().
* Array.prototype.valueOf
Devuelve el valor primitivo de una matriz unidimensional. Sobre escribe el método Object.valueOf().
Los siguientes métodos han sido introducidos en JavaScript 1.6.
* Array.prototype.indexOf()
Devuelve el primer índice (el menor) de un elemento dentro de una matriz unidimensional igual al valor especificado, o -1 si ninguno es encontrado.
* Array.prototype.lastIndexOf()
Devuelve el último índice (el mayor) de un elemento dentro de una matriz unidimensional igual al valor especificado, o -1 si ninguno es encontrado.

**Métodos de repetición**
Los siguientes métodos han sido introducidos en JavaScript 1.6.
Varios métodos toman como argumentos funciones que son reinvocadas mientras se procesa la matriz unidimensional. Cuando estos métodos son invocados, la longitud  length de la matriz unidimensional se muestrea y cualquier elemento añadido más allá de esta longitud desde el interior de la reinvocación no es visitado. Otros cambios a la matriz unidimensional (configuración del un valor o la eliminación de un elemento) puede afectar los resultados de la operacion si el método visita luego el elemento cambiado. el comportamiento específico de estos métodos en tales casos no está siempre bien definido y no debería confiarse sobre ello.

* Array.prototype.filter()
Crea una nueva matriz unidimensional con todos los elementos de esta matriz unidimensional para los cuales la funcion de filtrado provista devuelve true.
* Array.prototype.forEach()
Invoca a una funcion por cada elemento en la matriz unidimensional.
* Array.prototype.every
Devuelve verdadero  true si cada elemento en esta matriz unidimensional satisface la función de pruebas  testing provista.
* Array.prototype.map
Crea una nueva matriz unidimensional con los resultados de la invocación de una funcion provista sobre cda elemento en esta matriz unidimensional.
* Array.prototype.some
Retorna verdadero  true si al menos un elemento en esta matriz unidimensional satisface la función de pruebas provista.

## Patrón modulo

Encapsulación de código, nadie puede llamar desde fuera.

Funciones anónimas autoinvocadas (módulo)
(() => {
    'use scrict' // javascript se ejecuta modo estricto
 .. // Nuevo scope por lo que no hay referencia por nombre en las funciones

    // Dentro de este patrón es la única forma de tener acceso a un método desde el exterior
    return {
        nuevoJuego: inicializarJuego
    };
})();
// 2da forma de definirla, identica a la anterior
(function(){
    ..
})();

## URLS
https://mathiasbynens.be/notes/javascript-identifiers
https://mothereff.in/js-variables#%E0%B2%A0%5f%E0%B2%A0
https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/Object

https://javascript-minifier.com/


## SINGLETON

Instancia única de mi clase
Siempre devuelve la misma instancia para una clase.

class Singleton {
    static instancia;
    nombre = '';
    constructor( nombre = '' ) {
        if( !!Singleton.instancia ) {
            return Singleton.instancia;
        }
        Singleton.instancia = this;
        this.nombre = nombre;
    }
}

Al incluir la condición de si existe Singleton.instancia, devolvemos la instancia creada por primera vez, así cada vez que la instanciemos devolverá esa primera instancia.




