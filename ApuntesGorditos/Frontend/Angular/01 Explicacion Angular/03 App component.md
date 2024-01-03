
Un componente va a formar por varias partes que ya vimos en el [[02 Explicación de cada archivo#app|directorio app]], y estos son los archivos app.component.\*.

1. _app.component.css_ : Archivo para CSS

2. _app.component.html_: Archivo para HTML

3. _app.component.spec.ts_: Archivos de pruebas (.spec o .test para testing)

4. _app.component.ts_ ___A___: Archivo ts, el mas importante. Explica como funciona el componente, que dependencias tiene etc. Los demás son digamos que formas para que no todo estuviera dentro de este (Mejor legibilidad).


En el archivo .ts viene definido cada uno de los archivos:

```ts title='app.component.ts'
import { Component } from '@angular/core';
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrl: './app.component.css'
})
export class AppComponent {
  title = 'bases-angular';
}
```

_templateUrl_: es la sección para el html.
_styleUrl_: es la sección para el CSS.

_selector_: 'app-root', -->  Si nos vamos al index.html del proyecto veremos que: 

```html hl:11 title='index.html'
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>BasesAngular</title>
  <base href="/">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="icon" type="image/x-icon" href="favicon.ico">
</head>
<body>
  <app-root></app-root>
</body>
</html>
```

La línea 11 tiene la etiqueta app-root, ahí es donde se renderiza el componente o modulo de angular.

## app.component.html

En este archivos podemos escribir código typescript, para ello vamos a modificar un poco el archivo .ts:

```ts title='app.component.ts'
import { Component } from '@angular/core';
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrl: './app.component.css'
})
export class AppComponent {
  title = 'bases-angular';
  public variable:string = 'Cervantes era una pájaro'
}
```

Ahora vamos a  borrar el html y le ponemos solo un `{html}<h1>` y un `{html}<p>`

```html title='app.component.html'
<h1> {{variable}} </h1>
<hr>
<p>
  Bienvenidos a mi aplicación
</p>
```

Y si [[Paquete @angular_cli#Levantar servidor|levantamos]] el servidor, veremos los cambios:

![[ts-en-html.png]]

