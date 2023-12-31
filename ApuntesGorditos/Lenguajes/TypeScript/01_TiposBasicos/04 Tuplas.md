JavaScript no tiene tuplas, es un tipo de dato que implemento TypeScript.

## ¿Qué es una tupla?

Una tupla es un _Set de datos ordenados_, tienen un conjunto de valores, ordenados.

`{typescript}let tupla =[ 1, "Codorniz"]`

### Inmutabilidad 

Una tupla, es inmutable en su elementos, tanto en:
- tipo
- longitud
- orden

Pero si *es mutable* en el valor.

***Nota***: En python las tuplas son inmutables. En TS "no", se puede cambiar el valor, pero no el numero de elementos y tipo de dato.
### Declaración

```typescript title="Tupla implicita"
var tupla = [1, "Uno"]
tupla = [2, "Uno"]
tupla = [3, 1]
// Deberia dar error, pero no declaro explicito el tipo tupla
tupla = [4,2,"cinco"]
```


#### Declaración explicita

La manera de declarar una tupla de manera explicita y bien es:
`{typescript}var tuplita: [number, string]`

```typescript title="Tupla explicita"
var tuplita: [number, string] = [1,"Uno"]
tuplita = [2, "sonrisa"] // BIEN

tuplita = ["Uno",1] // No hay orden en sus elementos - MAL

tuplita = [2 ,2] // No son del mismo tipo - MAL

tuplita = [1, "cachorro", 2] // Tiene mas elementos - MAL
```


![[errores-tupla.png]]

También pueden tener dentro arreglos
`{typescript}var tuplita: [number, string[]]`

### Observaciones

Tratar de tener coherencia a la hora de crear una tupla, si esta tiene muchos datos, seguramente se necesite otro tipo de dato para representar tal caso.

### Error del compilador con las Tuplas

En TS hay un error no contemplado.

```typescript title="Metodo push"
var tupla2: [number, boolean]
tupla2 = [2 , true]
tupla2.push(8) // No arroja error
```

El método push añadiría un  elemento a la tupla, cosa que no se puede. 

El compilador y el entorno de TS no arroja este error, cosa a tener en cuenta cuando se trabaje con tuplas.

Como resultado, el sistema inserta el elemento y se queda tan pancho.

![[error-tupla-push.png|450]]