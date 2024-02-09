
# Que es

Es un archivo de metadatos que proporciona información sobre el proyecto y sus dependencias.

## Iniciar un proyecto

ya hemos visto como crear el archivo package.json creando un proyecto desde 0 en [[07 npm#Iniciar proyecto|Iniciar un proyecto]],.

package.json tiene varias secciones, una de ellas son las _dependencias_, que pueden ser de producción y de desarrollo.

### Instalar paquete en Dependencia

Al crear un proyecto, el archivo no tendrá ninguna dependencia:

![[package-recien-creado.png|600]]

Si añadimos un nuevo paquete:

`{bash}npm i colors`

![[npm-install-colors.png|600]]

### Instalando paquete como Dependencia de desarrollo

Las dependencias de desarrollo estan en la sección _devDependencies_

`{bash}npm install nodemon --save-dev`

![[devdependencies.png|500]]

Cuando el proyecto vaya a producción, estas dependencias no las compilará.
