
# Yaml

formato de serialización de datos legible, se usa para configuración de proyectos en este ámbito.

Cada nivel se diferencia por 2 espacios, evitar usar _Tab_. 
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

