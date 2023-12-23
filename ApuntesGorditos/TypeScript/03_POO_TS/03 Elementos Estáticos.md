
## Propiedades y Métodos Estáticos 

Crear una variable estática `{typescript}equipo: number` que cuenten cuantos personajes se han creado.

```typescript title=Static
class Personaje04 {
    profesion?: string
	// Propiedad estatica
    private static equipo: number = 0

    constructor(
        public readonly id: number,
        public name: string,
        private _nivel: number,
        private _hp: number

    ) {
        Personaje04.incrementarEquipo()
    }

    static incrementarEquipo(): void
    {
        Personaje04.equipo++
    }
    static muestraCantidad(): number
    {
       return Personaje04.equipo
    }
}
```





