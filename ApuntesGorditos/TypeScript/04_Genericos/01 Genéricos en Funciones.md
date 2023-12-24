
## Genéricos en Funciones

`{typescript}function log<T>`  para generalizar el tipo de dato con el que vaya a trabajar:

```typescript title="Genérico en funciones"
function log<T>(a: string, b: T){
    console.log(a, b);
}
log<number>('dato', 42)
log<boolean>('datito',true)
```

Se pueden inferir los tipos

```typescript title="INfieriendo tipos"
function log<T, V>(a: T, b: V){
    console.log(a, b);
}
log(1, 2)
log('Saludos', true)
```


