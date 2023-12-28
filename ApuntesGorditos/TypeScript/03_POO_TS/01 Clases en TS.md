# Clases

Sigue la dinámica de [[01 Clases en JS|clases en javascript]].

## Clases con typescript

Como practica vamos a crear una clase Personaje, orientado a juegos, este tendrá un id, un nombre, un nivel y vida.

```typescript title="Clase Personaje"
class Personaje {
    id: number
    name: string
    nivel: number
    hp: number

    constructor(id: number, name: string, nivel: number, hp: number){
        this.id = id
        this.name=name
        this.nivel=nivel
        this.hp=hp
    }
}
```

### Instanciar objeto

`{typescript}var personaje: Personaje = new Personaje(1, 'Goku', 2, 100)`

El autocompletado, no da sus propiedades con cajitas azules.

Cajita azul -> Propiedades
Cajita Morada -> Métodos

![[propiedades-autocompletado.png|500]]

### Métodos

Queremos que el personaje pueda bajar nivel y aumentar vida.

para crear un método, no se pone la palabra reservada de _function_.

```typescript
class Personaje {
    id: number
    name: string
    nivel: number
    hp: number

    constructor(id: number, name: string, nivel: number, hp: number){
        this.id = id
        this.name=name
        this.nivel=nivel
        this.hp=hp
    }

    subirNivel(): number
    {
       return ++this.nivel
    }

    bajarNivel(): number
    {
       return --this.nivel
    }

    restarHp(cantidad: number): number
    {
        this.hp= this.hp - cantidad;
        return this.hp
    }
}
```

