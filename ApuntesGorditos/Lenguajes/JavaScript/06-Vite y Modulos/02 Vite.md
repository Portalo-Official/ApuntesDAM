
## Vite

[Vite.dev](https://vitejs.dev)

[Vite en español GUIA](https://es.vitejs.dev/guide/why.html)

#### Ventajas

1. _Cambia módulos_ en caliente: No tiene que reinstalar todos los módulos cada vez que hay un cambio en uno, cosa que webpack si hacia.

2. Mantiene el estado de sus variables y de los objetos

3. Tiene un código pregenerado de desarrollo. Con webpack se tenia que hacer manualmente.

### Instalación

1. Asegurarnos tener instalado [[Node.js Instalación|Node.js]]
2. hacer uso de el package manager [[07 npm|07 npm]].

Tipar comando `{bash}npm create vite`, pedirá un nombre del proyecto, en nuestro ejemplo se llama _vite-comienzo_ y paso posterior elegir _framework_ y se elegirá vanilla.

![[framework-vite.png]]

 
- Vanilla -> Javascript sin ningún framework.

Siguiente paso: Elegir javascript o typescript. Elegir primero.

Una vez finalizado se habrá creado esta carpeta:

![[proyecto-vite.png]]

En package.json: nos centraremos en el apartado de `{json}"scripts":{}`

![[packagejson-scripts.png]]


**Scripts de Construcción y Desarrollo:**

- Vite utiliza los scripts `{bash}"build"` y `{bash}"{bash}dev"` en el _package.json_ para definir cómo se construye y se ejecuta la aplicación. Estos scripts son invocados comúnmente con comandos como `{bash}npm run dev` o `{bash}npm run build`.

### Instalar dependencias

El proyecto que hemos creado, no ha sido a partir de vite en realidad, si no a partir de Node.

Una vez visto todo esto, tenemos que instalar las dependencias.

con `{bash}npm i` se instalarán las dependencias necesarias del proyecto, esto se ve en el archivo [[package.json]] en `{json}"devDependencies"`.

una vez instalado, npm habrá creado la carpeta _node_modules_, donde se encuentran todas las dependencias.


## Correr script

Una vez instaladas las dependencias y creada la carpeta node_modules:

podemos usar el comando _npm run dev_

![[npmp-run-dev-url.png]]

Este comando levanta un servidor con la pagina web actual que tenemos.

# Estructura de directorios

Estructura de directorios al instalar vite:

- Directorio Public: Donde están los archivos que no necesitan procesamiento (estáticos). Aquí podría ir el directorio assets.

- index.html: Archivo principal de html, todo proyecto siempre leerá el index.html por convención.

- main.js: Archivo principal de js, por convención es el que esta enganchado al index.html principal mente, este llama o importa lo necesario de otros archivos javascript.

- counter.js: Script de js que se exporta a main.js para su uso.

- style.css: La hoja de estilos creadas por defecto para el proyecto.

- Logos de JS y Vite

Los demás directorios o archivos son creados en general por node.js con npm al crear un proyecto o demás paquetes