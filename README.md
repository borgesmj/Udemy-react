# MERN (MongoDB, Express, React, NodeJs)
**Notas del curso de MERN en Udemy**

## ¿Cuanto JavaScript debo saber?
No tiene que saberse todo de Javascript para aprender React
*variables
*funciones
*tipos de datos
*ternarios
*objetos
*Promises
*Arrow functions
*Async/Await
*Condicionales
*Array Methods

## Variables con LET
En Javascript se puede utilizar VAR, LET, CONST, aunque var no se usa actualmente
Javascript es tipo dinamico
Las variables con LET se pueden reasignar
en JavaScript se utiliza camelCase

## Variables con CONST
Const no se puede reasignar
Const no pueden iniciar sin un valor
Las variables no pueden ser creadas con numeros o caracteres especiales
Las variables no pueden tener espacios

## Estructura y tipos de datos
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
console.log(typeof clinete) //undefined
```

```
let cliente = 20
console.log(cliente) //20
console.log(typeof clinete) //number
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

