
Para recibir información desde una terminal

```js title='script normal'
function genTablaMultiplicar(base) {
      for (let i = 1; i <= 10; i++) {
        let multiplicacion = i * base;
        console.log(`${base} x ${i} = ${multiplicacion}\n`);
      }
    }
// Invocar funcion
let numero = 5;
genTablaMultiplicar(numero)
```

El script anterior, imprime por consola la tabla de multiplicar de la variable _numero_.

Si queremos mandar la variable numero por consola. tenemos que usar _argv_.
### argv

argv -> se refiere a los argumentos de línea de comandos que se pasan a un script Node.js. Estos argumentos son accesibles a través de la variable _process.argv_.

`{bash}node app.js arg1 arg2 arg3`

siendo arg los argumentos, Node recibe esto como un _array_, siendo el primer elemento \[0] la palabra node y el segundo elemento \[1] el nombre del archivo.

- process.argv\[0] = ruta al ejecutable de Node.js  'usr/local/bin/node'.

- process.argv\[1] = ruta del script.

- process.argv\[2]= primer argumento.

usando [[07 Pro Tips Funciones#Desestructuración|desestructuración]]:

```js title='Desestructurando process.argv'
function genTablaMultiplicar(base) {
      for (let i = 1; i <= 10; i++) {
        let multiplicacion = i * base;
        console.log(`${base} x ${i} = ${multiplicacion}\n`);
      }
    }
// Invocar funcion
const [ , ,numero ] = process.argv;
genTablaMultiplicar(numero)
```

los 2 primeros estan vacíos porque no queremos guardar esa información.

Si no mandaran argumentos la variable _numero_ ahora estaría vacía.

Esto se arregla poniendo un valor por defecto:
`{js}const [ , ,numero = 'base=5' ] = process.argv;`

Como lo que recibe la funcion es un tipo _number_, podemos convertir este dato

```js title='Convirtiendo dato'
function genTablaMultiplicar(base) {
      for (let i = 1; i <= 10; i++) {
        let multiplicacion = i * base;
        console.log(`${base} x ${i} = ${multiplicacion}\n`);
      }
    }
// Invocar funcion
const [ , ,arg3 ] = process.argv;
// segundo valor será el numero
const [ , numero] = arg3.split('=');
genTablaMultiplicar(numero)
```

A nivel educativo esta bien, pero esto tiene muchas limitaciones para que nuestro código no funcione.

Hay un paquete para gestionar este tema muy bien desarrollado y muy usado llamado [[Yargs]].