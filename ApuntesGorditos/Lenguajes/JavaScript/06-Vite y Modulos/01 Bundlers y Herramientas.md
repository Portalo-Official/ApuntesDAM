
# Bundlers y Herramientas 

Javascript pego el bastinazo en ES6 - ECMAScript 2015. Los navegadores web deben de aceptar las versiones nuevas de javascript a medida que este evoluciona.

ES6 es el mas emblemático:
- Por todas la funcionalidades avanzadas
- La implementación del estándar en todos los navegadores

## Evolución 

Los siguientes estándares : ES2018, ES2019, ES2020... son anuales a partir de 2018 y el problema es que no todos los clientes tienen implementados.

Para estos inconvenientes, se crearon los _Bundlers_ o empaquetadores.

### Bundlers

Nos permite desarrollar una aplicación de javascript moderna:
- Con módulos
- Separando archivos
- Cada archivo con responsabilidad única
- Importación de diferentes tecnologías
- Poder usar distintos estilos de CSS (Sass)

Todo ello acabando en un resultado final listo para producción. 

![[bundler.png]]

También podemos escribir con javascript moderno y después transformarlo a cualquier version que queramos de js.

El bundler mas popular durante muchos años fue [webpack](https://webpack.js.org), todavía es muy usado.

webpack tiene plugins para:
- Transpilar aplicaciones
- Usar CSS
- Minimizar
- Levantar servidores en tiempo real

[[00 Angular Instalación índice|Angular]] usa como bundler por defecto webpack.

El tiempo de webpack se esta pasando, la velocidad de webpack impide que se pueda generar código mas rápidamente.

[[02 Vite|Vite]] es un bundler mas rápido que webpack y será el que se use.

Decir que webpack es una version muy antigua y el predecesor de este es [Tubopack](https://turbo.build/pack), que lo usa [[Next.js Puntos de estudio|Next.js]] version 13 y muestra grandes resultado, mas que vite. 

Este ultimo aun no esta en un punto listo par aplicaciones de producción (2022).
