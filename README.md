# MERN (MongoDB, Express, React, NodeJs)
**Notas del curso de MERN en Udemy**

# ¿Cuanto JavaScript debo saber?
## 1. ¿Cuanto JavaScript debo saber?
No tiene que saberse todo de Javascript para aprender React
* variables
* funciones
* tipos de datos
* ternarios
* objetos
* Promises
* Arrow functions
* Async/Await
* Condicionales
* Array Methods

## 2. Variables con LET
En Javascript se puede utilizar VAR, LET, CONST, aunque var no se usa actualmente
Javascript es tipo dinamico
Las variables con LET se pueden reasignar
en JavaScript se utiliza camelCase

## 3. Variables con CONST
Const no se puede reasignar
Const no pueden iniciar sin un valor
Las variables no pueden ser creadas con numeros o caracteres especiales
Las variables no pueden tener espacios

## 4. Estructura y tipos de datos
undefined
object
Null
Number
String
Symbol
Boolean
Big Int
Function

### Undefined
Desde el momento que se crea una variable, tiene el tipo undefined (si no tiene ningun valor asignado). Luego que se le asigna un valor, cambia el tipo de variable

```
let cliente
console.log(cliente) //undefined
console.log(typeof cliente) //undefined
```

```
let cliente = 20
console.log(cliente) //20
console.log(typeof cliente) //number
```
En JavaScript el tipo de la variable se almacena en el valor y no en la variable como en otros lenguajes de programacion

### Boolean (true or false)
```
const descuento = true
console.log(descuento) // true
console.log(typeof descuento) //boolean
```

### Number
En otros lenguajes, los numeros son tratados por aparte (enteros, decimales...) en JavaScript todos son tratados por igual y son Number
```
const numero1 = 20.20
const numero2 = 30
const numero1 = -100

console.log(typeof numero1) //number
console.log(typeof numero2) //number
console.log(typeof numero3) //number
```

>Los numeros no llevan comillas, cuando tienen comillas, son string

