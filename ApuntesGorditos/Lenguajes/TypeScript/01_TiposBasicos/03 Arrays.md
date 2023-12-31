Como ya se dijo en [[01 Tipos TypeScript|tipos de TS]] estos ya son tipos de datos Objects.

## Arrays

Maneras de tipar un arreglo:

```typescript hl:5 title=arrays
// menra explicita
var animales: string[] = ['changuito','tortuga','gatete']

// manera tipo inferido
var numeritos2 = [] // Sera un any[]

console.log(typeof(numeritos2));
```

Si declaramos de manera de Tipo inferido, el arreglo será un _any[ ]_ , a priori no salta error, pero si le añadimos la línea 7, saltara el siguiente error:


![[arreglo-any-implicito.png|650]]

Si nos fijamos en el siguiente bloque en la _línea 10_ se ve la manera en la que TS quiere que declares un tipo Array.

```typescript title="Forma de declarar arrays"
// manera explicita
var animales: string[] = ['changuito','tortuga','gatete']

//Descomentar linea 7 para ver error
// manera tipo inferido
var numeritos2 = [] // Sera un any[]
//console.log(typeof(numeritos2));

// FORMA DE TIPAR ARRAYS
var numeritos: Array<number>
```

la variable tipo any[ ] no tenga ningún problema a priori, pero será tedioso trabajar con ella, pues el programador tendrá que gestionar que tipo es para saber que métodos usar en el.

### TypeScript Autocompletado

animales es un _string[]_, TS detecta que sus elementos son string y te ayuda con los métodos de la clase string: 

![[autocompletar-array.png]]

