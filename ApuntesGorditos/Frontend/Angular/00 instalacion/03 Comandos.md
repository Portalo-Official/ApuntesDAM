Una vez instalado [[02 Paquete @angular_cli]]
# Comandos
siguiendo los comandos de [[angular-cheat-sheet.pdf]], vamos a perfilar parámetros

## No generar archivos

Para evitar generar archivos adicionales al crear un componente como los tests o los CSS.

`--skip-tests` --> Para no generar los tests.
`--inline-style` --> Para no generar los archivos CSS.

## Ruteo

`--routing` --> Al generar un modulo podemos añadir un archivo de ruteo
`--module app --route products` --> Para añadir el lazyRouting en el modulo principal siendo `app` el modulo principal (Cambiar según el nombre).