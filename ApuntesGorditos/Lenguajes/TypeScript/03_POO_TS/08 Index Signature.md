### Contexto

Cuando estemos trabajando con algún arreglo u objeto, este puede tener objetos indexados.

En el caso que tengamos un objeto que este contenga propiedades dinámicas, nosotros podemos asignarle el tipo utilizando *index asignature*.

```typescript title="Index Asignature"

class DiccionarioUsuarios{
// Index Asignature
    [id: string]: string
}

let diccionarioUsuarios = new DiccionarioUsuarios() 

diccionarioUsuarios['1a'] = 'usuario 1'
diccionarioUsuarios['a1'] = 'usuario 2'
diccionarioUsuarios['a2'] = 'usuario 3' 

console.log(diccionarioUsuarios);
```


