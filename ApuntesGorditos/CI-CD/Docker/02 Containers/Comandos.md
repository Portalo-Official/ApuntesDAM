#docker #comandos

[[comandos-basicos.pdf | CheatSheet de Comandos]]
## Comandos básicos

- `docker version` --> Version de docker en el sistema.
- `docker ps` --> Muestra contenedores encendidos.
- `docker ps -a` --> Muestra todos los contenedores.

### Comandos Imágenes

- `docker images` --> Muestra las imágenes instaladas en el sistema.
- `docker pull [nombre_imagen]` --> Instalar imagen.
- `docker pull [image]:tag` --> Instalar imagen con un tag en concreto (Version), por defecto siempre es la ultima (_latest_).
- `docker rmi [id_imagen]` --> Borrar imagen.
- `docker rmi [nombre_imagen]` --> Borrar imagen. 

### Comandos contenedores

- `docker run [imagen]` --> Crea un container sobre la imagen, si la imagen no esta instalada, también lo hará.
- `docker run --name prueba1 ubuntu` --> Crea container de imagen Ubuntu con el nombre _prueba1_.
- `docker stop [nombre_container]` --> Parar container en ejecución.
- `docker stop [id_container]` --> Parar container en ejecución.
- `docker start [nombre_container]` --> Ejecuta un container ya creado.
- `docker rm [id_container]` --> Borrar container.
- `docker rm [nombre_container]` --> Borrar container. 
## Profundizando

### docker ps

- `docker ps -l` --> Muestra el ultimo que se ejecuto.
- `docker ps -n 4` --> Muestra los 4 últimos.
- `docker ps -q` --> id de los container en ejecución.
- `docker -a -q` --> id de todos los container.
-  `docker -s` --> Cuanto ocupan containers en ejecución, -a -s para todos.

[filtros](https://docs.docker.com/reference/cli/docker/container/ls/#filter)

- `docker ps -f "name=ubuntu"`--> muestra los containers en ejecución con nombre Ubuntu.
- `docker ps -a --filter 'exited=137'` --> Containers con exited con código 137 (aquellos que tuvieron tal error).
- `docker ps -f "ancestor=ubuntu"` -->  Containers en running con la imagen Ubuntu.


