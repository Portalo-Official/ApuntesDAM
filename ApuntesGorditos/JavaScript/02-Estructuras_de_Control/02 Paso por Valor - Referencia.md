## Paso por valor

Cuando igualamos alguna variable con [[01 Tipos primitivos#Que son los Primitivos|Tipo primitivo]], captura en memoria el valor tal cual.

```javascript title='Paso por valor'
let a=10,
    b=a;
    a=30;
console.log({a, b}); // { a: 30, b: 10 }
```

## Paso por referencia

Cuando igualamos alguna variable con un [[04 Objetos Literales|Objeto]], captura en memoria el valor tal cual. Coge la referencia de memoria, si cambia el valor de la propiedad del objeto también lo tendrá.

```javascript title='Paso por referencia'
let juan = {nombre: 'juan', edad: 24}
let ana = juan
juan.edad= 37
console.log('juan',juan);
console.log('ana',ana);
```

![[paso-por-referencia.png]]

### Romper referencia

_Operador spread_: parecido al parámetro rest, pero distinto, con el rompemos la referencia del objeto.

La principal diferencia es que los parámetros rest se usan en el parámetro de la función.

```javascript title='Romper Referencia'
let tom = {nombre: 'Tom', edad: 24}
let jerry = {...tom}
jerry.nombre= 'Jerry'

console.log('Tom',tom);
console.log('Jerry',jerry);
```

#### Operador Spread en arrays

Con array se puede hacer de varias formas:

```javascript title="Referencia rota por spread"
let frutas = ['Manzana', 'Pera', 'Piña']
const otrasFrutas= [...frutas];
```

```javascript title="Referencia rota por .slice()"
let frutas = ['Manzana', 'Pera', 'Piña']
const otrasFrutas= frutas.slice();
```

_.slice()_ es un método que ya vimos en la arreglos que retorna un nuevo array.

Antes Spread es mas rápido que .slice(), hoy en día son muy parejo, podemos verlo poniendo temporizadores:

```javascript title="Referencia rota por .slice()"
let frutas = ['Manzana', 'Pera', 'Piña']

console.time('spread')
const otrasFrutas= [...frutas];
console.timeEnd('spread') 

console.time('slice')
const otrasFrutas2= frutas.slice();
console.timeEnd('slice')
  
otrasFrutas.push('Mango')
otrasFrutas2.push('Coco')
console.table({frutas,otrasFrutas,otrasFrutas2});
```
