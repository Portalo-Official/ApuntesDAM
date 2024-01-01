
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

- Vite utiliza los scripts `"build"` y `"dev"` en el `package.json` para definir cómo se construye y se ejecuta la aplicación. Estos scripts son invocados comúnmente con comandos como `npm run dev` o `npm run build`.

## Estructura del directorio

El proyecto que hemos creado, no ha sido a partir de vite en realidad, si no a partir de Node.



