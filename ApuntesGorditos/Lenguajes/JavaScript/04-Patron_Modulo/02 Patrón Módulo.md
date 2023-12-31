# Patrón Módulo

Es el patrón mas común que existe en js.

## IIFE

IIFE ->**E**xpresión de **F**unción **I**nvocada **I**nmediatamente.

La idea es crear una funcion y llamarla inmediatamente, de tal forma que **no** tenga una referencia por nombre.

De esta forma es imposible llamar al objeto o elemento desde fuera.

```javascript title='IIFE'
(function(){
	//Logica de la funcion
})();

// En forma arrow function
(()=> {
	//Logica de la funcion
})();
```

El ultimo paréntesis es cuando lo invocamos, imagina cuando llamar a una funcion:

`{javascript}getNombre()` --> con el paréntesis es como se invoca a la funcion. Solo que en                                       IFEE no hay nombre.

### Ejemplo de anonimato

```javascript title='IIFE ejemplo'
(()=> {
    const personaje= 'Ana'
    console.log(personaje);
})(); //
console.log(personaje);
```

La funcion se auto invoca y muestra por consola 'Ana'. pero después se intenta llamar desde fuera y arroja error.

![[fuera-de-scope-iife.png]]


## Use Strict

Fuente: [Modo Estricto](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Strict_mode)

Javascript tiene 2 maneras de tratar con el código, el [sloppy mode](https://developer.mozilla.org/es/docs/Glossary/Sloppy_mode) y el modo estricto. Por defecto esta el sloppy mode.

El modo estricto tiene varios cambios en la semántica normal de JavaScript:

1. Elimina algunos errores silenciosos de JavaScript cambiándolos para que lancen errores.
2. Corrige errores que hacen difícil para los motores de JavaScript realizar optimizaciones: a veces, el código en modo estricto puede correr más rápido que un código idéntico pero no estricto.
3. Prohíbe cierta sintaxis que probablemente sea definida en futuras versiones de ECMAScript.

Los navegadores que no admiten el modo estricto ejecutarán el código con un comportamiento diferente, hacer pruebas de las características mas relevantes.

**Importante**= No andar mezclando modo estricto con modo sloppy, puede llegar a dar comportamientos no esperados.

### Aplicación Use Strict

```javascript title='Para todo el script'
'use strict'
// Todo el script que siga tal cual
```

```javascript title='Para funciones'
function strict() {
  // Sintaxis del modo estricto a nivel de función
  "use strict";
  function nested() {
    return "¡Y yo también!";
  }
  return "¡Hola!  ¡Soy una función en modo estricto!  " + nested();
}
function notStrict() {
  return "Yo no soy estricto.";
}
```

```javascript title='Para módulos'
function strict() {
  // debido a que este es un módulo, soy estricto por omisión
}
export default strict;
```