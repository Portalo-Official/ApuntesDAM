## Contexto

Remplazo del tipo [[02 Tipo any|any]].

Es lo mismo en general todo, solo que la gran diferencia es que TS te obliga a gestionar los caminos para *Unknown*.

![[unkwnon-sinGestion.png|550]]

```typescript title="Gestion de caminos unknown"
function fn(params:unknown) {
    if( typeof params == 'number'){
        params.toFixed
    }
    if( typeof params == 'string'){
        params.toLowerCase
    }

    if(params instanceof HTMLAllCollection ){
        params.item
    }
}
```