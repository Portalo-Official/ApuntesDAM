
# Interpolación 

Fuente: [Angular docs](https://angular.io/guide/interpolation)
Fuente: [Interpolación en español](https://soka.gitlab.io/angular/conceptos/data-binding/interpolacion/interpolacion/)

La interpolación de cadenas en ***Angular*** es el mecanismo para sustituir una expresión por un valor de tipo _string_ en la plantilla (_template_).

Cuando ***Angular*** se encuentra una expresión entre _{{}}_ (la sintaxis "Mustache" de las dos llaves) en la plantilla lo evalúa y trata de *sustituir el contenido por el valor de la propiedad del componente con el mismo nombre.

*Este tipo de vinculación o __binding__ es unidireccional*, vincula el valor del elemento a la propiedad del componente.

`{html}<a href="{{ miHref }}">Enlace</a>`

_Ejemplo_

```html hl:3,5,9 title='hero.component.html'
<dl>
  <td>Nombre:</td>
  <dd class="fs-4 fw-semibold">{{ name }}</dd>
  <td>Edad:</td>
  <dd class="fs-4 fw-semibold">{{ age }}</dd>
  <td>Método:</td>
  <dd class="fs-4 fw-semibold">algún método</dd>
  <td>Capitalizado:</td>
  <dd class="fs-4 fw-semibold text-capitalize">{{ name }}</dd>
</dl>
<button class="btn btn-primary m-1">
    Cambiar nombre
</button>
<button class="btn btn-primary">
    Cambiar edad
</button>
```


# One Way Data Binding 

Blog español: [Binding](https://desarrolloweb.com/articulos/binding-angularjs-doble-binding.html)

Binding seria enlace en español, y este termino se refiere el enlace de datos. Es un enlace que tenemos con el "scope" de la clase con el HTML.

One Way Data Binding --> En este caso la información solamente fluye desde el scope hacia la parte visual, ósea, desde el modelo hacia la representación de la información en el HTML. Siempre con Mustache ___{{}}___.

# Two-way binding

En este segundo caso la información fluye desde el scope hacia la parte visual (igual que en "one-way binding") y también desde la parte visual hacia el scope. La implementas por medio de directivas.

Es una sintaxis combinada de corchetes y llaves `[{}]`,   

