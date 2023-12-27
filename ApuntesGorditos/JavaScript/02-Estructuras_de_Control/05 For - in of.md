
# For

For tradicional:

```javascript title='Calcular Numeros Primos'
numerosPrimos =[]
// numeros primos hasta 150
for (let i = 1; i < 150; i++) {
    let divisores=0;
    for (let j = 1; j <= i; j++) {
       if(i%j==0){
        divisores++;
       }
    }
    if(divisores==2){
        numerosPrimos.push(i);
    }
}
```

### For in 

Recorre con índice la longitud de un array.

```javascript title='Recorrido con indice'
for( i in superHeros){
    console.log(superHeros[i]);
}
```

### For of

Recorre el array cogiendo los elementos uno a uno.

```javascript title='Recorrdido por elementos'
for (numeros of numerosPrimos){
    console.log(numeros);
}
```
