## Propiedades

### Control de acceso

Las propiedades deben de ser privadas (algunas no, eso ya cada situación).
Se ha decidido que nivel y hp deben ser privadas

```typescript title=Private
class Personaje {
    id: number
    name: string
    private nivel: number
    private hp: number
    
    constructor(id: number, name: string, nivel: number, hp: number){
        this.id = id
        this.name=name
        this.nivel=nivel
        this.hp=hp
    }
}
```

### Parámetros Opcionales y ReadOnly

Se quiere introducir una profesión a nuestro personaje, pero cuando se crea el personaje no tiene profesión, ya la desarrolla mas tarde.

Cuando declaramos una propiedad, si no esta en el constructor, arroja un error.

Por lo tanto hay que hacer uso del operador [[06 Objetos#Opcional Implementación|Optional]].

Además se quiere que id sea [[06 Objetos#Propiedad ReadOnly|ReadOnly]].

```typescript title=Private
class Personaje {
    readonly id: number
    name: string
    private nivel: number
    private hp: number
    profesion?: string
    
    constructor(id: number, name: string, nivel: number, hp: number){
        this.id = id
        this.name=name
        this.nivel=nivel
        this.hp=hp
    }
}
```


### Propiedades por parámetros

Con el objetivo de hacer el código mas corto, TS permite que se haga la misma declaración de las Propiedades en el parámetro del constructor.

```typescript title=Private
class Personaje02 {
    profesion?: string // este no por opcional

    constructor(
        public readonly id: number,
        public name: string,
        private _nivel: number,
        private _hp: number
    ) { }
}
```

el guion bajo de \_hp, es una antigua convención entre programadores que indica una propiedad es privada y no puede ser manipulada fuera de la clase. 

### Getters y Setters

Métodos para poder ver o actualizar las Propiedades.

Se puede hace como en java


```typescript title="Getters Setters Muy de 2015"
class Personaje02 {
    profesion?: string // este no por opcional

    constructor(
        public readonly id: number,
        public name: string,
        private _nivel: number,
        private _hp: number
    ) { }

	getHp():number
	{
		return this._hp
	}
	setHp(hp: number)
	{
		this._hp=hp
	}
}
```

Otra manera de hacerlo

```typescript title="Getters Setters Modernito"
class Personaje02 {
    profesion?: string // este no por opcional

    constructor(
        public readonly id: number,
        public name: string,
        private _nivel: number,
        private _hp: number
    ) { }

	get hp(): number {
       return this._hp
   }
   set hp(value: number) {
       this._hp = value;
   }
}
```

Se llaman así:

- ***Get*** -> `{typescript}console.log(presonaje.hp)`

- ***Set*** -> `{typescript}presonaje.hp= 50`
