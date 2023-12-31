## Estructura de control

Las estructuras de control nos permite dirigir el flujo de la sentencias en ejecución del programa.

### If-Else

```javascript title="If Else"
let hoy = new Date();

if ( hoy.getMonth() == 10 ){
    console.log("Es Noviembre");
}else if(hoy.getMonth() == 11){
    console.log("Es Dicimebre");
}else{
	console.log("No es Noviembre ni Diciembre");
}
```

#### Buscar Alternativas

Para evitar entramados de _if-else if-else_, al ser una lista enumerada de los días de la semana o meses, lo mejor es tener un objeto que actué como diccionario:

```javascript title="Alternativa if-else"
let hoy = new Date();
// Alternativa a if else en estos casos
let diaSemana = {
    0:'Domingo',
    1:'Lunes',
    2:'Martes',
    3:'Miercoles',
    4:'Jueves',
    5:'Viernes',
    6:'Sabado'
}
console.log(diaSemana[hoy.getDay()]);
```

### Switch

```javascript title='Switch'
switch(hoy.getDay()){
    case 0:
        console.log('Domingo');
        break;
    case 1:
        console.log('Lunes');
		break;
    default:
        console.log('Es otro dia');
}
```
