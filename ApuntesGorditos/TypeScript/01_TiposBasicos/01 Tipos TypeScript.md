este contenido se practicara en el repositorio e [github](https://github.com/santiagoieshna/TypeScriptPRacticando). en la carpeta 
*01-TiposBasicos* y se llevara a cabo la estructura de directorios de [[01_Configuracion#Configuracion Directorios|Configuración de directorios]] y los comandos para [[01_Configuracion#Configuración de TypeScript|tsconfig.json]] 
# Tipos Nativos JS

Existen muchos tipos nativos en JavaScript 

- number
- string 
- boolean
- null
- undefined
- function 
- [[06 Objetos|Objeto]]

Tipos de TypeScript:

- [[02 Tipo any|any]]
- unknow
- [[03 Arrays#Arrays|arrays]]
- [[04 Tuplas|tuplas]]
- [[05 Enums|Enums]]
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

Tipo inferido sucede cuando declaramos una variable sin indicar su tipo pero le asignamos un valor, la variable cogerá el tipo del valor para siempre.

````typescript hl:4 title="Tipo inferido"
var sueldo: number = 200 // Es number siempre
let pagado = true // Es boolean de manera inferida

pagado = "Esta pagado " // Arroja Error
````

![[error-tipo-inferido.png|700]]

***Importante:*** No confundir con declarar una variable sin asignarle un valor en la misma sentencia.

`{typescript}let variable;//Aqui no se esta infiriendo ningun tipo de dato      `

en este caso  *variable* es de tipo **any**.

```typescript title="Mal tipo inferido"
let variable;
variable = "Que soy? nadie lo sabe.." // Parece que es tipo string
console.log(typeof(variable)) // Saldra string
variable = 24 //No arroja error
console.log(typeof(variable)) // Imprime number
```

En la línea 3, imprime string, pues es el tipo del valor que contiene, pero si en VsCode pasamos por encima el ratón a variable saldrá:

![[mal-tipo-inferido.png|500]]
