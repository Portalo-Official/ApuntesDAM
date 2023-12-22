
## Contexto
algún valor obtenido por algún lado que nosotros sabemos 100% que tipo de datos va a ser. Pero el compilador puede tener dificultado en saber que tipo de datos puede ser.

### Ejemplo
imaginemos que tenemos:

`{typescript}const elemento: any = null`

`{typescript}const elemento` -> es una variable que vendrá de algún sitio (BBDD, o Elemento HTML) y sabemos que su tipo es numérico ( lo sabemos 100%, no hay fallas).

pero a la hora de operar con el, el compilador no nos entrega métodos del tipo number.

![[no-metodos.png|400]]

Para ello existe Type asertion 

`{typescript}const elem1 = elemento as number`

![[si-metodos.png]]

Podemos observar el sistema ya nos ofrece funciones del tipo number.

## Caso Real

Un caso real para entender mejor esta funcionalidad.

Nos encontramos ahora con una situación muy elemental de JavaScript, que es conectar a un elemento HTML.

`{typescript}let inputUser = document.getElementById('username')`

para obtener su valor existe el método _.value_, pero el Ts no detecta que *inputUser* tenga ese método.

![[value-sin-sugerencia.png]]

Para solucionarlo, como sabemos que si o si tendrá ese valor, le indicamos el tipo que debe ser *inputUser*. En este caso es *type HTMInputElement*.

```typescript title="Asertion"
let inputUser = document.getElementById('username') as HTMLInputElement

inputUser.value
```

![[value-con-sugerencia.png]]
