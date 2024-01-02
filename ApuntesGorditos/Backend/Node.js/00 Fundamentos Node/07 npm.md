# npm

npm --> node package manager

Con el se instalan los paquetes necesarios para armar las aplicaciones.

En su [Web](https://www.npmjs.com) podemos ver y buscar todos los paquetes que tiene disponibles y su identificaciones.

### Instalar paquete

con el comando `{bash}npm install` o `{bash}npm i` mas el nombre del paquete, instalará las dependencias de el.

Tiene otros argumentos como:

- -g : instalara el paquete de manera global (como en [[06 Nodemon|nodemon]]).
- --save-dev: Instalar paquete en la sección de dependencias de desarrollo.
	- Ejemplo -> `{bash}npm i nodemon --save-dev`
- @X.X.X: Instalar una versión en especifico (X.X.X es la versión correspondiente)
	- Ejemplo -> `{bash}npm i colors@1.0.0`

#### Desinstalar paquete

comando `{bash}npm uninstall` mas nombre del paquete.

### Actualizar paquetes

`{bash}npm update` --> Actualiza todas las dependencias
### Paquetes de importancia

[dotenv](https://www.npmjs.com/package/dotenv): dotenv es un paquete que gestiona las variables de entornos.

[vite](https://www.npmjs.com/package/vite): Es un bundler muy usado, (ver apuntes [[02 Vite|Vite]]).

[nodemon](https://www.npmjs.com/package/nodemon): Visto en la sección anterior, levanta la aplicación y la reinicia cada vez que haya cambios.

[yargs](https://www.npmjs.com/package/yargs): Facilita el análisis y la gestión de argumentos de línea de comandos de manera estructurada.

[express](https://www.npmjs.com/package/express): Express  es un framework para el backend en node.js muy usado.

[nesttjs/cli](https://www.npmjs.com/package/@nestjs/cli): Instala una interfaz de comandos para el framework Nest.js. 

[pnpm](https://www.npmjs.com/package/pnpm): Gestor de paquetes como npm, pero tiene distinta la distribución de dependencias (usado por grandes compañías).

[next](https://www.npmjs.com/package/next): Paquete destinado para React.

[@angular/cli](https://www.npmjs.com/package/@angular/cli): Es un command-line interface, que ayuda a crear con angular muchas cosas rápido.

### Paquetes para tontear

[colors](https://www.npmjs.com/package/colors):  colors tiene funciones para salida por consola con colores y demás.


## Iniciar proyecto

Si quieres iniciar un proyecto sin instalar paquetes primero. 

El comando `{bash}npm init` inicia un proyecto, en el cual deberás elegir:
- Nombre
- Versión
- Descripción
- Archivo de entrada 
- comando para test
- Repositorio de Git
- keywords 
- Autor
- Licencia

![[npm-init.png]]

Todo estos datos, son los que generarán un archivo llamado [[package.json]].

![[npm-init-package.json.png]]

Para entender mas este archivo ver [[package.json]].