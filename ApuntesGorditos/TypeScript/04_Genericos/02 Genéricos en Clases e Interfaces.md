## Genéricos en Clases

```typescript title="Genericos en Clases"
// Clase con un generico
class Programador<T>{
    private ordenador: T;
    constructor(t:T){
        this.ordenador = t
     }
}
type Ordenador={
    encender: () => void,
    apagar: ()=> void
} 

var acer: Ordenador = {
    encender: () => {console.log("Encendido");},
    apagar() {console.log('Apagado');},
}

//Asignando generico 
var programador1 = new Programador<Ordenador>(acer)
var Programador2 = new Programador<string>('msi')
```


## Genéricos en interfaces

Ejemplo de como usamos una interfaz con dos tipos de datos como salida en 2 funciones.

```typescript title="Genericos en interface"
// interfaz con 2 genericos
interface KeyValue<T,V>{
    key: T,
    value: V
}

interface Product{
    id: string
} 

// funcion usando la interfaz <string, Producto>
function fetchProduct(): KeyValue<string, Product>
{
    return{
        key: 'idProucto',
        value: {id: 'id de product'}
    }
}

// funcion usando la interfaz <string, number>
function fetchStock(): KeyValue<string, number>
{
    return{
        key: 'idProucto',
        value: 50
    }
}
```