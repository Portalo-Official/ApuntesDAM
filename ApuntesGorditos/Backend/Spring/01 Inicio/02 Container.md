#IoC #spring
Spring proporciona un contenedor que *maneja todo lo que se hace con los objetos del IoC*. Debido a la naturaleza del IoC, el contenedor más o menos ha definido el ciclo de vida de los objetos y resuelve las dependencias entre los servicios que él controla.

IoC --> Inversión de dependencias.

Resumen: el _container_ es un objeto que sabe como instancias y configurar objetos y sus objetos dependientes.

![[SpringModulesContainer.gif]]

### Módulos

spring-core --> Encargado de implementar el código de IoC de Spring permitiendo inyectar beans.

spring-beans --> Encargado de añadir Factorías como BeanFactory, instancia distintos beans registrados en el framework.

spring-context --> Este módulo es el encargado de añadir un contexto al framework y se encarga por ejemplo de simplificar la carga de los distintos recursos. Es en este package en el que nos encontramos el interface de *ApplicationContext*.

spring-context-support --> Encargado de añadir las clases que gestionan servicios complementarios como Cache, Mail, Quartz etc.

