# Problemática

Se necesitaban Clases para no hace muchos [[04 Objetos Literales|objetos literales]].

```javascript title='Como se hacia antes'
const persona1 = {
	nombre:'Juan',
	id:24
}
const persona2 = { nombre:'Maria', id:21}
const persona2 = { nombre:'Ana', id:56}
```

Pasado el tiempo, para llegar algo parecido a una clase:

```javascript title='Usar function para Objetos'
function Persona(nombre ,edad=10){
    this.nombre= nombre;
    this.edad  = edad; 
}
let persona1 = new Persona(nombre = 'Pedro', edad = 25);
let persona2 = new Persona(nombre = 'Ana' ,  edad = 35);
```

Esto era un tema lioso, pues si un programador nuevo llegase t viese esa funcion, no tiene que saber que se usa el operador new para crear el objeto.
# Clases

Todas las Clases en javascript tienen por defecto el [[02 Patrón Módulo#Use Strict|modo estricto]], no hace falta poner `{javascript}'use strict'`.

```javascript title='Class Persona'
class PersonaClase{
	// Propiedades
    nombre;
    codigo;
    frase;
    
    constructor(codigo){
        this.codigo= codigo;
    }
}
const persona1 = new PersonaClase();
```

Como no hemos dado valor por defecto a las Propiedades, menos código, las demás son _undefined_:

![[propiedades-undefined.png]]


### Sintaxis limpia

Una sintaxis mas limpia de los anterior seria:

```javascript title='Sintaxis limpia'
class PersonaClase{
    nombre = '';
    codigo = '';
    frase  = '';
    constructor(nombre = 'noName', codigo = 'Sin codigo', frase='Sin frase'){
        this.nombre = nombre;
        this.codigo = codigo;
        this.frase  = frase;
    }
}
const persona1 = new PersonaClase();
const persona2 = new PersonaClase('Jaime', 'AB-5', 'Pienso, luego existo')
console.log({persona1});
console.log({persona2});
```

![[sintaxis-limpia-clase.png]]


### Métodos


