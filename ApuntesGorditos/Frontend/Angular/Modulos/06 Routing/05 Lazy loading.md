
# Carga perezosa

Primero de todo tenemos que tener un routing.ts main y otro secundario con rutas hijas.

En la siguiente imagen, vemos una estructura de directorios de una aplicación donde tenemos el routing.ts principal (_1_) y uno secundario (_2_).

![[Frontend/Angular/Modulos/06 Routing/ANEXO/Pasted image 20240219233230.png|300]]
### Routing secundario
El secundario (___2___) tendrá sus hijas y en el import tendrá un .forChild(routes):

```ts
const routes: Routes = [
                    {
                       path: '',
                       component: BasicsPageComponent
                    },
                    {
                       path: 'number',
                       component: NumberrPageComponent
                    },
                    {
                       path: 'common',
                       component: CommonPageComponent
                    },
                    {
                       path: '**',
                       component: BasicsPageComponent
                    },
                  ];
@NgModule({
  imports: [RouterModule.forChild(routes)],
  exports: [RouterModule]
})
```

### Routing primario

Es algo feo como se hace.

```ts hl=8,9
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';  

const routes: Routes =[
              {
                 path: '',
                 loadChildren:
                  () => import('./products/products.module')
			                 .then(m => m.ProductsModule)
              },
            ];
@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule { }
```

