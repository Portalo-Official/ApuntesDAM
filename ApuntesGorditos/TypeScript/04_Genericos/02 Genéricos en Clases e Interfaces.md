## Genéricos en Clases

```typescript title="Genericos en Clases"
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

var programador1 = new Programador<Ordenador>(acer)
var Programador2 = new Programador<string>('msi')
```


## Genéricos en interfaces

Ejemplo de como usamos una interfaz con dos tipos de datos como salida en 2 funciones.

```typescript title="Genericos en interface"
interface KeyValue<T,V>{
    key: T,
    value: V
}

interface Product{
    id: string
} 

function fetchProduct(): KeyValue<string, Product>
{
    return{
        key: 'idProucto',
        value: {id: 'id de product'}
    }
}

function fetchStock(): KeyValue<string, number>
{
    return{
        key: 'idProucto',
        value: 50
    }
}
```