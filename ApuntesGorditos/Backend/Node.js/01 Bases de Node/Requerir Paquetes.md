
## Documentación

Documentación oficial Node.js: [Node Docs 20.1](https://nodejs.org/dist/latest-v20.x/docs/api/)

Aquí puedes ver todas las clases y funciones que tiene node.js


## Ejemplos

_fs.writeFile( file, data\[, options], callback)_: [fs.writeFile(...)](https://nodejs.org/dist/latest-v20.x/docs/api/fs.html#fswritefilefile-data-options-callback) 

```js title='Crear archivos'
const fs = require('fs');

const numero = 14;
let filename= `tabla-${numero}.txt`;
let contenido = gentablaMultiplicar(numero);  

fs.writeFileSync(filename, contenido , (err)=>{
    if (err){
        throw `Algo fallo con `
    }
    console.log(`Archivo  creado`);
})

function gentablaMultiplicar(base) {
    let salida= '';
    for (let i = 1; i <= 10; i++) {
        let multiplicacion= i * base;
        salida += `${base} x ${i} = ${multiplicacion}\n`;
    }
    return salida;
}
```
