#angular #routing 

# Que es el Routing

- El **routing** es un mecanismo que permite navegar entre diferentes vistas o componentes en una aplicación web sin recargar la página completa.
    
- Se usa especialmente en aplicaciones SPA (_Single Page Application_).

## Por qué es importante en SPAs

- Mejora la experiencia de usuario (UX) al facilitar una navegación fluida y rápida.
    
- Permite organizar claramente el flujo de navegación.
    
- Facilita el mantenimiento y escalabilidad de la aplicación mediante rutas claras.

## Como funciona en Angular

- Angular maneja rutas con un módulo específico llamado `RouterModule`.
    
- Cada ruta está asociada a componentes específicos que se renderizan en el lugar designado por `<router-outlet>`.

### Conceptos clave

- **Rutas**: definición del path y componente asociado.
    
- **RouterModule**: módulo para definir y gestionar rutas.
    
- **router-outlet**: directiva que indica dónde cargar los componentes asociados a las rutas.

### Ejemplo



```typescript title="Archivo routes.ts" 
// app-routing.module.ts
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { HomeComponent } from './home/home.component';
import { AboutComponent } from './about/about.component';

export const routes: Routes = [
  { path: '', component: HomeComponent },
  { path: 'about', component: AboutComponent }
];

```


#### Routerlink

Para llamar al Routing desde HTML


```html title="app.main.ts"
<!-- app.component.html -->
<nav>
  <a routerLink="/">Home</a>
  <a routerLink="/about">About</a>
</nav>

<router-outlet></router-outlet>

```

## Angular 19+

Para que esto funcione, se necesita importar la parte del routerLink

```typeScript  hl=2,7 title="Importar RouterLink"
import { Component } from '@angular/core';
import { RouterLink } from '@angular/router';
  

@Component({
  selector: 'app-navbar',
  imports: [RouterLink],
  templateUrl: './navbar.html',
  styleUrl: './navbar.css',
})
export class customComponent {

}
```