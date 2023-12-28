Este proyecto esta en [github](https://github.com/santiagoieshna/jsPracticando), en JavascriptPracticando/04_DOM-BlackJack.

## Laboratorio

Vamos a elaborar el juego de Blackjack para abordar la parte de DOM ( Document Object Model)

### Estructura y estilo

Para tener un soporte del estilo usaremos Bootstrap, de esta forma nos ahorramos generar CSS, cuando el cometido es manipular javascript-html.

Si te interesa poco ahora html y que partes tiene este proyecto, pasa pa'lante. El html entero esta en la ultima sección de esta hoja.

#### Desglosando html

Si no se añade el CSS es porque las clases son de Bootstrap

##### Cabecera

```html title='Cabecera'
<header class="bg-dark bg-gradient titulo">Blackjack</header>
```

```css title='.titulo'
.titulo{
  width: 100% !important;
  text-align: center;
  color: aliceblue;
  padding: .5rem;
  font-size: 1.4em;
  font-weight: 600;
}
```


##### Botones

```html title='Botones'
<div class="row mt-3">
      <div class="col text-center">
          <button class="btn btn-light">Nuevo Juego</button>
          <button class="btn btn-success">Pedir Carta</button>
          <button class="btn btn-outline-danger">Detener</button>
      </div>
</div>
```

##### Cartas de jugador y crupier

```html title='Cartas jugador y crupier'
 <div class="row container">
            <div class="col">
                <h1>Crupier -<small>0</small></h1>
                <div id="crupier-cartas">
                    <img class="carta" src="assets/img/cartas/10C.png" alt="carta01" />
                    <img class="carta" src="assets/img/cartas/10C.png" alt="carta01" />
                    <img class="carta" src="assets/img/cartas/10C.png" alt="carta01" />
                    <img class="carta" src="assets/img/cartas/10C.png" alt="carta01" />
                </div>
            </div>
        </div>
        <div class="row container">
            <div class="col">
                <h1 >Jugador 1 -<small>0</small></h1>
                <div id="jugador-cartas">
                    <img class="carta" src="assets/img/cartas/10C.png" alt="carta01" />
                    <img class="carta" src="assets/img/cartas/10C.png" alt="carta01" />
                    <img class="carta" src="assets/img/cartas/10C.png" alt="carta01" />
                    <img class="carta" src="assets/img/cartas/10C.png" alt="carta01" />
                </div>
            </div>
        </div>
```

```css title='Altura de cartas y contenedores'
.carta{
  width: 10rem;
  position: relative;
  left: 5rem;
  margin-left: -4.5rem;
}

#crupier-cartas, #jugador-cartas {
  height: 18rem;
}
```


### Html entero
```html title='Index.html'
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="assets/css/normalize.css" />
    <link rel="stylesheet" href="assets/css/styles.css" />
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN"
crossorigin="anonymous"/>
    <title>Blackjack</title>
  </head>
  <body>
    <header class="bg-dark bg-gradient titulo">Blackjack</header>
    <section class="justify-content-center">
        <div class="row mt-3 fix-ancho">
        <!-- Para centrar en el medio-->
            <div id="botonera" class="col text-center ">
            <button id="new-game" class="btn btn-light">Nuevo Juego</button>
            <button id="give-card" class="btn btn-success">Pedir Carta</button>
            <button id="stop" class="btn btn-outline-danger">Detener</button>
            </div>
        </div>
        <div class="row container">
            <div class="col">
                <h1>Crupier - <small>0</small></h1>
                <div id="crupier-cartas">
                    <img class="carta" src="assets/img/cartas/grey_back.png" alt="carta01" />
                </div>
            </div>
        </div>
        <div class="row container">
            <div class="col">
                <h1 id="nombre-jugador">Jugador 1 - <small>0</small></h1>
                <div id="jugador-cartas">
                    <!-- <img class="carta" src="assets/img/cartas/10C.png" alt="carta01" /> -->
                </div>
            </div>
        </div>
    </section>
    <script     src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL"
      crossorigin="anonymous"></script>
    <script src="assets/js/underscore-min.js"></script>
    <script src="assets/js/juego.js"></script>
  </body>
</html>
```
