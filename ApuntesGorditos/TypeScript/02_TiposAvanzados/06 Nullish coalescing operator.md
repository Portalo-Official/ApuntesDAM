# Resumen

`{javascript} modo: difficulty ?? 1` --> Nullish ___??___ : si es null coge la otra opción.
## Contexto

Sirve para coger valores por defecto.

Supongamos que estamos diseñando un juego.

Tenemos una base de datos de la cual cogemos usuarios del juego. 

Esta recibe una actualización añadiendo un campo (Dificultad) y ahora este puede que en muchos registros no tenga un valor.

Entonces se nos ocurre darle un valor por defecto con el Operador OR ( || )
```typescript title="Valor por Defecto OR"
const difficulty: number | null = null

const user2 = {
    userName: 'Cenizo49',
    modo: difficulty || 1 // Operador OR
}
```

[[03 Operadores#Asignaciones|Asignaciones con operadores]]: Cuando usamos OR, el evalúa a través de falsy.

Ver mas: [truthy y falsy](https://arielfuggini.com/javascript-valores-truthy-falsy/)

falsy da falso en los siguiente casos:
- ' '  (comillas simples vacías)
- "" (comillas dobles vacías)
- \`\` (tildes invertidas)
- 0  (Cero)
- undefined 
- null
- NaN

En nuestro caso el 0  nos puede interesar.

Si ponemos `{typescript}const dificulty: number | null = 0` , lo toma como falso poniendo 1 como opción.

### Nullish

Para estos casos se usa el ***Nullish***, se declara con _??_

```typescript title="Nullish ??"
var user01 = {
    userName: 'Cenizo49',
    modo: difficulty ?? 1
}
console.log("user2 "+user01.modo);
```







