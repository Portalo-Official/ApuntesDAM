
# Response - Request 

Creamos 2 clases destinadas  a la petición de la base de datos y la respuesta de esta

```c# title='Request'
 public class Request
 {
     public long Id { get; set; }
     public string Name { get; set; }
 }
```

```c# title='Response'
public class Response
{
    public string OK { get; set; }
    public string Error { get; set; }
    public Object Data { get; set; }
}
```