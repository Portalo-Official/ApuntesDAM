
## Consola


### Tipos de mensajes

No solo existe `{javascript}console.log('Hola Mundo')`, hay también para lanzar advertencia y error.

`{javascript}console.error(mensaje)` -> Lanza mensaje de error en consola de navegador

`{javascript}console.war(mensaje)` -> Lanza mensaje de advertencia en consola de navegador

`{javascript}console.table([array])` -> Tabla por consola ( puede ser array `[]` u objeto `{}`)

```javascript 
let a=10,
    b=20,
    c=30
    d=40
    x= a + b;
console.info(a);
console.warn('a vale '+a);
console.error('Probando');
```

Si enganchamos un script en un html y lo vemos en un navegador:

![[tiposmensaje-navegador.png|600]]

## Modos de impresión

Varias maneras para visualizar los datos

```javascript title="Modos de imprimir"
let a= 10,
	b= 20,
	c=30,
	d=40,
	x= a+b;
	
console.log(a); // dato simple
console.log({b}) // nombre de la varible -> {b : 20}
console.log('c', c) // 2 variables -> c, 30
console.table({a, b, c, d, x}); // Tabla de object
console.table([a, b, c, d, x]); // Tabla de array

```

Ver el nombre de variable y valor:
- `{javascript}console.log({b})` -> lo convertimos a objeto con `{}`  

Ver datos en un tabla:
- `{javascript}console.table({a, b, c, d, x});` -> para objetos
- `{javascript}console.table([a, b, c, d, x]);` -> para array

![[tablas-por-consola.png|500]]

### Impresión con CSS

`{javascript}console.log('%c Mis variables', 'color:blue; font-weight: bold;')`

