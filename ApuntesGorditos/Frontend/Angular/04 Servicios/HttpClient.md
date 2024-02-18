#peticionHttp

fuente: [HttpClient Blog](http://blog.enriqueoriol.com/2017/11/httpclient-vs-http-angular.html)
# HttpClient

`HttpClient` es un cliente con los métodos REST habituales (a continuación), que está basado en `Observables`. Básicamente es lo que vas a utilizar para hacer llamadas a una API REST y obtener resultados de la misma.

Métodos:
```ts title=''
get(url: string, options: {...}): Observable<any>
delete(url: string, options: {...}): Observable<any>
patch(url: string, body: any|null, options: {...}): Observable<any>
post(url: string, body: any|null, options: {...}): Observable<any>
put(url: string, body: any|null, options: {...}): Observable<any>

head(url: string, options: {...}): Observable<any>
options(url: string, options: {...}): Observable<any>
jsonp<T>(url: string, callbackParam: string): Observable<T>

request(first: string|HttpRequest<any>, url?: string, options: {...}): Observable<any>
```

Otros detalles que vale la pena recordar:

- *La suscripción se cancela al completar la petición*, así que no tienes que gestionarlo tú.
- Devuelve _cold observables_
- No se ejecuta ninguna _request_ hasta que no se llama al método `subscribe()`
- Los objetos `HttpRequest`, `HttpHeaders` y `HttpParams` son inmutables.

### JSON como respuesta por defecto

El nuevo servicio HttpClient te **devuelve** directamente **el body de la respuesta, parseado como JSON**. Esta aproximación simplifica el código en la mayoría casos. Eso sí, si trabajas con otro tipo de respuesta, tendrás que escribir algo más de código.

```ts
//new Angular HttpClient service
http.get('/api/items')
.subscribe(data => {   // data is already a JSON object
    console.log(data['someProperty']);
});
```

