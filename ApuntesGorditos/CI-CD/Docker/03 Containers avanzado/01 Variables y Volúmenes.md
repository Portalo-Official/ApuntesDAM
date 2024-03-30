

## Variables de entorno

Son muy utilizadas para ciertas configuraciones a la hora de levantar containers.

Para declarar una variable de entorno se usa _-e_ .

Ejemplo: Para levantar un container de una base de datos en postgres, usaremos la variable de entorno para poner la contraseña de la bbdd.

`{bash}docker run -e POSTGRES_PASSWORD=mysecretpassword -d postgres`

