

Creamos un proyecto ASP .NET Framework API Web

### Borrar contenidos


Una vez creado, borramos los controles, carpeta view, y en el directorio 


##### Directorio App_start 

Quedamos solo *WebApiConfig.cs*.

![[WebApiConfig.cs.png|500]]

##### Archivo global.axax

Borramos las líneas de los archivo que se borraron en App_start



## Controllers

Recordar que la API que montaremos será para libros

### Crear Controller

Creamos un controller en el framework como siempre:
click derecho -> Agregar-> controlador 

Una vez ahí elegir la opción *Web Api*  en blanco.
![[crear-controller-webapi.png]]

Empezamos creando el controlador para temas.

````c#  title=temasController
[HttpGet]
[Route("tema-controller")]
public List<string> getTemas()
{
    return new List<string> { "Terror", "Romance", "Aventura"};
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
````

Una vez hecho esto, comprobamos por Postman que los métodos se llamen bien.


