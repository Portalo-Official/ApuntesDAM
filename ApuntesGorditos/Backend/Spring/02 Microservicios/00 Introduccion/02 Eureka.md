
# Eureka

Eureka es un microservicio que actúa como registrador. Su función es registrar los microservicios del entorno de la aplicación.

## Decorador

Para indicar que va a actuar como un servidor que registre, se indica con el decorador ___@EnableEurekaServer___.

![[eureka-decorador.png]]

## Dependencias

_Eureka Server_: Para registrar los demás microservicios.
_Config Client_: Para centralizar las configuraciones en el servicio ConfigServer.
_Actuator_: Métricas.

![[eureka-dependencias.png]]

## Configuración

```yml title='Configuracion Eureka'
server:
  port: 8761

spring:
  application:
    name: ms-eureka
    
# Registrador
eureka:
  instance:
    hostname: localhost
  client:
    # En que sitio trabaja
    service-url:
      defaultZone: http://${eureka.instance.hostname}:${server.port}/eureka/
# Decirle al server que no se registre como microservicio
    register-with-eureka: false
    fetch-registry: false
```

## Lado del Cliente

Desde el lado de cliente usaremos el decorador _@EnableDiscoveryClient_.

![[eureka-cliente.png]]

