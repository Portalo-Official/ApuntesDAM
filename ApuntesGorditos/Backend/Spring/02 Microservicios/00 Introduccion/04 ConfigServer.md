
# ConfigServer

Servicio destinado a centralizar la configuración (Yaml) de cada microservicio de la aplicación.

## Dependencia

### Para el servidor de configuraciones
![[configserver-dependencia.png]]

### Para los servicios clientes


## Decoradores

En la clase para ejecutar la aplicación añadimos _@EnableConfigServer_.

![[configserver-decorator.png]]

## Configuraciones

### Centralización para los microservicios

La configuración para cada uno de los micro servicios vendrá en archivos .yml individuales en el directorio _configurations_.


![[configserver-configurations.png]]

### Configuración de ConfigServer

```yml title='aplication.yml en ConfigServer'
server:
  port: 8092

spring:
  profiles:
    active: native
  application:
    name: ms-config

# Indicar donde estan las configuraciones para los servicios
cloud:
  config:
    server:
      native:
        search-locations:
         - classpath:/configutarions
```

