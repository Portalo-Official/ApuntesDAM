
## Exportar Módulo
La manera en la que exporta Node.js 
```js title='exportar modulo'
const crearArchivo =  (numero ) => {
  // La logica que sea, nos da igual
};

// Exportar en Node.js
module.exports = {
  crearArchivo: crearArchivo,
};
```

## Importar módulo

En Node.js la manera de importar modulo es :

`{js}const variable = required('./ruta')`

_Importante_: en la ruta poner siempre el _./_, si no da problemas.

Ejemplo:
`{js}const {crearArchivo} = require('./helpers/multiplicar')`

