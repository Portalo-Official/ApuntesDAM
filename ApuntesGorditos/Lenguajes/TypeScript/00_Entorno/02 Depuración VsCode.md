## Pasos

Para correr una archivo JavaScript:
`{bash}node dist/typeof_VerTipos.js                                       `

Si queremos depurar código typescript en VsCode hay que seguir una serie de pasos para ello.

### Habilitar mapeo de js
configuración [[01_Configuracion#sourceMap|sourceMap]]   


### Colocar BreakPoint

![[breakpoint.png|500]]


### depurador de VsCode 

-  Pinchar en la opción *create a laucnh.json file*

![[depuradorvscode.png|350]]

- Elegir la opción node.js 

![[depurar-opciones.png]]

Una vez elegida la opción , se genera un archivo launch.json. 

![[archivo-laucn.json.png|600]]


#### launch.json

cambiaremos el name a "Depurar Apuntes" para ver mas adelante que este nombre hay que elegirlo en la depuración.

**IMPORTANTE**: configurar tal cual a partir de ahora. no improvisar aquí.

añadir entre *"program"* y *"outFiles"* el parámetro -> ***preLaunchTask***  

`"preLaunchTask":"tsc: build - tsconfig.json"                       `

![[modificacion-launch.json.png|650]]

Copiarlo tal cual con los espacios, si no, arroja error.


##### Componentes del launch.json
###### version

versión que se esta utilizando del archivo.

###### type

Indica como va a depurar la aplicación (en este caso indica que es con node).

###### request

Petición que esta haciendo.

###### name

Etiqueta para indicar que queremos usar este archivo launch.json, por defecto se llama *Launch Program*.

###### program

De donde va a sacar el código fuente nuestra aplicación.

###### outFiles

Donde va a escupir todo el código js que se ha transcrito desde typescript. 

###### preLaunchTask

La función es hacer una tarea en concreto antes de ejecutarse.

Lo que hace el que se puso en la sección de [[02 Depuración VsCode#launch.json|modificar launch.json]] es *transcribir el archivo ts a js con la configuración de nuestro archivo tsconfig.json*.

### Ejecutar Depuración

Estando en el apartado de debug, nos centramos en el botón de Play.
Clicaremos para ver las opciones, *Depurar Apuntes* es la etiqueta que cambiamos (Launch Program es la etiqueta creada por defecto) que esta indicada en el apartado anterior en el parámetro **[[02 Depuración VsCode#name|name]]**.

![[botonPlayDebug.png]]

Una vez seleccionada la etiqueta que queremos, le damos para correr la depuración (Aquí se elige *Depurar Apuntes* ya que es la que creamos).

Si te arroja erro, mira la guía de [[03_Errores_Depuracion|errores comunes]].

Una vez puesto en marcha debería de  enseñarte ya el código a la altura del BreakPoint y esto significa que hemos hecho todos los pasos exitosos.

## Depuración en ejecución

Una vez estamos depurando ya nos encontramos un entorno reconocido, donde tenemos el apartado de variables.

![[ejecucion-ddepuracion.png]]

También tenemos el menú e depuración como en cualquier entorno, este puede estar suelto de la ventana principal.

![[menu-ddepuracion.png]]


