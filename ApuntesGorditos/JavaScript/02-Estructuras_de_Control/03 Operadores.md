
## Operadores
### Operadores Lógicos

- `{javascript}>` --> Mayor que
- `{javascript}>=` --> Mayor igual que
- `{javascript}<` --> Menor que
- `{javascript}>=` --> Menor igual que
- `{javascript}!=` --> Distinto de
- `{javascript}==` --> Igual que (No importa el tipo de dato)
- `{javascript}===` --> Igual que (Importa el tipo de dato)

`{javascript} 5 == '5' --> true`
`{javascript} 5 === '5' --> false`

### Lógica Booleana

`!` --> (NOT) negación
`&&`--> (AND) conjunción
`||`--> (OR) disyunción 

#### Asignaciones

En asignaciones, los operadores, se rigen por [truthy y falsy](https://arielfuggini.com/javascript-valores-truthy-falsy/). 

```javascript title="Asignaciones"
console.warn('Asignaciones');
const soyUndefined = undefined;
const soyNull = null;
const soyFalso = false;

// && -> todas tienen que ser verdadero, si no ponde false por defecto
const a1 = true && 'Hola Mundo' && 150; // asigna lo ultimo
const a2 = false && 'Hola Mundo' && 150; // no asigna nada
console.log({a1, a2});

// || mira todo, y si es falso undefine o null coge lo que ya no sea ninguno de eso.
const a3 = soyFalso || 'Ya no soy falso';
const a4 = soyFalso || soyNull || soyUndefined || 'Ya no soy falso';
const a5 = soyFalso || soyNull || soyUndefined || 0 ||'Ya no soy falso' || 'Soy yo mismo';
console.log({a3, a4, a5});
```

_falsy_ da falso en los siguiente casos:
- ' '  (comillas simples vacías)
- "" (comillas dobles vacías)
- \`\` (tildes invertidas)
- 0  (Cero)
- undefined 
- null
- NaN

### Operador Ternario

`{javascript}let variable = (condicion) ? valor1 : valor2`

en funcion:
`{javascript}const elMayor = (a,b)=> (a>b)? a:b;`
