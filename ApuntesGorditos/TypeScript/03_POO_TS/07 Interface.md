## Interfaces

2 maneras

### Interface

las interfaces pueden tener propiedades y métodos


```typescript title="interface"
interface Animal{
  name: string
  caminar(): void
  onomatopeya():string
}

class Caballo implements Animal{
    constructor(
        public name:string
    ){ }
    caminar(): void {
      console.log("Troto");
    }
    onomatopeya(): string {
      return 'Hii'
    }
}
```

Existe la convención de usar `{typescript}interface` en vez de la siguiente maneta con *type*.

### Type

Usar type cuando -> Si no se indica clase y se crea algo suelto. (yo que se, no me rayes).


```typescript title="Type"
type Canino = {
    name: string
    caminar(): void
    onomatopeya():string
} 

class Perro implements Canino{
    constructor(
       public name:string
    ){ }
    caminar(): void {
        console.log("Camino");
    }
    onomatopeya(): string {
        return 'Hii'
    }
}
```




