
# SQLiteOpenHelper

Android se comunicara con cualquier BBDD SQLite con la clase SQLiteOpenHelper.

Esta clase nos permite hacer CRUD de registros, crear eliminar tablas, procedimientos almacenados.

## Métodos Básicos

SQLiteOpenHelper cuenta con dos métodos básicos, el cual son el OnCreate() y el OnUpgrade().

### OnCreate()

Se ejecuta por primera vez que creamos la base de datos, ya que es aquí, donde creamos los datos.


### OnUpgrade()

Este método es utilizado cuando se quiere hacer una modificación sobre la estructura de la base de datos.

- Agregar nuevas tablas.
- Añadir Columnas nuevas.
- Cambiar todo el esquema de la base de datos.




