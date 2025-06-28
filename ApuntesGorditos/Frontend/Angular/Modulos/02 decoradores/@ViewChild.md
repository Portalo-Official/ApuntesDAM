#angular 

# Modo de uso

Decorador que sirve para capturar valores de un elemento HTML.

Ejemplo:

Tenemos un buscador ( el ejemplo esta con clases de bootstrap).

```html title='Template de componente'
<h5>Buscar</h5>
    <input type="text"
    class="form-control"
    placeholder="Buscar gifs...">
```


![[formulario-viewchild.png]]

Para capturar lo que se ha escrito en el buscador, se hace uso de @ViewChild .

En la clase del componente tendrá un atributo en este ejemplo llamado newTag de tipo *ElementRef*, indicando sobre que elemento hacemos referencia, en este caso un input (*HTMLInputElement* para typescript).

```ts  title='search.component.ts'
export class SearchBoxComponent {

  @ViewChild('txtTagInpunt')
  tagInput? : ElementRef<HTMLInputElement>;
  
  constructor(){}
  
  searchTag( ){
      console.log(this.tagInput.nativeElement.value);
  }

}
```

Para capturar el valor presionando *Enter*, basta con usar el evento (keyup.enter) que nos ofrece angular.

```html title='Template de componente'
<h5>Buscar</h5>
    <input type="text"
    class="form-control"
    placeholder="Buscar gifs..."
    (keyup.enter)="searchTag()"
    #txtTagInpunt>
```

## Parámetros 

*@VieChild(__elemento__)* --> en su parámetro, estará como se llama el elemento por su id, en este caso (línea 6 del bloque de código anterior) es _txtTagInput_.
