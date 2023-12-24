## Clases y métodos abstractos

Cuando vamos a tratar una clase como un concepto para compartir funcionalidades que hereden otras.

`{typescript}abstract`

```typescript title="abstract"
// Clase Abstracta
abstract class DatosBasicos02{

    constructor
    (
     public name: string,
     public desc: string,
     public created_at: Date,
     public created_by: number,
    ){}

    get fullYear(): number
    {
        return this.created_at.getFullYear()
    }

    // NUEVO METODO
    get fullDesc(){
        return this.name+' '+ this.desc
    }
}
```

