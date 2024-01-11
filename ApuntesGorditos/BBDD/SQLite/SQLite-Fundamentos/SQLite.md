
# Que es

SQLite es un sistema de gestión de bases de datos relacional *basado en archivos*.

- Es una biblioteca C que proporciona un motor de base de datos SQL
- Sin servidor
- De código abierto. 

A diferencia de los sistemas de gestión de bases de datos tradicionales, SQLite no funciona como un proceso independiente, sino que se incorpora directamente en la aplicación, lo que lo hace ligero y fácil de integrar en proyectos. SQLite es ampliamente utilizado en aplicaciones móviles, sistemas embebidos y proyectos que requieren una base de datos compacta y eficiente.

## Ventajas

- No necesita configuración: Puertos, usuarios u otros parámetros.
- Seguridad: Crea un archivo para todo el esquema de la base de datos. es una bbdd local y no puede ser accedido por agentes externos.
- Rendimiento: Operaciones rápidas y eficaces (más que MySQL)
- SQL: implementa gran parte de los comandos SQL estándar, subconsulta, generación de usuarios, views y triggers. 
- Código Abierto: No es de pago.
# Instalación

Para tener en Windows SQLite basta con descargar un bundle en la pagina de descargas de [SQLite](https://www.sqlite.org/download.html)

Se elegirá el sqlite-tools-win-x64:

![[descargar.png]]

Una vez descargado s e descomprime. Este tendrá varios archivos ejecutables.

Es recomendable dejarlo en una carpeta dentro de C: , y agregar la ruta como variable de entorno:

![[variable de entorno.png|500]]

En en ejemplo se deja el nombre por defecto, esto es a gusto, pero esos números nos indican que version del paquete se ha descargado.

Una vez hecho esto podemos comprobar en consola:

![[sqlite-version-consola.png|500]]


# Descarga de IDE para SQLite

Para descargar un IDE de forma gráfica, este será [DB Browser SQLite](https://sqlitebrowser.org/).

Se puede descargar tanto el instalador como el comprimible en .zip

Si se descarga el imprimible, es recomendable guardarlo donde guardas también el sqlite-tools-win-x64. Crear un acceso directo del ejecutable DB Browser for SQLite.








