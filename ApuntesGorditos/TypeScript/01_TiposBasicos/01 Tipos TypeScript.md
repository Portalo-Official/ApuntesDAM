este contenido se practicara en el repositorio e [github](https://github.com/santiagoieshna/TypeScriptPRacticando). en la carpeta 
*01-TiposBasicos* y se llevara a cabo la estructura de directorios de [[01_Configuracion#Configuracion Directorios|Configuracion de directorios]] y los comandos para [[01_Configuracion#Configuración de TypeScript|tsconfig.json]] 
# Tipos Nativos JS

Existen muchos tipos nativos en JavaScript 

- number
- string 
- boolean
- null
- undefined
- function ***(dato simple?? no me suena..)

Recordad que hay datos simples y datos complejos (que son objetos).
Tipos de TypeScript:

- any
- unknow
- arrays
- tuplas
- Enums
- never

TypeScript también tiene una funcionalidad que se denomina *tipos inferidos*

## ¿Qué tipo es un dato?

La mejor manera para saber que tipo es un dato, es preguntarle a la propia maquina con la función `{typescript}typeof()`

````typescript  title="Funcion typeof()"
let variableUno = 1 
let variableDos = [1 , 2, 3]
console.log(typeof(variableUno)) // saldra number
console.log(typeof(variableDos)) // returnara type object
````

El código como ya vimos se usa para convertir a javaScript el comando:
`{bash}tsc                                                                `

Y para correr el archivo javaScript usamos el comando:
`{bash}node dist/typeof_VerTipos.js                                       `

*typeof_VerTipos.js* es como se nombró al archivo y como salida sale:

![[typeof.png|400]]

## Como tipar y tipos inferidos

El tipado en TypeScript se declarara con dos puntos y el tipo de dato:

`{typescript} let nombreVariable: number                                        `

De esta forma typescript sabra que dicha variable será un tipo *number* siempre y tirara error cuando se le asigne un valor de otro tipo.

````typescript hl:5 title="Tipar variable"

let presupuesto: number = 12000
presupuesto = presupuesto - 120 // Todo okey

presupuesto = false // dara error
````

![[error-number.png|700]]

#### tipo inferido

````typescript hl:4 title="Tipo inferido"
var sueldo: number = 200 // Es number siempre
let pagado = true // Es boolean de manera inferida

pagado = "Esta pagado " // Arroja Error
````

![[error-tipo-inferido.png|700]]


