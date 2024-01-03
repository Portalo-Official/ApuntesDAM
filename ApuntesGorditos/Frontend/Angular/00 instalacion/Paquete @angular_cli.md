
# Paquete @angular/cli

Fuente: [angular.io](https://angular.io/cli)

Fuente: [angular.dev](https://angular.dev/tools/cli)-> Beta Docs (Angular 17)

Instalación: con [[07 npm|npm]]

Es una interfaz de líneas de comandos para facilitar la creación en angular.

Pdf Resumen de Comandos: [[angular-cheat-sheet.pdf]].

### Instalación global

`{bash}npm install -g @angular/cli`

### Iniciar proyecto Angular

Comando:

`{bash}ng new my-app`

Pero como se explica en [[Angular actualización]] usaremos:

`{bash}ng new my-app --standalone false`

### Levantar servidor

`{bash}npm start` --> Por defecto de Node.js

`ng serve`

Una vez levantado, los cambios se realizaran al guardar los archivos.


### Generar componentes

`{bash}ng g c [name]` -> Puede ser el nombre solo o con ruta.

_Ejemplo_
``` title='Consola: Crear componente por ruta'
$ ng g c heroes/hero
CREATE src/app/heroes/hero/hero.component.html (19 bytes)
CREATE src/app/heroes/hero/hero.component.spec.ts (587 bytes)
CREATE src/app/heroes/hero/hero.component.ts (191 bytes)
CREATE src/app/heroes/hero/hero.component.css (0 bytes)
UPDATE src/app/app.module.ts (560 bytes) 
```



