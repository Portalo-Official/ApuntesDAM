
## Tipos de alertas

Hoy en día tienen poco uso, ya hay muchas librerias que te ofrecen alertas mas bonitas.

Estas instrucciones son bloqueantes: bloquean la ejecución del navegador web. No seguirá ejecutando ninguna línea de código hasta que quite la alerta
### Alert

Ventana emergente que te muestra un mensaje con un botón _ok_ para finalizar.

`{javascript}alert('mensaje')`

### Prompt

Ventana emergente que te muestra un mensaje y un campo de escritura para introducir datos con un botón _ok_ para afirmar y _Cancel_ para cancelar.

`{javascript}prompt('¿Cual es tu nombre?')`

`{javascript}prompt('¿Cual es tu nombre?', 'Nombre')` -> 2º param es un placeholder.

Esta funcion retorna un string que el usuario escriba.

**Cancel**-> Retorna `null`
**ok**-> Retorna el valor del campo.
### Confirm

Sirve para confirmar una opción seleccionada.

`{javascript}confirm('mensaje')`

retorna true o false.

```javascript title="Confirmar borras datos"
const seleccion = confirm('¿Estas seguro de borrar los datos?')
if(seleccion){
	borrarDatos();
}
```


