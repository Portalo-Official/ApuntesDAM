Veremos dos tipos de depuración aquí, la segunda es solo por saber manejar el navegador un poco más, pero no se le dará importancia.
## Depuración en VScode

Hay varias maneras para depurar js en vs code, vemos las mas directa.

### breakpoint

Un _breakpoint_ tiene como funcion pausar la ejecución del script, mostrando toda la información relevante definido en ese momento.

Se coloca pinchando a la izquierda del número de línea.

![[breakpoint-vscode.png]]

### Correr Depuración

Run -> Start Debugging

![[startdebug-vscode.png|400]]

Salen varias opciones, elegir Node.js.

![[debugging.png]]


## Depuración en Navegador
### Fuentes en navegador

Para conocer que archivos esta cargando nuestro navegador, nos vamos a la sección de *inspeccionar Elemento*-> _Red (NetWork)_.

![[Archivos-cargados-navegador.png]]

Los archivos podemos inspeccionarlos en la pestaña _Fuentes (Sources)_.

![[soirces-navegador.png]]

### Breakpoint  

Nos colocamos justo en la línea del número donde queremos hacer un breakpoint y clicamos.

![[breakpoint-navegador.png]]


### Correr depuración

Una vez establecido el breakpoint, podemos ver que tenemos los controles de ejecución como en cualquier otro IDE.

_Nota_: Si no te deja pulsar _step over_, _step into_ (comando de depuración), buscar actualizar cobertura.

![[depurar-navegador.png]]


Hay formas de proteger el código para que no sea tan manipulable desde el navegador.



