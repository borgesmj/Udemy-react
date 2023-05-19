# Instalando Tailwind CSS

## Abrimos la terminal de VS code `ctrl + ñ`

## Se instala la dependencia 
```
npm install -D tailwindcss postcss autoprefixer
```

## se deben haber instalado en el package.json
```
 "autoprefixer": "^10.4.13",
 "postcss": "^8.4.21",
 "tailwindcss": "^3.2.6",
```

## ingresa el comando `clear`

## ahora `npx tailwindcss init -p`

## crea dos archivos

```
postcss.config
tailwind.config
```

## en el archivo index.css se coloca los paquetes

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## en el tailwind.config se dice que archivos van a formar parte de la presentacion del proyecto
```
content: ["index.html","./src/**/*.jsx"],
```

### Esta ultima sintaxis entra en la carpeta src, evalua todos los archivos .jsx

>se vera que no modifica nada, aun no está aplicando, abre nuevamente la terminal externa, deten el server y vuelvelo a arrancar, todo tendra el mismo formato

[Mas informacion](https://tailwindcss.com/docs/installation/using-postcss)
