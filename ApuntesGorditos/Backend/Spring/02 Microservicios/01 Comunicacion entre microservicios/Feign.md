
# Introducción 

Feign es una librería desarrollada por Netflix que nos permite generar clientes de servicios web de forma declarativa.

# Dependencia

![[openfeig-dependencia.png]]

Una vez instalada la dependencia hay que usar el decorado _@EnableFeignClients_ en la aplicación.

![[feign-enable.png]]

# Uso 

Tenemos un endPoint en un servicio llamado getEstudiante:

![[estudiante-endpoint.png]]

Desde otro servicio llamado curso, queremos comunicarnos con el y coger el endpoint "/estudiante/uno", que en este caso nos devolverá "Soy un estudiante".

Para ello crearemos una interfaz donde definiremos el mismo endPoint y retorno de el.

![[feign-interface01.png]]

Usamos el decorador _@FeignClient_
`@FeignClient(name="ms-estudiante", url="localhost:8090/estudiante")`
- _name_: Nombre del microservicio (Lo conoce por estar conectado a Eureka)
- _url_: Indica la cabecera principal para el endpoint


