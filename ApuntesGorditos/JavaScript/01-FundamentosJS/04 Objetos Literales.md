## Introducción a Objetos literales

```javascript title="Objeto"
const objeto = {
    id: 23,
    name: 'Pez espada',
}
```

Cuando tenemos `{javascript}{}` en js, es un objeto. Es parecido a los Diccionarios, pues tienen una clave-valor ( key-value).

Los elementos de un objeto pueden ser propiedades y métodos (funciones).

para acceder sus propiedades ahi dos formas:

```javascript title=Propiedades
console.log(objeto.id) // imprime -> 23
console.log(objeto['name']); // imprime -> Pez espada
objeto.id = 'A-22' // Cambio valor 23 -> A-22

let id = 'id'; // Referencia por string
console.log(objeto[id]) // imprime A-22
```


## Object

La clase object tiene muchos [métodos](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Object), 

Javascript no tiene "sub-clases", tiene mecanismos para combatir estas limitaciones, pero no profundizamos, pues para eso estamos estudiando Typescript.

### Métodos 

`{javascript}Object.entries(persona)` 
--> Devuelve par key-value en arrays `[nombre, 'ana']`

`{javascript}Object.getOwnPropertyNames(persona)`
--> Retorna un array de los nombres de las propiedades del objeto.

`{javascript}Object.getOwnPropertyValues(persona)`
--> Retorna un array de los valores de las propiedades del objeto.

`{javascript}Object.create(persona)`
--> Crea un objeto nuevo, utilizando un objeto existente como el prototipo del nuevo objeto creado, [ver mas](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Object/create).

`{javascript}Object.freeze(persona)`
--> "Congela" un instante del objeto con las referencias de su estado. No cambian los valores referenciados.

