La misión de never es indicar que se va a lanzar un error.

Si vemos que una funcion retorna never, significa que lanza un error gestionada por el programador.

```typescript title=Lanzar Error
function ErrorUsuario(): never{
    throw new Error('Error de usuario')
}
```

Si le quitamos el tipado y dejamos que tome la funcion su retorno de manera implícita, este indicara que es tipo *void*.

```typescript title=Lanzar Error
function ErrorUsuario(){
    throw new Error('Error de usuario')
}
```

Una situación que se quiere evitar, pues void puede hacer muchas cosas aunque no retorne nada, pero ***never*** tiene como objetivo indicar que solamente lanzara un error y nada mas.