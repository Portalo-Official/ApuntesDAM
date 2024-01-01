# Ciclo de eventos

En resumen, el ciclo de eventos en Node.js se centra en la ejecución no bloqueante, donde las operaciones de E/S no bloqueantes permiten manejar múltiples conexiones de manera eficiente sin la necesidad de hilos adicionales. El Event Loop es la clave de este modelo, garantizando que las operaciones de E/S no bloqueantes se manejen de manera asíncrona mientras se mantiene la eficiencia y la capacidad de respuesta del sistema.

### Ejemplo 

El siguiente código, vamos a hacer 2 console.log y 3  setTimeout, que hacen su funcion una vez pasado su tiempo establecido.

En comentarios esta puesto lo que se piensa que debería pasar:

```js title='ciclo de eventos'
console.log('Inicio de programa'); // 1

setTimeout(() => {
    console.log('Primer Timeout'); // 5
}, 3000); // se ejecuta a los 3 segundos

setTimeout(() => {
    console.log('Segundo Timeout'); // 2
}, 0);

setTimeout(() => {
    console.log('Tercer Timeout'); // 3
}, 0);
console.log(('Fin de programa')); // 4 
```

Al ejecutarlo nos damos cuenta de lo que sucedió:

![[ciclo-de-eventos.png]]

Lo que sucedió aquí es, que Node.js trabaja estableciendo las funciones en una pila de ejecucion (Como los hilos en java), lo que una vez pasado el tiempo, irán a la pila de ejecucion y se ejecutaran cuando ellos puedan.

Fuente:[Aprendiendo Node](https://aprendiendo-nodejs.blogspot.com/2017/07/entendiendo-el-event-loop.html)


### descripción simplificada:

Video: [Event Loop](https://www.youtube.com/watch?app=desktop&v=b1ZZZERJOPQ)

![[ciclo-eventos.png]]

1. *Inicio del Programa:*
    
    - Cuando ejecutas un script de Node.js, comienza la ejecución del programa. Node.js carga el código del script y lo interpreta.
    
2. *Inicio del Event Loop:*
    
    - Node.js inicia el Event Loop (Bucle de Eventos), que es la parte central del modelo de concurrencia no bloqueante.
    
3. *Ejecución Sincrónica:*
    
    - Node.js ejecuta el código de manera síncrona hasta que encuentra operaciones de entrada/salida (E/S) no bloqueantes.
    
4. *Operaciones de E/S No Bloqueantes:*
    
    - Cuando se encuentra una operación de E/S no bloqueante (por ejemplo, lectura de un archivo, consulta a una base de datos), Node.js delega la operación al sistema operativo y sigue ejecutando otras tareas sin esperar a que se complete la operación de E/S.
    
5. *Event Loop:*
    
    - Mientras espera la finalización de las operaciones de E/S no bloqueantes, Node.js continúa con el Event Loop. El Event Loop revisa la cola de eventos y ejecuta cualquier código asociado a eventos que se hayan completado.

6. *Callback Functions:*
    
    - Cuando una operación de E/S no bloqueante se completa, se coloca en la cola de eventos. Si hay una función de retorno de llamada (callback) asociada con esa operación, se ejecuta.

7. *Manejo de Eventos:*
    
    - Node.js maneja eventos a través de EventEmitter, que es un componente clave del sistema de eventos en Node.js. Los eventos pueden ser emitidos y escuchados por funciones de retorno de llamada.
    
8. *Cierre del Programa:*
    
    - El programa Node.js se cierra cuando no hay más tareas que realizar. Esto puede ocurrir cuando todas las operaciones de E/S han finalizado y no hay más código por ejecutar.


