
# Introducción

Es el microservicio destinado a conectarse con la base de datos o hacer cualquier actividad relacionada con la lógica de negocios (productos, usuarios, mailing...).


## Dependencias

Las dependencias esenciales para la conexión en el entorno de un microservicio sin contar las suyas propias para el negocio(jpa, mongo, stream) son las siguientes:

![[servicio-negocio-dependencias.png]]

## Configuración

### Configuración intrínseca del servicio

La configuración propia que le da valor como individualidad (nombre, puerto, otras configuraciones para ajustarse a sus necesidades).

La parte básica destinada al entorno de los microservicios es:

```yml title='Configuracion Basica'
# Server
server:
  port: 8091

# Aplicacion
spring:
  application:
    name: ms-curso
  
eureka:
  instance:
    hostname: localhost
  client:
    service-url:
      defaultZone: http://${eureka.instance.hostname}:8761/eureka
```

En este ejemplo, no estamos contando con las configuraciones destinadas a conexiones de base de datos u otras que hagan falta para llevar a cabo su actividad en el modelo de negocio.

### Configuración centralizada en ConfigServer

```yml title='application.yml apuntando a ConfigServer'
spring:
  application:
    name: ms-curso
  config:
    import: optional:configserver:http://localhost:8888
```

