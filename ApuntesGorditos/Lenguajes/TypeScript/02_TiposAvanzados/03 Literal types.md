
## Contexto

fuente: [dev.to](https://dev.to/duxtech/fundamentos-de-typescript-8-tipos-literales-168i)

Necesidad: Limitar los valores para una variable.

### _Ejemplo_

Tenemos una variable _diaActual_, que guarda el día actual de la semana.

`{typescript}var dia: string`

Pero en una variable puede entrar cualquier valor string

```typescript title="Cualquier valor"
var diaActual: string = "lunes"

diaActual = 'perro viejo' // no es el valor de un dia de la semana
```

Ante este problema TS plantea la siguiente solución a la que se le llamo ***Literal type*** 

```typescript title="Literal Type"
var dia: 'lunes'| 'martes'| 'miercoles'| 'jueves'|'viernes'|'sabado'|'domingo'
dia = 'martes'

dia = 'cachorra' // Arroja error
```

### Type Alias

Si se tuviera que operar con varias variables con valores de día, lo mejor es hacer un [Type Alias](https://dev.to/duxtech/fundamentos-de-typescript-7-union-de-tipos-y-type-alias-4o5e) 

```typescript title="Type Alias"
// Type Alias
type diaNombre = 'lunes'| 'martes'| 'miercoles'| 'jueves'|'viernes'|'sabado'|'domingo'

var hoy: diaNombre = 'lunes'
```

De esta manera no habría que repetir todo ese código continuamente y lo hace mas legible.

Type Alias sirve para Union type y todos los demás también.

Si de pronto el día también se identificarse por su numero, siendo lunes 1.

```typescript title="Numero y Nombre del dia"
type numeroDia = 1|2|3|4|5|6|7

var diaHoy: diaNombre | numeroDia
diaHoy = 'viernes'
diaHoy = 3

//Otra opcion: Recoger todo en un type
type Dia= diaNombre|numeroDia

var hoyDia: Dia = 'lunes'
var hoyDia: Dia = 4
```






