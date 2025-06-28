
## Proyecto desde 0

Al crear un proyecto desde 0: `{bash}ng new estudiar-ficheros --standalone false` 

Te da opción de si quieres CSS, Sass y otros, en estos apuntes _usaremos CSS_.

La siguiente opción es si quieres que se habilite Server-Side Rendering (SSR), Elegiremos _NO_, esto nos facilita las cosas y primero lo aprenderemos, después para montar las cosas mas rápido si se usará.

Una vez creado (Puede tardar 1-2 minutos) se habrá creado el repositorio con el nombre del proyecto que se puso:

![[archivos-proyecto.png]]

## Explicación de archivos

Los mas importantes para Angular irán acompañados de una ___A___  

1. _.editorconfig_: Archivo que genera la extensión [EditorConfig]((https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig), permite sobrescribir valores por defecto de nuestro editor de código. 

2. _.gitignore_: archivo dedicado para GIT.  Ignora que archivos subir a los repositorios de GIT, por ejemplo node_modules nunca se querrá subir (ya que se puede autogenerar).

3. _.angular.json_ ___A___:  Archivo de configuraciones para el proyecto.

4. _packge-lock.json_: Archivo generado por Node.js, nunca se toca.

5. _package.json_ ___A___: Archivo generado por Node.js [[package.json]].

6. _README.md_: README en markdow del proyecto de angular por defecto. Aquí se explica como correr la aplicación, como funciones, si hay alguna configuración especial (si hay levantar base de datos o configurar un endpoint etc..), Así los desarrolladores entenderán mejor el proyecto.

7. _tsconfig.app.json_:  Archivo para la configuración de typescript en Angular.

8. _tsconfig.json_: Archivo para la [[01_Configuracion#Parámetros básicos en tsconfig.json|configuración de typescript]]. Ya vienen sus configuraciones para angular.

9. _tsconfig.spec.json_: Configuración para testing en TS.

## Explicación de directorios

1. _.vscode_: configuraciones de vscode, no se toca, no es parte del proyecto.
2. _node_modules_: Carpeta de node donde estan todos los modulos, no se toca.
3. _src_ ___A___: Es el directorio donde se trabajará el 90% del proyecto.


### src

![[estructura-src.png]]

_app_: Destinado para construir toda la lógica del proyecto.
_assets_: Archivos estáticos.
_index.html_: HTML que el proyecto selecciona como DOM principal por defecto.
_main.ts_: Archivo TS main, el que ejecutará principalmente.
_styles.css_: CSS por defecto.

##### app

![[carpeta-app.png]]

Los app.component son un componente.

1. _app-routing.module.ts_: Enrutamiento.
2. _app.component.css_ : Archivo para CSS
3. _app.component.html_: Archivo para HTML
4. _app.component.spec.ts_: Testing (.spec o .test para testing)
5. _app.component.ts_: Archivo ts con decoradores.
6. _app.module.ts_: Es el modulo principal, es un modulo muy importante. Tener cuidado que no crezca mucho.