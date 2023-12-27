
## Condición

While tratara `undefined` y `null` como false.

```javascript title='Undefined como false'
let x; // undefine
let contadorWhile = 0;
// al ser undefine, lo toma como false, nunca entra
while(x && contadorWhile<5){
    console.log(contadorWhile);
    contadorWhile ++;
}
```
