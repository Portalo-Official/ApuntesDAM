# Spring
Fuente: [introducción a Spring](https://miblogtecnico.wordpress.com/2013/11/08/introduccion-a-spring/)

Temas vinculantes: 
 - [Inyección de Dependencias](https://miblogtecnico.wordpress.com/2013/11/07/inyeccion-de-dependencias/)
 - [Programación Orientada a Aspectos](https://miblogtecnico.wordpress.com/2013/11/05/programacion-orientada-a-aspectos/)

**Spring** es un marco de trabajo (framework) que facilita el desarrollo de aplicaciones Java. La idea es que Spring maneje la infraestructura de las aplicaciones y el programador sólo se centre en la aplicación. Es por ello, que el programador se encargará de programar la lógica de negocio usando objetos simples de Java o [POJOs](http://es.wikipedia.org/wiki/Plain_Old_Java_Object "POJOs") (plain old Java objets) y Spring se encargará de añadir las capacidades de empresa o J2EE a nuestra aplicación. 

Spring tiene estas características:

- *Simplicidad y acoplamiento débil*: permite programar Java de una forma más sencilla: busca ser simple y se basa en la inyección de dependencias para obtener un acoplamiento débil.
- *Es un contenedor*: que gestiona el ciclo de vida de los objetos y como se relacionan entre ellos. Proporciona una gran infraestructura que permite que el programador se dedique a la lógica de la aplicación.
- *Ligero*: es muy rápido en tiempo de procesamiento y no es invasivo a la hora de programar.
- *Orientado a aspectos*: soporta la programación orientada a aspectos, lo que permite facilitar una capa de servicios que son ideales para este tipo de programación como auditoría, o gestión de transacciones.

AOP (aspect-oriented programming) --> tratar las *obligaciones transversales* de nuestros programas como módulos separados (aspectos) para lograr una correcta separación de responsabilidades.

Spring se divide en varios módulos que pueden ser agregados dependiendo de las necesidades.

![[spring-modules.webp]]

Aparte de estos 20 módulos, Spring dispone de diversos módulos/librerías que nos ayudan y simplifican el desarrollo del software: gestor de transacciones, gestor de seguridad, Email, Spring remote…

Por ejemplo el gestor de seguridad nos proporciona objetos para el trabajo de sesiones, con páginas de inicio y cierre de sesión y que el programador no tenga que preocuparse por esta parte del desarrollo. El gestor de transacciones simplifica notablemente desarrollar aplicaciones con transacciones ya que parte del desarrollo la proporciona Spring.

resumen final: podemos decir que Spring es un framework (un conjunto de librerías, APIS…) que simplifican enormemente el desarrollo de aplicaciones en Java, permitiendo al programador centrarse en el código de la aplicación y dejando a Spring el resto funcionalidades.
### Spring Framework


### Core Container

El módulo _Core Container_ nos permite configurar nuestra aplicación, incluyendo la característica de inyección de dependencias (IoC) para desacoplar el código de nuestra aplicación. También contiene el Contexto para el desarrollo de componentes J2EE y un lenguaje de Expresiones (SpEL).

### Data 

Permite la integración de la persistencia en las aplicaciones.
Tiene módulos como 
_JDBC_: conexión a base de datos.
_ORM_: Object Relational Mapping 
 - Hibernate: proveedor de persistencia --> JPA (implementación)

### Web
El módulo *Web* permite la integración del desarrollo de aplicaciones orientadas al web.
Contiene un módulo para implementar aplicaciones orientadas en el modelo de vista controlador (MVC), un módulo de integración con Struts y un módulo para la integración de Portlets.

### AOP
El módulo *AOP* permite la integración del desarrollo de aplicaciones orientadas a aspectos (orientadas a módulos).

### Instrumentation

El módulo de *Instrumentación* proporciona una implantación de cargador de clases para ciertos servidores de aplicaciones.

### Test

El módulo *Test* permite la integración de componentes de Testeo, tal como Junit en el desarrollo de aplicaciones.

## Spring Security

## Spring Boot

## Spring MVC

- Bloqueante
- Síncrona
- Un hilo por petición
- Servlet : Mecanismo de comunicación