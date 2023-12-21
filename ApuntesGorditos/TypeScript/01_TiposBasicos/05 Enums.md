Los Enums son un tipo de enumerado como en otros lenguajes. Son una lista de constante que se pueden referenciar.

Es un tipo de dato que se usa constantemente hoy en día:
- Estados de BBDD (Activo, pendiente, eliminado)
- Tallas de ropa (S, M, L, XL)
- Estados de carga a llamadas de API (Loading, Success, Error, IDLE)

## Constantes en JavaScript

En javaScript, las constantes se definen con la palabra reservada ***const***, como en java seria *final*, 

```javascript title=Constantes
const chica ='s'
const mediana ='m'
const grande ='l'
const extragrande ='xl'

chica = 'a' // Arroja al ejecutar
```

Si creásemos un archivo *JavaScript* y asignásemos constantes para la talla de ropa y después la cambiásemos, nos saldría tal error.

![[error-const-reassigment-js.png|350]]

## Constante en TypeScript

El mismo problema anterior sucedería con un archivo Ts.

![[error-const-reasignedvalua-ts.png|500]]

## Enum Type

La manera de declarar un tipo enum en ts:

```typescript title=Enum Type
enum Talla {
    chica= 's',
    mediana='m',
    grande='l',
    extragrande='xl'
}
```

#### Definir variable a enum type 

Para signar el tipo enum a una variable, hay que indicarle el nombre especifico del enum en concreto, en nuestro caso Talla es el nombre de este tipo enumerador.

`{typescript}var variable: Talla`

![[tipar-variable-enum.png|440]]

#### Comparar valores de enum

```typescript title="Comparar y ver valores"
var tallaChaquetaInvierno: string = 'm'
var tallaChaquetaVaquera: Talla = Talla.extragrande
// Ver si corresponde lo mismo
var esMismaTalla: boolean = tallaChaquetaInvierno == Talla.mediana

console.log("Chaqueta de Invierno es de talla mediana? "+ esMismaTalla);
  
console.log("Las chaquetas son de la misma talla? "+ (tallaChaquetaVaquera==tallaChaquetaInvierno));

console.log("Chaqueta Vaqueda Talla: "+ tallaChaquetaVaquera)
```

Código ejecutado:

![[comparar-enums.png|400]]


### Crear enum numéricos

Si creamos un enum sin asignar valor, este cogerá por defecto los valores del 0 hasta el N.º de elementos.

```typescript title="Valores por defecto"
enum Estado {Success, Error, Loading, IDLE}

console.log(Estado.Success); // Imprime 0
console.log(Estado.Error); // 1
console.log(Estado.Loading); // 2
console.log(Estado.IDLE); // 3
```

Si le asignamos un valor numérico al primero, los demás serán el valor anterior +1.

```typescript title="Valores por defecto"
enum Estado {Success=3, Error, Loading, IDLE}

console.log(Estado.Success); // Imprime 3
console.log(Estado.Error); // 4
console.log(Estado.Loading); // 5
console.log(Estado.IDLE); // 6
```

Caso asignando valor a un valor del medio

```typescript title="Valores por defecto"
enum Estado {Success, Error=12, Loading, IDLE} 

console.log(Estado.Success); // 0
console.log(Estado.Error); // 12
console.log(Estado.Loading); // 13
console.log(Estado.IDLE); // 14
```

Resumen: 
- Si no tiene valor el primer elemento -> *Vale 0*
- Si no tienen valor los demás elementos -> *Vale el anterior +1*

*Nota*: Para strings hay que asignar valor a todos

### IFEE

En el archivo javaScript generado por nuestro ts, estará la estructura convertida de nuestro enum llamada ***IFEE***.

```javascript title="Estructura IFEE"
var Talla;
// IFEE
(function (Talla) {
    Talla["chica"] = "s";
    Talla["mediana"] = "m";
    Talla["grande"] = "l";
    Talla["extragrande"] = "xl";
})(Talla || (Talla = {}));
```

##### Que significa IFEE

***IFEE ->*** inmediated invoke function expression

Significa que vamos a tener una función envuelta entre paréntesis y luego la vamos a ejecutar (invocar) inmediatamente

Dicho en español es una *invocación de función inmediata*.

## Ejemplo - código reducido

Un ejemplo mas real de el uso de este tipo es el estado de carga o peticiones a API o servicios.

Tendríamos:
- IDLE -> Aun no se ha ejecutado la carga.
- Loadding -> Cargando.
- Success -> Cargado con existo.
- Error -> Ocurrio un error.

El objetivo de este apartado es ver como influye el hecho de crear un const enum en el archivo javaScript.

`{typescript}const enum LoadingState{Idle, Loading, Succes, Error}`

Declarando solo esa línea en ts, veríamos que en javaScript no hay nada escrito. Esto se debe a que al ser constante el enum, solo se pasara a javaScript a medida que se le da uso cada elemento del enum.

```typeScript title="Const Enum"
const enum LoadingState{Idle, Loading, Succes, Error}

var estado = LoadingState.Succes
```

Si asignamos a una variable el valor de *LoadingState.Success*, en el archivo JS habrá transcrito:

```javascript title="Ts Const Enum convertido"
var estado = 2;
```

La variable estado vale *2* pues es el valor de *LoadingState.Success* en concreto.

De esta forma se consigue un código mas reducido u optimizado.