### String o cadena de texto
Se utilizan para representar un texto en pantalla, se coloca un valor entre comillas dobles (") o comillas simples ('), no se pueden mezclar

### BigInt 
Se utiliza para representar numeros muy grandes

```
const numeroGrande = BigInt(67457364786537649745908754875498)
console.log(typeof numeroGrande)
```

>Los numeros BigInt no se pueden mezclar los numeros normales con BigInt, a menos que se haga una conversion

```
const numeroGrande = BigInt(67457364786537649745908754875498)
const numero = 10
console.log(numero + Number(numeroGrande)) //6.745736478653765e+31
```

### Symbol
La caracteristica principal del symbol es que es un dato UNICO

### Null

Variable de tipo nulo

[mas informacion de las variables](https://developer.mozilla.org/es/docs/Web/JavaScript/Data_structures)

## 5. Introduccion a objetos

### ¿que es un objeto?
un objeto puede almacenar una gran cantidad de informacion

ejemplo
```
const nombre = "tablet"
const precio = 300
const disponible = true
```
se puede simplificar de esta manera
```
const producto = {
    nombre: "Tablet",
    precio: 300,
    disponible: true
}
```

las propiedades se colocan con dos puntos (:), a la izquierda de los puntos está la llave, el nombre de la propiedad y a la derecha el valor, si el objeto lleva mas de una pripiedad, debe llevar una coma (,).

de esta manera, en vez de tener tres variables para un mismo producto, se tiene una sola

```
console.log(producto) // {nombre: 'tablet', precio: 300, disponible: true}
console.table(producto)
```

Para acceder a las propiedades, se usa la sintaxis del punto (.)

```
console.log(producto.nombre) // tablet
```

>por medio de la sintaxis del punto, se puede acceder a muchas pripiedades de otros elementos de JavaScript

```
//colocar en la consola
console
//nos arroja todas las propiedades de vista de consola
//o
document
//nos trae las propiedades del DOM
``` 
### Destructuring de un objeto
Aparte de acceder a las propiedades, puede crear una variable nueva

```
const { nombre } = producto
console.log(nombre)
```

### Object Literal Enhacement
Funciona para meter variables que estan fuera del objeto, dentro del objeto

```
const autenticado = true
const usuario = "Miguel"

const nuevoObjeto = {
    autenticado: autenticado
    usuario: usuario
}

console.table(nuevoObjeto)
```

## 6. Manipulacion de objetos


### Modificando valores
```
//Reescribir valor
const producto = {
    nombre: "Tablet",
    precio: 300,
    disponible: true
}

producto.nombre = "Monitor curvo"

console.table(producto)
```

### Añadiendo propiedades


```
//Añadir una nueva propiedad
const producto = {
    nombre: "Tablet",
    precio: 300,
    disponible: true
}

producto.imagen = "imagen.jpg"
console.table(producto)
```
### Eliminar Propiedades

```
//Eliminar una propiedad
const producto = {
    nombre: "Tablet",
    precio: 300,
    disponible: true
}

delete producto.disponible
console.table(producto)
```

### Object freeze
Si no queremos que nadie modifique el objeto, se coloca:

```
const producto = {
    nombre: "Tablet",
    precio: 300,
    disponible: true
}
Object.freeze(producto)
producto.disponible
console.table(producto)
```
### Object Seal

Permite modificar las propiedades existentes, pero no permite añadir ni eliminar

## Destructuring de 2 o mas objetos
```
const producto = {
    nombre: "Tablet",
    precio: 300,
    disponible: true
}
const cliente = {
    nombre: "Miguel",
    premium: true
}

const {nombre, precio, disponible} = producto
const {nombre: nombreCliente, premium} = cliente

console.log(nombre, precio, disponible) // Tablet 300 true
console.log(nombreCliente, premium) // Miguel true
```

>Si hay variables en dos o mas objetos, que se llamen igual, no se puede hacer destructuring, tomando el mismo nombre de las variables porque daria error, si se podria cambiar el nombre dentro del objeto y del destructuring, pero en casos de variables que vengan de API o base de datos no se puede modificar, asi que se crea un alias temporal "_nombre: nombreCliente_" para tengan nombre distinto

## 7. Unir dos o mas objetos en JavaScript

```
const producto = {
    nombre: "Tablet",
    precio: 300,
    disponible: true
}
const cliente = {
    nombre: "Miguel",
    premium: true
}

//const nuevoObjeto = Object.assign(producto, cliente) crea un nuevo objeto uniendo los dos anteriores, pero como los dos objetos tienen una misma variable **nombre** toma el ultimo y se pierde datos, tambien modifica los objetos otiginales, asi que este metodo **NO** es recomendable

// const nuevoObjeto2 = {...producto, ...cliente} este metodo NO modifica los objetos originales, pero solo imprime un **nombre** de los dos objetos

const nuevoObjeto2 = {
    producto: {...producto},
    cliente: {...cliente}
}
console.log(nuevoObjeto2)
```

>**MUY IMPORTANTE** en react no se deben modificar los objetos

## 8. Introduccion a Arrays

Al igual que un objeto, un array puede tener mucha informacion, al igual que un objeto

```
const tecnologias = []
console.log(tecnologias) // []
```

```
const tecnologias = [20, 30, true, 'JavaScript', 'React']
console.log(tecnologias) // (5)[20, 30, true, 'JavaScript', 'React']
console.log(tecnologias[3]) // JavaScript
```

un arreglo se puede utlizar en carritos de compras

## 9. Manipulacion de los Array

```
const tecnologias = ['HTML', 'CSS', 'JavaScript', 'React', 'NodeJs']
console.table(tecnologias)
```

### Añadir elementos al array 
añadiendo un nuevo elemento al final

```
const tecnologias = ['HTML', 'CSS', 'JavaScript', 'React', 'NodeJs']
const nuevoArreglo = [...tecnologias, 'GraphQL']
console.table(tecnologias)
console.table(nuevoArreglo)
```
Añadiendo un nuevo elemento al comienzo
```
const tecnologias = ['HTML', 'CSS', 'JavaScript', 'React', 'NodeJs']
const nuevoArreglo = ['GraphQL', ...tecnologias]
console.table(tecnologias)
console.table(nuevoArreglo)
```
>Metodos como array.push y array.unshift no se deben utlizar en React, porque modifican el arreglo original

### Eliminar elementos

```
const tecnologias = ['HTML', 'CSS', 'JavaScript', 'React', 'NodeJs']
const nuevoArray = tecnologias.filter( function(){
    console.log('desde filter)
}) 
```
>Filter toma una funcion y retorna la cantidad de veces segun el length del array

```
const tecnologias = ['HTML', 'CSS', 'JavaScript', 'React', 'NodeJs']
const nuevoArray = tecnologias.filter( function(tech){
    console.log(tech)
}) 
```
>Escrito de esta manera, regresa cada uno de los elementos del array, mediante una iteracion
```
const tecnologias = ['HTML', 'CSS', 'JavaScript', 'React', 'NodeJs']
const nuevoArray = tecnologias.filter( function(tech){
    return tech !== 'HTML'
}) 
console.log(nuevoArray)
```
>
>Metodos como array.pop y array.shift no se deben utlizar en React, porque modifican el arreglo original

## 10. Destructuring de los Array
```
const tecnologias = ['HTML', 'CSS', 'JavaScript', 'React', 'NodeJs']
const [html, nodejs] = tecnologias
console.log(nodejs) // 'CSS'
```

>en el destructuring de array se extrae el indice, mas no el valor, si se quiere imprimir NodeJS, que está al final se utiliza
```
const tecnologias = ['HTML', 'CSS', 'JavaScript', 'React', 'NodeJs']
const [ , , , ,var5] = tecnologias
console.log(var5) // 'NodeJs'
```

>Se colocan comas con espacios vacios para que imprima el valor que queremos

## 11.Iteradores de arreglos

**forEach**
```
const tecnologias = ['HTML', 'CSS', 'JavaScript', 'React', 'NodeJs'] 
tecnologias.forEach(function(){
    console.log('ejecutando funcion')
})
```

```
const tecnologias = ['HTML', 'CSS', 'JavaScript', 'React', 'NodeJs'] 
tecnologias.forEach(function(tech){
    console.log(tech)
})
```

>forEach accede y ejecuta una funcion por cada elemento en el array

```
const tecnologias = ['HTML', 'CSS', 'JavaScript', 'React', 'NodeJs'] 
tecnologias.map(function(tech){
    console.log(tech)
})
```

>forEach solo te permite acceder y enlistar cada elemento de un arreglo, en cambio map permite crear un arreglo nuevo

## 11. Funciones - Function Declaration
```
function sumar(){
    console.log(2 + 2)
}
sumar()
```

## 12. Funciones - Parametros y parametros default
```
function sumar(a, b = 0){
    console.log( a + b)
}
sumar(10, 20) // 30
sumar(30, 20) // 50
sumar(20, 40) // 60
sumar (30) // 30, suma 30 + 0. ya que al no tener un segundo valor, toma el parametro por default declarado al comienzo de la funcion, de 0, si no se hubiese declarado ese valor por default, el resultado seria NaN
```

### 12. Funciones que retornan valores
```
function sumar(a, b = 0){
    return a + b
}
const resultado = sumar(10, 20)
console.log(resultado)
```

```
function sumar(a, b = 0){
    return [a + b, 'Hola Mundo']
}
const [resultado, holaMundo] = sumar(10, 20)
console.log(resultado)
console.log(holaMundo)
```
### 13. Funciones- function Expression
```
const sumar = function(){
    console.log(2+2)
}
sumar()
```
>la diferencia entre funcion declaration y function expression es que en la segunda NO se puede mandar a llamar antes de declarar la funcion

```
sumar()
function sumar(){
    console.log(2 + 2)
} // 4
```

```
sumar()
const sumar = function(){
    console.log(2+2)
} // Uncaught SyntaxError: Identifier 'sumar' has already been declared
```

### 14. Funciones- Arrow Function

