
## Orden y lugar

#### Orden

Si en el html añadimos el script de js en el `{html}<head>`  en vez de al final del `{html}<body>` este nos cargara antes que los elementos gráficos.

Ponerlo en el `{html}<head>` no suele ser recomendable porque el script se ejecutara antes _bloqueando el resto de código html_ , ocasionando una mala experiencia al usuario.

#### Lugar

La mayor parte de las veces, los archivos de js deberán ir en una carpeta con una convención.

- Carpeta js: indicando que dentro están los .js del proyecto

- assets: directorio donde van destinados los archivos que no necesitan un procesamiento en tiempo de ejecución y que pueden ser servidos directamente al cliente.

```lua
mi_proyecto_web/
|-- index.html
|-- assets/
|   |-- css/
|   |   |-- styles.css
|   |-- js/
|   |   |-- main.js
|   |-- images/
|       |-- logo.png
|-- other/
    |-- archivo_otro.html
```




