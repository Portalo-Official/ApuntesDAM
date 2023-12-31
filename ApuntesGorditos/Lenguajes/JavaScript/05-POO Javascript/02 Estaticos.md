
# Estáticos

Las propiedades, gets y métodos estáticos, podemos acceder a ellos sin necesidad de instanciar la propia clase.

`{javascript}static` es la [[02 Palabras reservadas|palabra reservada]] para usar propiedades y métodos estáticos. 

```javascript title='static'
class PersonaClase{
    static _conteo = 0;
    nombre         = '';
    codigo         = '';
    _frase         = '';
    comida         = '';

    constructor(nombre = 'noName', codigo = 'Sin codigo', frase='Sin frase'){
        this.nombre = nombre;
        this.codigo = codigo;
        this._frase  = frase;
        PersonaClase.incrementarConteo();
    }

    static incrementarConteo() {
        PersonaClase._conteo++;
    }
    
     static get Conteo(){
        return this._conteo;
    }
}
```


#### Problemas con javascript

Javascript , no tiene privacidad de propiedades ni de métodos.
Desde fuera de una clase puede crear tanto propiedades estaticas como propiedades de instancia
