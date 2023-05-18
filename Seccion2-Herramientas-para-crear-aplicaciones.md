# Crear una app en React
Existen muchas formas de crear una aplicacion en React, incluso puedes crear tu propio ambiente de desarrollo con herramientas como Babel, Parcel, Webpack, Vite, etc...

## Opciones Modernas para crear aplicaciones en React
* Vite
* Next.js
* Astro
* Remix Run
* Hydrogen (esta es exclusiva de shoppify)

Opciones ya no utilizadas
Create React app
Gatsby

## Recomendaciones por parte del equipo de react
el equipo de React ha menncionado en su documentacion que recomiendan Next.js o Remix para nuevos proyectos

¿Ya no se debe usar Vite?
Aun se recomienda, solo debes tener en cuenta que con Vite tendras que instalar las dependencias manualmente, dependencias para Routing, Consultas HTTPP y mas

¿Por que Next.js o Remix son las mejores recomendaciones?

El equipo de react estuvo trabajando por años con Server Components. Server Components esta disponible desde la v18 

Create react app es una herramienta que ellos habian diseñado para aprender React pero para hacer que soporte Server Components iba a requerir mucho tiempo

[server components](https://es.react.dev/blog/2023/03/22/react-labs-what-we-have-been-working-on-march-2023#react-server-components)

## Programas requeridos para Trabajar con React y Vite

* Node js [mas informacion sobre Node.js](https://developer.mozilla.org/es/docs/Learn/Server-side/Express_Nodejs/Introduction#%C2%BFqu%C3%A9_son_express_y_node)
[descargar](https://nodejs.org/es)

* Powersheel: una terminal de comandos 
[descargar](https://learn.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-windows?view=powershell-7.3)

## Pasos para crear proyecto en React
abrir carpeta de escritorio con `cd desktop`

1. Instalar la ultima version de vite con `npm init vite@latest`

2. Introducir el nombre del proyecto y elegir que tecnologia se estará usando

>Vite utiliza varias tecnologias(JavasCript Vanilla, Vue, React, preact, lit, scelte)

3. Se crea la carpeta, y entramos a esa carpeta por medio de `cd`

4. Se corre el comando `npm install`

* (opcional) Se abre el editor de texto con `code .`

5. `npm run dev` para que corra el servidor, nos genera un link de localhost, copiarlo y pegarlo en el navegador

## Estructura basica de un proyecto de vite
Todas las [herramientas](https://github.com/borgesmj/Udemy-react/blob/main/Seccion2-Herramientas-para-crear-aplicaciones.md#opciones-modernas-para-crear-aplicaciones-en-react) tienen su propia estructura, pero todas comparte algo en comun, es la carpeta `src` y es donde se guardan todos los componentes de React y los modulos de CSS.

El archiv _App.jsx_ es el archivo principal donde se estará trabajando, asi que se borra todo el contenido dejando un solo elemento HTML padre.

## ¿Que es JSX?

Son las iniciales para JavaScript Extension.

Es una extension del lenguaje desarrollada por facebook para React

Parece JavaScript pero muestra un codigo de HTML, y basicamente es un lenguaje de Template que muestra HTML pero tiene todas las funciones de JavaScript

Una vez compilado son archivos JS con funciones y objetos

Existen ciertas reglas en JSX

* A diferencia de HTML, que no es estricto, en JSX si un elemento tiene una etiqueta de apertura, deberá tener la etiqueta de cierre.
* las etiquetas de solo apertura, deberan terminar con />
* Cada componente debe tener un return
* Cada return debe tener maximo **UN SOLO ELEMENTO** a nivel maximo.


```
function App(){
    return(
        <div>
            <h1>Hola Mundo</h1>
            <img src="algunaimagen.jpg/>
        </div>
    )
}
```

>en el caso anterior, el div es el elemento padre, o el elemento en el nivel máximo y solo está permitido uno solo por _return_.
