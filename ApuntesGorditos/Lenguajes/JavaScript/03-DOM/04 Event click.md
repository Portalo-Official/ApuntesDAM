# Event click

Los elementos de DOM, pueden tener eventos, para ello se le añade con:
```javascript title='.addEventListener()'
let btnGiveCard = document.querySelector('#give-card');
btnGiveCard.addEventListener('tipo_evento', funcionCallback)
```

También se pueden quitar eventos: `.removeEventListener()`

```javascript title='Ejemplo Boton dar carta'
btnGiveCard.addEventListener('click', () =>{
    const carta = pedirCarta(deck);
    puntosJugador += getValorCarta(carta);
    puntosHTML[1].innerText= puntosJugador;
    addCardHTML(carta, cartasJugador);
    comprobarPuntosJugador()
});
```
### Tipos de eventos

Fuente: [Tipos de eventos](https://desarrolloweb.com/articulos/1236.php)

- `{javascript}'click'`
- `{javascript}'focus'`
- `{javascript}'dbclick'`
- `{javascript}'mouseover'`
- `{javascript}'mouseout'`
- `{javascript}'mousemove'`
- `{javascript}'mouseup'`
- `{javascript}'scroll'`