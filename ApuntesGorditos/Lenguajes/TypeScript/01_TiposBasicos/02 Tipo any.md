Es uno de los tipos vistos en los [[01 Tipos TypeScript|tipos de TS]] y en concreto un tipo de dato con el que debemos tener cuidado.

Maneras de declarar un tipo any:

```typescript title="Tipo Any"
let a: any 
let b // como Tipo inferido

```

## ***any***

El problema que tiene any es que acepta cualquier tipo de dato, por lo tanto contradice la misión de typescript.

### Funciones

A la hora de funciones, si no tipamos los parámetros, inferirá que es tipo any.

```typescript title="Tipo any implicito como parametro"
function sumarMultiplos( numero){
 //implementacion..
}
```

en la línea 1, el parámetro numero, no esta tipado, lo que implicara que es tipo any. esto nos arroja un error.

![[tipo-any-funcion.png|650]]

`Parameter 'numero' implicitly has an 'any' type                      `

El parámetro numero es implícitamente tipo any y arroja error, esto se debe a que tenemos configurado que typescript no pueda transcribir a js si hay errores.

#### Parámetros de configuración

Si recordamos un poco:

- El parámetro [[01_Configuracion#strict|Strict]] es el que arroja error por haber un tipo any implícito.

- En la opción [[01_Configuracion#noEmitOnError|noEmitOnError]] del archivo *tsconfig.json* que pusimos true, esto significa que desactiva convertirlo a js si hay tipos de datos .

#### Soluciones de any en funciones

- Activar el Parámetro [[01_Configuracion#noImplicitAny|noImplicitAny]]
	- Solución desaconsejable y solo se usa *como ultimo recurso* y nunca si es posible, pues queremos evitar any a toda costa. 

- Tipar tipo any  -> `{typescript}function sumar(numero: any){}`


```typescript title="Tipo any implicito como explicito"
function sumarMultiplos( numero: any){
 //implementacion..
}
```





