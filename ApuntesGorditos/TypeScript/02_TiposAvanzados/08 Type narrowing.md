## Contexto

cuando se pueden tener mas de un tipo de dato dentro de la misma variable.

```typescript title=""
function lala(x: string | number){
	//Type narrowing
	if(typeof x == 'number'){
		x. // Dara metodos de number
	}
	x. // dara metodos de string
}
```

Simplemente que al filtrar por *if* el *typeof* de la variable TS lo trata como ese tipo. 