
## Configurando Vite

Cuando necesitamos las características por defecto, todo es mas fácil. Pero cuando queremos que el proyecto se builde de una manera en especifico, hay que hacer uso del archivo de configuración de Vite: [vite.config.json](https://es.vitejs.dev/config/) .

### Funcionalidades
#### Base

Fuente: [base](https://es.vitejs.dev/config/shared-options.html#base)

Definir la Ruta pública base cuando se sirve en desarrollo o producción.

Se suele necesitar cuando se intenta subir nuestra aplicación a [GitHub Pages](https://docs.github.com/es/pages/quickstart)

```js title="vite.config.js 'base:'"
import {defineConfig} from 'vite';

export default defineConfig({
	base: '/directorio_deaseado/',
	plugins: [] // Se podrian añadir plugins
});
```
