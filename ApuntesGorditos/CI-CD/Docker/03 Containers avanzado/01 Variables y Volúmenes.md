

## Variables de entorno

Son muy utilizadas para ciertas configuraciones a la hora de levantar containers.

Para declarar una variable de entorno se usa _-e_ .

Ejemplo: Para levantar un container de una base de datos en postgres, usaremos la variable de entorno para poner la contraseña de la bbdd.

`{bash}docker run -e POSTGRES_PASSWORD=mysecretpassword -d postgres`

## Volúmenes

Almacenamiento donde persistir los datos o archivos que necesita o genera un contenedor.

`docker volume ls` --> Lista todos los volúmenes presentes en nuestro docker.
`docker volumen rm [name]` --> Elimina un volumen
`docker volumen prune` --> Elimina todos los volúmenes que no están en uso.

### Volúmenes en directorios

al crear un contenedor podemos asignar un directorio de nuestro equipo como volumen y mapearlo a algún directorio o ruta del contenedor.

``` title='Container para aplicacion nest.js'
docker container run `
--name nest-app `
-w /app `
-dp 8087:3000 `
-v ${pwd}:/app `
node:18-alpine3.18 `
sh -c "yarn install && yarn start:dev"
```

El siguiente fragmento de código levanta una aplicación de nest.js del lado del container y nosotros podremos verlo a partir del puesto 8087. Para ello se necesitaría la aplicación (parte no proporcionada aquí).

La línea 5 `-v ${pwd}:/app` asignara el directorio actual en el que este la terminal como volumen y el contenido de esta lo tendrá presente el contenedor en su ruta `/app`.

