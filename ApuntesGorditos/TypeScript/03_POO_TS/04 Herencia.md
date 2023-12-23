## Herencia

```typescript title="Clase Padre"
class DatosBasicos{

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

    get fullDesc(){
        return this.name+' '+ this.desc
    }
}
```

```typescript title="Clase Producto"
class Producto extends DatosBasicos{

    constructor
    (
        public stock: number,
        public sku: number,
  
        name: string,
        desc: string,
        created_at: Date,
        created_by: number,
    ) {
        super(name, desc, created_at, created_by)
    }
}
```

```typescript title="Clase Categoria"
class Categoria extends DatosBasicos{
    public productos: Array<Producto>

    constructor
    (
        name: string,
        desc: string,
        created_at: Date,
        created_by: number,
    ) {
        super(name, desc, created_at, created_by)
        this.productos= []
    }  

    agregarProducto( producto: Producto)
    {
        this.productos.push(producto)
    }
}
```



### Override






#### Configuracion

Si no ponemos override, no nos arroja error, pero el programa puede actuar de manera extraña.

Para qeu siempre se exija poner la palabra Override, habilitar [[01_Configuracion]]
