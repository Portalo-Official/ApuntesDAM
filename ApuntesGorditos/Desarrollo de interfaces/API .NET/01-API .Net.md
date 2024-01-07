
# API en ASP .NET C\#

Todo el proyecto esta en [GitHub](https://github.com/santiagoieshna/api-rest-libreria-.net)
## Crear Proyecto

Creamos un proyecto ASP .NET Framework API Web

![[crear-proyecto-asp.png]]

![[api-web-proyecto.png]]
### Borrar contenidos


Una vez creado, borramos:

- Todos los controladores (la carpeta la queremos)
- Directorios:
	- view
	- Scripts
	- Áreas
	- Content

Contenido resultante:
![[contenido-resultante.png]]
##### Directorio App_start 
Borramos todo menos *WebApiConfig.cs*.

##### Archivo global.axax

Borramos las líneas de los archivo que se borraron en App_start

![[global-axax.png|500]]

## Controllers

Recordar que la API que montaremos será para libros

### Crear Controller

Creamos un controller en el framework como siempre:
click derecho -> Agregar-> controlador 

Una vez ahí elegir la opción *Web Api*  en blanco.
![[crear-controller-webapi.png]]

Empezamos creando el controlador para temas.
Sus funciones irán decoradas con los verbos de HTTP

_Nota_: Ver códigos en modo escritura es mas legible que en modo lectura.
````c#  title=temasController
[RoutePrefix("api/tema")]
public class TemaController : ApiController
{
    [HttpGet]
    [Route("tema-controller")]
    public List<string> getTemas()
    {
        return new List<string> { "Terror", "Romance", "Aventura" };
    }

    [HttpPut]
    [Route("tema-controller")]
    public string putTemas()
    {
        return "Insertando Tema con su EndPoint";
    }

    [HttpPost]
    [Route("tema-controller")]
    public string postTemas()
    {
        return "Actualizar tema";
    }

    [HttpDelete]
    [Route("tema-controller")]
    public string deleteTema()
    {
        return "Borrar tema";
    }
}
````

Una vez hecho esto, comprobamos por Postman que los métodos se llamen bien.

Esto se hará  para formato, edición y Autor (con la misma estructura).
### Crear Modelos (POJO)

POJO -> Plain Old Java Object. Un objeto plano como los modelos que estamos creando.

Crearemos modelos de Temas, Autor, Edición y Formato.

```c# title='Tema.cs'
  public class Tema
  {
      public int Id { get; set; }
      public string Temas { get; set; }
  }
```

```C# title='Autor'
public class Autor
{
    public int id { get; set; }
    public string nombre { get; set; }
}
```

```C# title='Edicion'
 public class Edicion
 {
     public int id { get; set; }
     public string nombre { get; set; }
 }
```

