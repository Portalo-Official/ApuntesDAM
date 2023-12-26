# Funciones

Tienen la palabra reservada `{javascript}function`.

### Problemas con variables

```javascript title="function"
function saludar(nombre){
    console.log('Hola', nombre);
}
var saludar = 234
saludar('Anastasia'); // throw TypeError
```

`{javascript}var` captura el nombre ya sea de una funcion o de un elemento de un objeto global. 

Si se hiciera lo mismo con `{javascript}let` o `{javascript}const` arroja un error _SyntaxError_.

No llamar las variables igual que las funciones.

## Definir variable

Ya hemos visto la _forma tradicional_ en el punto anterior. 

### Definirla en una variable

Podemos crear una funcion anónima `{javascript}function(){}`, no tiene nombre, pero no será problema porque ira ligada a una variable.

```javascript title=
const saludar2 = function(){
    console.log('Hola mundo');
}
saludar2(); // Invocar la funcion
```


## Arguments

todas las funciones tradicionales tienes un objeto implícito llamado arguments.

```javascript title="arguments"
function saludar3(nombre){
    console.log(arguments);
    console.log('Hola',nombre);
}

saludar3('Plakton', 23, 'Patricio')
/**
 * [Arguments] { '0': 'Plakton', '1': 23, '2': 'Patricio' }
 *  Hola Plakton
 */
```

### Funcion flecha

Son mas eficientes que las tradicionales, también evitan problemas con `{javascript}this`.

```javascript title="Arrow Function"
const saludarFlecha = (nombre)  => {
    console.log('Hola', nombre,',Buen dia')
}
saludarFlecha('Melisa');
```

Si la funcion solo va a hacer una cosa en una línea:

`{javascript}const sumar= (a,b) => a + b;`


