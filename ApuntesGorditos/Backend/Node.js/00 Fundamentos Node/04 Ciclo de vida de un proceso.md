
## Explicación 

En el ejemplo de [[03 Ciclo de eventos de Node#Ejemplo|Ciclo de eventos]] vimos como la ejecución del archivo no se resolvió como esperamos.

![[pila-de-procesos.png]]

Cuando un script js se ejecuta, tiene un main, este se ejecuta en la Pila de procesos (Franja Verde de la izquierda en la imagen) y va llamando una a una sus ejecuciones para completarlas.

En el momento que llama a un método _setTimeout_, este no se ejecuta y pasa a Node Apis (franja central azul), un lugar donde Node esta pendiente de sus procesos como respuesta de tareas [[Asincronía Índice|asincronas]].

Una vez pasado el tiempo del setTimeout, este pasará a ejecutarse, pero _NO_ va directo a la Pila de procesos, si no que va a la _cola de callbacks_(franja de la derecha).

En el momento que main ha recorrido todo, el termina, pero esto no quiere decir que la aplicación termina.

Los otros procesos que está la pila de procesos vacía, Node vera la cola de callbacks, y los ira pasando a la pila de procesos para ejecutarse.

![[event-llop-stack.png]]