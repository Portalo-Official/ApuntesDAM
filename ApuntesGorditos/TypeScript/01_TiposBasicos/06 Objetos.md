
## Declarar un objeto

`{typescript}const persona = {nombre: "Felix", edad: 22}`

Las propiedades son de sus tipos por *tipo inferido*

```typescript title="Objeto: Tipado Inferido"

const persona = {nombre: "Felix", edad: 22}

persona.nombre = true //Error Es string por tipo inferido
persona.edad = "VeintiDos" //Error es number por tipo inferido

```

También, puede hacerse un tipado explícitamente.

```typescript title="Objeto: Tipado Explicito"
const canino: {
	nombre: string,
	raza: string,
	edad: number,
	tienePropietario: boolean
}= {nombre:"Kira", raza: "Yorkie", edad: 7, tienePropietario: true}

```

Estos objetos, son instancias ya, la variable se llama canino después se define su estructura de tipos de datos.

No confundir esto con una instancia de una [[01 Clases en TS|clase]], esto se vera en adelante.

### Propiedades - funcionalidades

#### Propiedad Opcional

Algunas veces, un propiedad no tiene porque estar siempre presente a la hora de crear un objeto.

Esta estructura anterior, necesitara siempre todos los datos como le hemos indicado, si falta una, arroja error.

```typescript title="Error: falta una propiedad"
const persona:{
	nombre: string,
	edad: number
} = {nombre: "Felix"} // Arroja error, falta el campo edad
```

###### Opcional Implementación

Definir la propiedad como ***opcional***, nos dará la despreocupación de que esa variable tenga que estar siempre si o si.

Implementación -> _propiedad_***?*** : *Tipo_Dato*

```typescript title="Opcional"
const persona:{
	nombre: string,
	edad?: number
} = {nombre: "Felix"} // Todo Okey
```

#### Propiedad ReadOnly

Ocurre casos que no queremos que haya propiedades que sean cambiadas. Que solo queramos que sean de solo lectura (read only).

Esto se soluciona añadiendo ***readonly*** antes del nombre de la propiedad.

```typescript title="Solo Lectura"
const perrete: {
    readonly nombre: string,
    raza: string,
    edad: number,
    tienePropietario?: boolean
}= {nombre:"Lira", raza: "Labrador", edad: 5}
perrete.nombre = "Tobi" // Arroja error
```


## Definir un type object

La manera anterior, es una forma de definir para una instancia en ese momento.
¿Pero, y si queremos mas? porque debemos de querer agrupar varios perretes en un array. 

```typescript title="Type Object"
enum RazaAves {
    Canario="Canario",
    Agaporni="Agaporni",
    Paloma="Paloma",
    Avestruz="Avestruz"
}
// Type Object
type Pajaro= {
    readonly nombre: string,
    raza: RazaAves,
    edad?: number,
    esSalvaje: boolean
}
// variable tipo Pajaro
var p1: Pajaro = {
    nombre: "Piti",
    raza: RazaAves.Agaporni,
    esSalvaje: false
}
console.log(typeof(p1)); // imprime object
```

### Objeto dentro de objeto

```typescript title="Objecto into object"
type Direccion = {
    numero: number,
    calle: string,
    pais: string
}
type Persona = {
    readonly id: number,
    nombre: string,
    direccion: Direccion

}
var p2: Persona = {
    id: 4,
    nombre: "Chavero",
    direccion: {
        numero: 11,
        calle: "San Roque",
        pais: "Spain"
    }
}
```



