
# Introducción

Cuando un proceso síncrono se queda parador en un punto, la pantalla se quedara congelada o en blanco esperando.

Para que esto no ocurra entre microservicios, uno este esperando al proceso del otro, se implementa un mecanismo de fallback para no seguir encolando peticiones en un servicio dependiente.

## Patrón Circuit-Breaker

![[circuit-breaker-dhanushka-one.png | 550]]

Circuit-breaker es un patrón que trata de supervisar las comunicaciones entre microservicios(micros).

Cuando hay un micro se comunica con otro, en ese instante de comunicación, el circuito esta abierto (_open_). Una vez acabada (recibió la respuesta ), el circuito pasará estar cerrado (_close_).

Si un micro externo tarda mucho o no contesta se entiende que el circuito esta abierto.

En vez de seguir intentando la comunicación, responde con una excepción o respuesta alternativa.



# Dependencia

Antes se usaba Hystrix, pero ya esta obsoleto ( si ves tutoriales o guías estar atento de si usa Hystrix, seria la parte que se tiene que cambiar).




