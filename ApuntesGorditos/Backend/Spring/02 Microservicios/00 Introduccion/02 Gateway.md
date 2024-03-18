
# Gateway

Es el servicio de punto de entrada para la aplicación, donde un frontend hará peticiones.

## Dependencias

![[gateway-dependencias.png]]
### Función de cada una

- _Gateway_: proporcionar un punto de entrada a nuestro ecosistema de microservicios, proporcionando capacidades de enrutamiento dinámico, seguridad y monitorización de las llamadas que se realicen.
- _Eureka Discovery Client_: Para poder registrar el microservicio en el servidor de Eureka.
- _Config Client_: Poder guardar la configuración del microservicio en el [[04 ConfigServer|configserver]]
- _Actuator_: Seguimiento del microservicio.

