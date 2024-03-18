
# Yaml

Formato para configuración de proyectos.

## Microservicio
```yml title='Configuracion Microservicio'
# Server
server:
  port: 8091
  compression:
    enabled: true
# Aplicacion
spring:
  application:
    name: ms-curso
# Registrarse en Eureka
eureka:
  instance:
    hostname: localhost
  client:
    service-url:
      defaultZone: http://${eureka.instance.hostname}:8761/eureka
```

