## Contexto 

Trabajar con null

_Ejemplo_

Diseñamos una funcion que reciba por parámetro un string y la convierta a number.

```typescript
function toNumber(s: string){
    return parseInt(s)
}

var n = toNumber(null) // Arroja Error
```

El compilador te dirá que un tipo null no es asignable a un tipo string.

Según la version de VsCode, puede no arrojar error, pero al compilarlo no te dejara.

Para que salga el error si o si, de igual la version, habilitaremos la opción [[01_Configuracion#strictNullChecks|strictNullChecks]].

### Problema

En una funcion nos puede entrar por parámetro un null o un undefined ( si no se le dio valor a la variable).

### Solución

Con [[01 Union type|Union Type]] podemos gestionar la entrada de posible null y undefined.

`{bash}function toNumber( s: string | null | undefined )`

Ahora el problema esta en que habrá que gestionar el retorno.

![[solventar-problema-NULL.png]]

TypeScript es bastante inteligente y te arroja que si es null o undefined, no se podrá aplicar la funcion *parseInt()*


```typescript title="Gestionar tipos"
function toNumber2(s: string | null | undefined){
    // Preguntamos si NO existe
    if(!s){
        return 0
    }
    return parseInt(s)
}
```

La sentencia `{typescript}if(variable){}` devuelve *true* si el valor de la variable existe.

