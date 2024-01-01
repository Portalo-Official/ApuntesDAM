
Esto es pura teoría, si quieres ponerte a practicar avanza.
# Blocking vs non-blocking
Fuente: [lemoncode](https://lemoncode.net/lemoncode-blog/2018/1/29/javascript-asincrono)



### No Bloqueo (No Bloqueante):

- _Definición_:
    
	En un entorno no bloqueante, las tareas pueden continuar ejecutándose sin esperar a que otra tarea se complete. Las operaciones de E/S (entrada y salida) se inician y el programa sigue con otras tareas mientras espera la finalización de esas operaciones.
 
- _Ejemplo Analógico_:
    
	Siguiendo con la analogía del café, en un entorno no bloqueante, podrías realizar otras actividades mientras esperas tu turno para ordenar. Puedes revisar tu teléfono o charlar con un amigo sin afectar el flujo general.
	
- _En Node.js_:
    
	En un entorno no bloqueante de Node.js, las operaciones de E/S no detienen la ejecución del programa. En lugar de bloquear, se utiliza un enfoque asincrónico, donde las operaciones se delegan y se procesan cuando se completan, lo que puede mejorar la eficiencia y el rendimiento.


### Ventajas de No Bloqueante en Node.js:

- Mejora la eficiencia al permitir que múltiples operaciones se ejecuten simultáneamente.
- Aprovecha al máximo la capacidad de respuesta en situaciones de E/S intensivas.
- Permite gestionar múltiples solicitudes sin necesidad de un hilo dedicado para cada una.