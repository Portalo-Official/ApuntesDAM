## Contexto
Union Type es  cuando nosotros podemos usar mas de un solo tipo cuando podemos referirnos a una variable.

Pagina de interés-> [dev.to](https://dev.to/duxtech/fundamentos-de-typescript-7-union-de-tipos-y-type-alias-4o5e)

*Ejemplo*: tenemos una variable para identificar a un jugador de un equipo, y un jugador se puede identificar por su nombre o por su numero de camiseta

```typescript title="Iddentificar jugador"
var puntuacion = 10
// Por tipo inferido es number
puntuacion= "Messi" // Arroja error
```

## Implementación

Para solventar este caso, hacemos uso de los pipe :

`{typescript}var variable: number | string`

De esta forma no arroja error y solo permite esos tipos.

### Implementación Variables
#### Inconvenientes

Ser los mas estrictos posibles, si nos ponemos a unir muchos tipos, al final no se diferencia nada a tener un any.

Si podemos tener un solo tipo mejor, si no, unir lo justo y necesario.

#### Ejemplo con objetos

```typescript title="Clientes Gasolinera"
type ClienteHabitual = {
    id: number,
    nombre: string,
}
type ClienteSocio = {
    id: number,
    nombre: string,
    tarjetaDescuento: string
}

var cliente1: ClienteSocio | ClienteHabitual = {id: 4, nombre: "Beltran"}

var cliente2: ClienteSocio | ClienteHabitual = {id: 2, nombre: "Rangel",tarjetaDescuento:'25315-12-234'}
```

### Implementación funciones

```typescript title="Union por parametro"
function sumarDos(n: number | string ):number
{
    if(typeof n === 'number'){
        return n+2
    }
    return parseInt(n)+2
}
```

