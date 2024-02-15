
# Directiva ngFor

Directiva que sirve para iterar en el HTML.

```html title='Directiva ngFor'
<ul >
  <li *ngFor="let name of heroNames" > {{name}} </li>
</ul>
```

`let name of heroNames`  -> heroNames es un array String\[\]  que esta declarado en el TS del componente.

```ts title='fragmento de TS del componente'
export class HeroesListComponent {

  public heroNames : string[] = ['Spiderman', 'Iron Man', 'Hulk', 'Black Widow'];

}
```

Saliendo el siguiente resultado:

![[ngfor-html.png]]

## Variables locales

*Index* --> Variable que indica el número de la iteración.

*First*

*Last*

*Even*

*Odd*

