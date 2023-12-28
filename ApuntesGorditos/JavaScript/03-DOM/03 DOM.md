
# DOM

DOM ---> Document Object Model

Es un conjunto de elementos anidados para crear un documento html xml...

La idea del DOM es tener un acceso dinámico a través de programación a sus elementos y poder manipularlos.

Aprender mas: [DOM](https://lenguajejs.com/javascript/dom/que-es/#el-objeto-document)

## Como se accede al DOM

Cuando se crea un script –esté en un elemento `{html}<script>` o incluido en una página web por la instrucción de cargar un script– inmediatamente está disponible para usarlo con el API, accediendo así a los elementos [`document`](https://developer.mozilla.org/es/docs/Web/API/Document) o [`window`](https://developer.mozilla.org/es/docs/Web/API/Window),

### Document

Fuente:[document](https://developer.mozilla.org/es/docs/Web/API/Document)

Document es una interfaz que representa cualquier web cargada.

### Window

Fuente:[window](https://developer.mozilla.org/es/docs/Web/API/Window)

El objeto window representa la ventana que contiene el documento DOM. de ella sale las [[05 Alertas|Alertas]], entre otros

## Document

### Metodos

De los métodos podemos obtener:

- Elementos `Element`
- Lista de nodos `NodeList`

#### Obtener elemento

##### Por id , clase y nombre de etiqueta

|Method|Description|
|---|---|
|document.getElementById(_id_)|Encuentra un element por el id |
|document.getElementsByTagName(_name_)|Encuentra un elemento por el tag |
|document.getElementsByClassName(_name_)|Encuentra un elemento por la clase |

###### Ejemplo

```javascript title='Obtener Elemento'
// Por class
let cartas = document.getElementsByClassName('carta'); // Todos
// Por id
let jugador= document.getElementById('jugador-cartas');
let crupier= document.getElementById('crupier-cartas');
// Por tag
let botones= document.getElementsByTagName('button'); // Todos
```

#### Por selectores

```javascript
// id
let jSelector= document.querySelector('#jugador-cartas');
// class
let cartaSelector= document.querySelector('.carta');// la primera
// Retorna todas las cartas
let cartasSelector= document.querySelectorAll('.carta');
// Retorna todas las etiquetas <small>
let puntosHTML = document.querySelectorAll('small'); //tags <small>
```

#### Añadir y Borrar elementos

|Method|Description|
|---|---|
|document.createElement(_element_)|Crea un elemento HTML |
|document.removeChild(_element_)|Elimina un elemento HTML |
|document.appendChild(_element_)|Añade un elemento HTML |
|document.replaceChild(_new, old_)|Reemplaza un elemento HTML |
|document.write(_text_)|Write into the HTML output stream|
##### Ejemplo crear y añadir botón

```javascript title='Add Button'
// Obtener div de los botones
let divBotones = document.getElementById('botonera');
// Crea un boton en memoria
let botonNuevo= document.createElement('button');
// Añadir al div
divBotones.append(botonNuevo);
// Poner texto
botonNuevo.innerText= 'Borrar Partida'
// Añadirle clases
botonNuevo.classList.add('btn'); // Class de Bootstrap
botonNuevo.classList.add('btn-success');// Class de Bootstrap
```
#### Modificar un elemento

| Property | Description |
| ---- | ---- |
| _element_.innerHTML =  _new html | Cambia el HTML de un elemento |
| _element_.innerText = 'new text' | Cambia el texto de un elemento |
| _element_._attribute = new value_ | Cambia el valor del atributo |
| _element_.style._property = new style_ | Cambia el estilo del elemnto |
| element.classList | Retorna lista de las clases |

| Method | Description |
| ---- | ---- |
| _element_.setAttribute_(attribute, value)_ | Change the attribute value of an HTML element |
##### Propiedad classList

###### Metodos de classList

- .add('clase') ---> Añade una clase al elemento.
- .contains('clase') ---> true si esta presente, false si no.
- .remove('clase') ---> elimina la clase.

## Cheatsheet Métodos

Fuente:[profulsadangi](https://twitter.com/profulsadangi/status/1294169143218810884/photo/1)

![[dom-cheatsheet-resumen.png]]

Fuente:[Div_pradeep](https://twitter.com/Div_pradeep/status/1631559402380509186/photo/1) 

![[dom-cheatsheet01.png]]