
## Pro Tips 

### Retornar objetos

Cuando las propiedades del objeto a retornar se llaman igual que variables con sus propios valores se puede omitir poniendo solo la variable, js intuye que la propiedad se llamara así.

```javascript title="Retornar Persona"
// Forma antigua
function crearPersona(nombre, apellido){
    return{
        nombre: nombre,
        apellido: apellido
    }
}
//Omitiendo
function crearPersona(nombre, apellido){
    return{
        nombre,
        apellido
    }
}
```

Con ___arrow function___ sería:

`{javascript}const crearPersona= (nombre, apellido)=> ({nombre,apellido})`

### Parámetro Rest en Arrow Function

Las arrow function no tienen [[05 Funciones#Arguments|arguments]] como las funciones tradicionales. Si necesitáramos de estas, tenemos que implementar el [parámetro rest](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Functions/rest_parameters)  

```javascript title="Parametro Rest"
const imprimeArgumentos2 = (...args) => {
    return args;
}
```

___importante___: después del parámetro rest, no puede ningún otro parámetro.

Si viene otro parámetro antes del parámetro rest, tendrá su propio valor independiente.

```javascript title="Valor Propio"
const imprimeArgumentos2 = (edad,...args) => {
    console.log({edad, args});
}
// edad tendra el valor de 10.
// args tendra {1: 'Noche',2: 23, 3}
imprimeArgumentos2(10,'Noche',23,true)
```


### Desestructuración

Cuando una funcion retorna muchos parámetros y necesitamos recogerlos sueltos, uno a uno en variables individuales:

```javascript title="Desestructuracion"
const imprimeArgumentos2 = (...args) => {
    return args;
}
const [casado, edad, nombre] = imprimeArgumentos2(false, 23, 'Ana')
console.log(casado);// flase
console.log(edad); // 23
console.log(nombre); // Ana
```

