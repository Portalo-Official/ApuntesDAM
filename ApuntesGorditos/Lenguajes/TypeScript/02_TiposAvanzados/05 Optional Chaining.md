

Optional Chaining Operator se puede usar en 3 instancias.

### Contexto

Tenemos un funcion que devuelve usuarios ( no le des importancia a la implementación, es orientativo) y recibe por parámetro el id.

```typescript title="getUser()"
function getUser( id: number) {
    if(id<0){
       return null // returna nll
    }
    return {
        id:1,
        name:'CachorroTravieso',
        created_at: new Date()
    }
}
var user = getUser(-1)
console.log(user.created_at) //Error user es posiblemente 'null'
```

Nos encontramos en una situación donde podemos obtener o un usuario o un **null**, lo cual daría error.

Existe la funcionalidad Optional Chaining Operator, en la línea 12 se pone un ? al final del objeto:

`{typescript}console.log(user?.created_at)`

Esta *?* , verá si existe (si es un objeto) y el caso de que este exista, permitira acceder a la propiedad (en nuestro caso create_at).

Este objeto era para ***Objetos***, una de las 3 instancias, las otras son arreglos y funciones.

### ***Arrays***

```typescript title="Arrays con Optional Chaining "
const arrayUno = null
console.log( arrayUno?.[0] );
```

### ***Funciones***

```typescript title="funciones con Optional Chaining "
var fn1: any = null
console.log( fn1?.() );
```

Con el Optional chaining nos ahorramos tener que validar nosotros si existe la funcion o no.

Lo que nos ahorramos seria: 

```typescript title="Validar si hay funcion"
function existeFn( fn: any ){
    if(fn){
        return fn()
    }
}
console.log(existeFn(fn1));
```










