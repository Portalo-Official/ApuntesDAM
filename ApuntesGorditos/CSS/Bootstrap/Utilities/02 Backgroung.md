# Background

En el se define el color.

Ver mas: [Background](https://getbootstrap.com/docs/5.3/utilities/background/)

## Estructura

bg-\* --> con bg-{nombreColor}
bg-\*-subtle --> tono mas oscuro bg-{nombreColor}-subtle

#### Gradientes

Añadir después establecer el color, separado por espacio:

						`bg-gradient`

#### Opacity

Hay que tocar desde la etiqueta html a style e insertar:


```html title='Ejemplos'
<div class="bg-success p-2 text-white">This is default success </div>
<div class="bg-success p-2 text-white bg-opacity-75">This is 75% opacity success background</div>
<div class="bg-success p-2 text-dark bg-opacity-50">This is 50% </div>
<div class="bg-success p-2 text-dark bg-opacity-25">This is 25% </div>
<div class="bg-success p-2 text-dark bg-opacity-10">This is 10%</div>
```


Ver mas: [Opacidad Bootstrap](https://getbootstrap.com/docs/5.3/utilities/background/#opacity)


