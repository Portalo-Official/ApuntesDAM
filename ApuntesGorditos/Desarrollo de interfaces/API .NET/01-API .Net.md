
# API en ASP .NET C\#
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


