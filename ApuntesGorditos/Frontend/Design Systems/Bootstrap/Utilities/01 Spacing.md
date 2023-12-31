### Spacing

Fuente: [Spacing](https://getbootstrap.com/docs/5.3/utilities/spacing/)

Con el se añade el _padding_ y _margin_, estructura:

_{propiedad}{lado}-{tamaño}_

El espaciado va de .25rem a 3rem por defecto. tiene una variable $spacer, que sera el espacio del entorno.

la variable $spacer se encuentra en el [Sass](https://getbootstrap.com/docs/5.3/utilities/spacing/#sass-maps) map:

```scss title='scss/_variables.scss'
$spacer: 1rem;
$spacers: (
  0: 0,
  1: $spacer * .25,
  2: $spacer * .5,
  3: $spacer,
  4: $spacer * 1.5,
  5: $spacer * 3,
);
```


#### Propiedad

- `{json}m` - poner `margin`
- `p` - poner `padding`

#### Lado

- **t** -->  _margin-top_ o _padding-top_
- **b** -->  _margin-bottom_ o _padding-bottom_
- __s__ --> (start)  _margin-left_ o _padding-left_ en LTR, _margin-right_ o _padding-right_ en RTL
- __e__ --> (end)  _margin-right_ o _padding-right_ en LTR, _margin-left_ o _padding-left_ en RTL
- __x__ --> poner ambas _\*-left_ y _\*-right_
- __y__ --> poner ambas _\*-top_ y _\*-bottom_

#### Size

- 0 --> para eliminar margin o padding (valor 0)
- 1 --> Poner espacio a $spacer * .25rem.
- 2 --> Poner $spacer * .5rem.
- 3 --> Poner $spacer.
- 4 --> Poner $spacer * 1.5rem.
- 5 --> Poner $spacer * 3rem.
- auto --> poner el margin auto.

### Ejemplo

Cuando ponemos en la class de un html, estos apartados están definidos en `scsss/_utilities.scss`, que pertenece al [Sass Utilities API](https://getbootstrap.com/docs/5.3/utilities/spacing/#sass-utilities-api)

```html title='Ejemplo de Spacing'
<div class="mx-auto p-2" style="width: 200px;">
  Centered element
</div>
```