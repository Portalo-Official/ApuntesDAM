#BBDD
# Diagrama E-R

![[Diagrama ER.svg]]


## Código SQL

El código SQL esta en [GitHub](https://github.com/santiagoieshna/api-rest-libreria-.net).

En el se crearán las entidades del diagrama y por cada tabla haremos 4 procedures:

_Ejemplo con Temas:_
- getTemas
- putTema
- updateTema
- deleteTema


## Connector MySQL

Para conectar con una base de datos, necesitamos un Connector especifico para esa BBDD, una interfaz para comunicarnos con ella.

Tenemos 2 Opciones de descarga

1. Connector MySQL: [MySQL_connector](https://dev.mysql.com/downloads/connector/net/)

- Si lo instalas por aquí después click en Referencias y agregar referencia

![[agregar-referencias.png]]

2. Con el Gestor de paquetes NuGet:

![[nuget-mysql-connector.png]]


## Modificar WebApiConfig

Añadiremos en el archivo un fragmento de código para añadir un nuevo tipo de medio (mediatype) a los formatos de respuesta admitidos por el formateador JSON. 

_Nota_: Ver códigos en modo escritura es mas legible que en modo lectura.
```C# hl:14 title='WebApiConfig
 public static class WebApiConfig
 {
     public static void Register(HttpConfiguration config)
     {
         // Configuración y servicios de Web API
         // Rutas de Web API
         config.MapHttpAttributeRoutes();

         config.Routes.MapHttpRoute(
             name: "DefaultApi",
             routeTemplate: "api/{controller}/{id}",
             defaults: new { id = RouteParameter.Optional }
         );
    config.Formatters.JsonFormatter.SupportedMediaTypes.Add(new System.Net.Http.Headers.MediaTypeHeaderValue("text/html"));
     }
 }
```

# Carpeta SQL





## Dotenv

![[Pasted image 20240107031947.png]]
