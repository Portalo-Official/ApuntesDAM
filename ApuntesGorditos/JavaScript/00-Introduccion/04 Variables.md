## Variables

### var 

Uno de los principales problemas del `{javascript}var` es que me permite reemplazar propiedades y objetos propios del objeto global windows. 

Usar `{javascript}let` y `{javascript}const` -> No sobrescriben, las variables de objetos globales. 

#### Error de declaración

```javascript 
console.log( miVariable);

var miVariable = 'Santiago'
```

Debería dar un error, porque la variable no esta definida cuando la llaman en la línea 1. Pero en lugar de eso, arroja _undefined_ (tipo de dato js).

Javascript antes de ejecutar, hace un abarrido para cachear el nombre de todas las variables.

Esto es un problema serio. porque te deja manipular la variable antes de estar inicializada.

### let

Soluciona los problemas de var, es una variable que se le pude cambiar la referencia y valor.


### const

Es una constante como en cualquier lenguaje, no se puede cambiar valores o referencia a objetos (los objetos si pueden cambiar internamente).




