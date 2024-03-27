
# Introducción

Cuando un proceso síncrono se queda parador en un punto, la pantalla se quedara congelada o en blanco esperando.

Para que esto no ocurra entre microservicios, uno este esperando al proceso del otro, se implementa un mecanismo de fallback para no seguir encolando peticiones en un servicio dependiente.

## Patrón Circuit-Breaker

![[circuit-breaker-dhanushka-one.png | 550]]

Circuit-breaker es un patrón que trata de supervisar las comunicaciones entre microservicios(micros).

Cuando hay un micro se comunica con otro, en ese instante de comunicación, el circuito esta abierto (_open_). Una vez acabada (recibió la respuesta ), el circuito pasará estar cerrado (_close_).

_Ejemplo_:

Si un micro externo tarda mucho o no contesta se entiende que el circuito esta abierto.

En vez de seguir intentando la comunicación, responde con una excepción o respuesta alternativa.

Por supuesto sigue pendiente de saber si el circuito se ha vuelto a cerrar, el micro externo funciona de nuevo para redirigir peticiones.

Con circuito _open_ da un tiempo sin peticiones al micro. Pasado este tiempo vuelve a aceptar peticiones, estado semi-abierto (_Half-open_), e intenta volver a conectarse al micro externo. Si pasa el tiempo si contestar vuelve al estado _open_ y trata las peticiones según la política seguida.

# Dependencia

Antes se usaba _Hystrix_, pero ya esta obsoleto ( si ves tutoriales o guías estar atento de si usa Hystrix, seria la parte que se tiene que cambiar).

_ResilenceJ4_ es la dependencia supporteada por Netflix actualmente.

![[resilencej4-circuit-breaker.png]]

Aparte también necesitamos la dependencia _AOP_, que ni [spring initializr](https://start.spring.io/) ni el wizard de eclipse. 

```xml title='Otras Dependencias'
<!-- Dependencia AOP - para circuit-breaker -->
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-aop</artifactId>
</dependency>

```

## Decoradores e implementación

Uso del decorador _@CircuitBreaker_. Con los parámetros, nombre y fallbackMethod.

fallbackMethod indica que método ejecutar en caso de que salte una excepción.

![[resilence4j-implementation.png]]

## Configuración

Con Resilencej4 no hace falta tocar la configuración a priori para la puesta en marcha.

```yml title='Configuracion para CircuitBreaker'
resilience4j.circuitbreaker:
  configs:
    defaults:
	  # Indicador de salud, para saber si esta abierto o no
	  registerHealthIndicator: true
	  # Tamanio de ventanas que se pueden aceptar
	  slidingWindowSize: 10
	  # Numero minimo de llamandas
	  minimumNumberOfCalls: 5
	  # Llamadas permitidas en estrado Medio Abierto
	  permittedNumberOfCallsInHalfOpenState: 3
	  # Transicion automatica de Abierto a Medio Abierto
	  automaticTransitionFromOpenToHalfOpenEnabled: true
	  # Estado de espera, para saber si te esta fallando o no una peticion
	  waitDurationInOpenState: 5s
	  # Cantidad de fallos que permite
	  failureRateThreshold: 50
	  eventConsumerBufferSize: 10
```
