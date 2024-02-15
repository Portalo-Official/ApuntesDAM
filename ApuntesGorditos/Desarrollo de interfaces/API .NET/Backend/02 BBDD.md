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

Crear una carpeta SQL destinada a la las clases:

- Conexión de BBDD
- DAO - Data Access Object
- DTO - Data Transfer Object

![[carpeta-sql.png]]

### Dotenv

Con Dotenv podemos guardar las variables de entorno (variables delicadas) como acceso a la base de datos en un archivo, de manera que esta nos e suba a repositorios como github.

Así cada quien podrá descargarse el repositorio y poner sus credenciales propias en el archivo .env .

![[nuget-dotenv.png]]


Archivo .env a la altura dentro del proyecto raíz:

![[archivo.env.png]]

```C# hl:3 title='Cargar Variables de entorno'
private ConnectionBD()
{
// Cargar variables de entorno desde el archivo .env
// Poner ruta absoluta de tu archivo .env ( Temporal hasta arreglar)
var rutaAbsoluta = "D:\\DAM\\DAM_Segundo\\Desarrollo_De_Interfaces\\Proyectos_discoDuro\\api-rest-libreria-.net\\api-libreria-dotnet\\.env";
DotEnv.Load(options: new DotEnvOptions(envFilePaths: new[] { rutaAbsoluta }));
    string connectionString = GetConnectionURL();
    try
    {
        this.connection = new MySqlConnection(connectionString);
    }catch (Exception ex)
    {
        throw new Exception("Error al conectarse con la BBDD"+ ex.Message);
    }
}
```

```C# title='Inyectar Variables del Archivo .env'
 private string GetConnectionURL()
 {
     // Coge los valores del archivo .env
     string server = Environment.GetEnvironmentVariable("DB_SERVER");
     string database = Environment.GetEnvironmentVariable("DB_DATABASE");
     string user = Environment.GetEnvironmentVariable("DB_USER");
     string password = Environment.GetEnvironmentVariable("DB_PASSWORD");

     return $"Server={server};Database={database};User ID={user};Password={password};";
 }
```

De esta forma, protegemos información que puede ser importante.

Saber mas: [Dotenv explicado](https://github.com/bolorundurowb/dotenv.net)
## Conexión BBDD

Clase que tendrá la instancia de la conexión de la base de datos con un patrón singleton.

```C# title='ConnectionBD'
public class ConnectionBD
{
    // no se crea ninguna instancia mientras no se tenga acceso por primera vez con Lazy<T>
    private static readonly Lazy<ConnectionBD> lazyInstance = new Lazy<ConnectionBD>(() => new ConnectionBD());
    public static ConnectionBD Instance => lazyInstance.Value;
    private MySqlConnection connection;
    private ConnectionBD()
    {
        DotEnv.Load(); // Cargar variables de entorno desde el archivo .env
        string connectionString = GetConnectionURL();
        try
        {
            this.connection = new MySqlConnection(connectionString);
        }catch (Exception ex)
        {
            throw new Exception("Error al conectarse con la BBDD"+ ex.Message);
        }
    }
    private string GetConnectionURL()
    {
        // Coge los valores del archivo .env
        string server = Environment.GetEnvironmentVariable("DB_SERVER");
        string database = Environment.GetEnvironmentVariable("DB_DATABASE");
        string user = Environment.GetEnvironmentVariable("DB_USER");
        string password = Environment.GetEnvironmentVariable("DB_PASSWORD");

        return $"Server={server};Database={database};User ID={user};Password={password};";
    }

    public MySqlConnection GetConnection()
    {
        if (this.connection.State != System.Data.ConnectionState.Open)
        {
            this.connection.Open();
        }
        return this.connection;
    }
}
```



