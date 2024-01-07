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
    DotEnv.Load(); // Cargar variables de entorno del archivo .env
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

## Manipulando Data

Fuente: [Patrón de software](https://rjcodeadvance.com/patrones-de-software-que-es-patron-de-diseno-parte-2/)
Fuente: [Blog interesante](https://www.oscarblancarteblog.com/2018/11/30/data-transfer-object-dto-patron-diseno/)
Fuente: []()
### Patrón de software 



#### DAO

Data Access Object es la clase destinada a la implementación para obtener los datos de la base de datos.


```C# title='TemaDAO'
public class TemaDAO
{
    private readonly MySqlConnection connection;

    public TemaDAO(MySqlConnection connection)
    {
        this.connection = connection;
    }

    public List<DTO_Tema> ObtenerTodosLosTemas()
    {
        List<DTO_Tema> temas = new List<DTO_Tema>();

        using (MySqlCommand command = new MySqlCommand("getTemas", connection))
        {
            command.CommandType = System.Data.CommandType.StoredProcedure;

            using (MySqlDataReader reader = command.ExecuteReader())
            {
                while (reader.Read())
                {
                    temas.Add(DTO_Tema.FromDataReader(reader));
                }
            }
        }

        return temas;
    }

    public void AgregarTema(string nuevoTema, int idTema)
    {
        using (MySqlCommand command = new MySqlCommand("putTema", connection))
        {
            command.CommandType = System.Data.CommandType.StoredProcedure;
            command.Parameters.AddWithValue("@nuevoTema", nuevoTema);
            command.Parameters.AddWithValue("@idtema", idTema);
            command.ExecuteNonQuery();
        }
    }

    public void ActualizarTema(int id, string temaActualizado)
    {
        using (MySqlCommand command = new MySqlCommand("updateTemas", connection))
        {
            command.CommandType = System.Data.CommandType.StoredProcedure;
            command.Parameters.AddWithValue("@id", id);
            command.Parameters.AddWithValue("@temaActualizado", temaActualizado);

            command.ExecuteNonQuery();
        }
    }

    public bool EliminarTema(int id)
    {
        using (MySqlCommand command = new MySqlCommand("deleteTema", connection))
        {
            command.CommandType = System.Data.CommandType.StoredProcedure;
            command.Parameters.AddWithValue("@id_Tema", id);

            int rowAffected = command.ExecuteNonQuery();
            return rowAffected > 0; // Retorna -1 para cualquier otro valor no Query ok
        }
    }
}
```


#### DTO

Fuente: [Video DTO](https://www.youtube.com/watch?v=4p6z6hL8BNg)




#### Mapper

Fuente: [AutoMapper](https://bravedeveloper.com/2021/12/24/aplicando-el-patron-dto-y-mapeando-objetos-con-automapper-en-un-web-api-con-net-core/)
Fuente: [Video AutoMapper](https://www.youtube.com/watch?v=pr_pemcmVAs)

