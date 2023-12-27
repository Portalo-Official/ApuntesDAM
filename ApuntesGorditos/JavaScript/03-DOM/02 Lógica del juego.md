
# Lógica

A continuación vamos a mostrar la lógica para elaborar el Blackjack.

Para ello nos ayudaremos de una librería de tercero: [[01 UNDERSCORE.JS|UNDERSCORE.JS]]
Underscore es una librería muy popular para js.
## Crear Baraja de cartas

Las cartas las tenemos `assets/img/cartas/`, 54 imágenes correspondiente a las cartas.

Cada carta tiene como nombre, su numero mas la sigla de su palo:
2 de corazones es -> 2H.jpg

Para crear la baraja hemos usado el siguiente código en js:

```javascript title='CrearDeck'
let deck         = [];
const tipos      = ['C', 'D', 'H', 'S'];
const especiales = ['J', 'Q', 'K', 'A'] 
const crearDeck = () => {
    // Cartas numericas
    for (let i = 1; i < 10; i++) {
        for( let tipo of tipos){
            deck.push(i+tipo)
        }
    }  
    // Cartas especiales
    for (let tipo of tipos) {
        for (let especial of especiales) {
            deck.push(especial+tipo)
        }
    }
}
crearDeck(); // creamos deck
// console.log({deck})
```

Una vez creada la baraja, tenemos que pensar que estas ordenada, siempre saldrán las mismas cartas.

Para barajar las cartas usaremos una funcion de la librería [UNDERSCORE.JS](https://underscorejs.org/#shuffle), llamado .shuffle()

Asique después de crear la baraja, instalamos underscore.js e insertamos: `{javascript}deck.shuffle()`

en el html pondremos `{html}<script src="assets/js/underscore-min.js"></script>` antes de este script.

```JAVASCRIPT title='shuffleDeck()'
/**
 * Funcion que desordena una array
 * @param {*} deck array[]
 * @returns retorna el parametro deck desordenado
 */
const shuffleDeck = (deck) => {
    return _.shuffle(deck)
}
```
## Pedir carta 


