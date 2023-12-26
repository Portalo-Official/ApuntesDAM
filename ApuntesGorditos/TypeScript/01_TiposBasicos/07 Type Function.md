## Type Function

`Function` indica a una variable que está *solo puede contener una referencia a una funcion*.

`{typescript}let resultado: Function;`

Saber mas de [Type Function](https://dev.to/duxtech/fundamentos-de-typescript-10-type-function-1lic)
## Funciones

Las funciones se pueden definir de varias formas

### Definición de variable

Usando el famoso ***arrow function*** de JS.

`{typescript}var sumarNumeros = () => { }`

### Palabra Reservada function

`{typescript}function sumarNumeros() { }`

## Tipado de funciones

Lo que hay que tipar aquí, es el retorno (Aunque no hay que olvidar lo parámetros, pero esos ya sabemos hacerlo).

***void***

```typescript title="Tipado en Retorno void"
var fn: () => void = () =>{  }

function fn1():void
{

}
```

***number***

```typescript title="Tipado en Retorno number"
var fn3: () => number = () =>{
    return 2
}

function duplicar(x: number):number
{
    return x*2
}
console.log(duplicar(12)); // -> 24
```

***Usando Variable Arrow Function***

```typescript title="Usando variables con ArrowFunction"
// Primero tipamos su parametro y retorno
var numeroPar: (x: number) => boolean

// implementamos
numeroPar = (x) =>{
    if(x%2 == 0){
        return true
    }
    return false
}

// Llamamos
console.log(numeroPar(4)); // -> true
```

### Configuración

#### Parámetros sin usar

Hay una configuración, para avisar que hay parámetros que no se están usando en la función.

En ts se dice que no lo ha leído, *isn't read*

```typescript title="Usando variables con ArrowFunction"
var fn: (x: number) => number
// implementamos sin usar el parametro x
fn = (x) =>{
    return 2
}
```

La cuestión aquí es, que si no se esta usando a lo mejor estamos implementando mal o sobra dicho parámetro.

Para ello, vamos a habilitar la opción [[01_Configuracion#noUnusedParameters|noUnusedParameters]].

#### Obligar retorno tipado

cuando no se tipa el retorno, de manera implícita muchas veces puede retorna un tipo *undefined*.

Para evitar esto, habilitamos la opción [[01_Configuracion#noImplicitReturns|noImplicitReturns]].

##### Undefined
[[06 Retorno de funciones#undefined|Undefined]] en Js, es cuando una variable *global* no se le ha asignado un valor

```javascript title="Variable Global sin asignar Valor"
function test(t) {
  if (t === undefined) {
    return 'Undefined value!';
  }
  return t;
}

let x; // Declaramos sin definir valor
console.log(test(x));
// Expected output: "Undefined value!"
```

Una función devuelve `undefined` si no se ha `devuelto` un valor.

```typescript title="function sin devolver valor"
function mayorDeEdad( edad: number)
{
 if(edad > 17)
	 return true
}
```

En este código, puede parecer que esta todo bien, pero para `edad < 17` la función no retorna ningún valor.

![[error-reotorno-implicito.png|650]]

Al pasar el ratón por encima de la función, nos indica que el retorno es:

`{python}true | undefined`

El error que nos sale, _Not all code paths returns a value_, es por haber habilitado la opción [[01_Configuracion#noImplicitReturns|noImplicitReturns]]. 

Con esta opción habilitada, la siguiente funcion retorna de manera implicita y es valida porque todos los returns devuelven un valor (puede ser de diferente tipo).

```typescript title="function implícita"
function mayorDeEdad( edad: number)
{
 if(edad > 17)
	 return true
return "Eres menor de edad"
}
```