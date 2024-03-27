
# Gateway

Es el servicio de punto de entrada para la aplicación, donde un frontend hará peticiones.

Este microservicio es conocido como un load balancer (balanceador de carga)
## Dependencias

![[gateway-dependencias.png]]

```xml title='pom del proyectop Maven'
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-actuator</artifactId>
</dependency>
<dependency>
	<groupId>org.springframework.cloud</groupId>
	<artifactId>spring-cloud-starter-config</artifactId>
</dependency>
<dependency>
	<groupId>org.springframework.cloud</groupId>
	<artifactId>spring-cloud-starter-gateway</artifactId>
</dependency>
<dependency>
	<groupId>org.springframework.cloud</groupId>
	<artifactId>spring-cloud-starter-netflix-eureka-client</artifactId>
</dependency>
```


### Función de cada una

- _Gateway_: proporcionar un punto de entrada a nuestro ecosistema de microservicios, proporcionando capacidades de enrutamiento dinámico, seguridad y monitorización de las llamadas que se realicen.
- _Eureka Discovery Client_: Para poder registrar el microservicio en el servidor de Eureka.
- _Config Client_: Poder guardar la configuración del microservicio en el [[04 ConfigServer|configserver]]
- _Actuator_: Seguimiento del microservicio.

## Configuración

```yml title='Configuracion GateWay'
server:
  port: 8081
spring:
  application:
    name: ms-gateway
  cloud:
    gateway:
    # Declarar los micro servicios
      route:
        # MicroServicio 1
        - id: ms-estudiante
		  # lb -> load Balance
		  uri: lb://ms-estudiante
		  # Declarar endpoint de acceso
		  predicates:
		    - Path= /estudiante/**
		# Microservicio 2
		- id: ms-curso
		  uri: lb://ms-curso
		  predicates:
		    - Path= /curso/**
eureka:
	instance:
	  hostname: localhost
	client:
	  service-url:
	    defaultZone: http://${eureka.instance.hostname}:8761/eureka
```


