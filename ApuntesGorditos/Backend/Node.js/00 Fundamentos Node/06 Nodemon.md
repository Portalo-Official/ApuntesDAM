
# Nodemon

Nodemon es uno de los paquetes que se recomienda que se instalen de manera global.

Es una herramienta muy útil para el desarrollo de aplicaciones Node.js. Su nombre es una abreviatura de "Node Monitor", y su principal propósito es reiniciar automáticamente tu aplicación Node.js cuando detecta cambios en los archivos del proyecto. 

Esto es especialmente útil durante el desarrollo, ya que te permite ver instantáneamente los efectos de los cambios que realizas en tu código sin tener que reiniciar manualmente el servidor cada vez.

Web: [nodemon.io](https://nodemon.io)

## Instalación

`{bash}npm i -g nodemon`

_-g_ significa que se instala de manera global ( puede que haga falta instalar como root o admin).

## Usando nodemon

`{bash}nodemon --version` --> ver version

`{bash}nodemon app.js` --> ejecutara el proyecto y estará preparado reiniciarlo.

![[nodemon-app.png]]

Cada vez que cambiemos el archivo y guardemos, nodemon reiniciara la aplicación, de esta manera nos ahorramos el escribir una y otra vez `{bash}node app.js`

#### Aviso

En producción no es aconsejable usarlo nunca, si se cae la aplicación se necesitan los errores ( para saber que fallo) y los errores de nodemon son diferentes a los errores de node llegando a confundir.

También nodemon podría reiniciar todo el servidor y es algo que no queremos en producción.
### Usos clave

1. *Reinicio Automático:*
    
    - nodemon monitorea los archivos del proyecto y reinicia automáticamente la aplicación cuando detecta cambios en los archivos JavaScript, JSON, o incluso configuración de nodemon.
    
2. *Facilita el Desarrollo:*
    
    - Al utilizar nodemon, no es necesario reiniciar manualmente el servidor cada vez que realizas un cambio en tu código. Esto agiliza el proceso de desarrollo, ya que puedes ver los resultados de tus modificaciones de inmediato.
    
3. *Personalización:*
    
    - Puedes personalizar la configuración de nodemon a través de opciones en línea de comandos o mediante un archivo de configuración (_nodemon.json_ o [[package.json]]). Esto te permite ajustar el comportamiento según tus necesidades.
    
4. *Compatibilidad con Diferentes Entornos:*
    
    - nodemon es compatible con aplicaciones Node.js desarrolladas con diferentes frameworks, bibliotecas y enfoques. Puedes usarlo con aplicaciones [[00 Express Índice|Express.js]], Koa, Hapi, entre otros.
    
5. *Integración con Proyectos:*
    
    - Es común incluir nodemon como una dependencia de desarrollo en tu proyecto (_devDependencies_) para que otros desarrolladores puedan ejecutar la aplicación de la misma manera.

