
## Paquetes

Para la instalación de paquetes, en la página de [Bootstrap](https://getbootstrap.com) hay 2 alternativas.

- Instalar package manager:
- Incluir por CDN en el html

### Instalar paquetes

Fuente: [Package managers](https://getbootstrap.com/docs/5.3/getting-started/download/#package-managers)

Dependerá de la tecnología que uses para instalar el paquete: [node](https://getbootstrap.com/docs/5.3/getting-started/download/#npm), [.NET](https://getbootstrap.com/docs/5.3/getting-started/download/#nuget) etc..

### CDN

CDN -> Content Delivery Network

Fuente: [CDN](https://getbootstrap.com/docs/5.3/getting-started/introduction/#quick-start) ,  [CDN(traducido)](https://esdocu.net/bootstrap/5.3/getting-started/introduction/)

hay que insertar en el html:

```html title='Link'
 <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" crossorigin="anonymous">
```

```html title='Script'
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL" crossorigin="anonymous"></script>
```

Copiar y ponerlas en sus respectivos lugares:
```html hl:6,10 title='Etiquetas para Bootstrap'
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Bootstrap demo</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" crossorigin="anonymous">
  </head>
  <body>
    <h1>Hello, world!</h1>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL" crossorigin="anonymous"></script>
  </body>
</html>
```

También puedes incluir [Popper](https://popper.js.org/) y nuestro JS por separado. Si no planeas usar menús desplegables, ventanas emergentes popovers o tooltips, ahorra algunos kilobytes al no incluir Popper.

```html title='Script Poppers'
<script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.11.8/dist/umd/popper.min.js" integrity="sha384-I7E8VVD/ismYTF4hNIPjVp/Zjvgyol6VFvRkX/vR+Vc4jQkC+hVqc2pM8ODewa9r" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.min.js" integrity="sha384-BBtl+eGJRgqQAUMxJ7pMwbEyER4l1g+O15P+16Ep7Q9Q+zqX6gSbd85u4mG4QzX+" crossorigin="anonymous"></script>
```
