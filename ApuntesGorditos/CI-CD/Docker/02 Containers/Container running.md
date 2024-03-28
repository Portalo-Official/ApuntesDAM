## Contenedores en Ejecución

Para ejecutar un contenedor y que este se mantenga y no se pare, hay 2 opciones:

- Contenedores interactivos.
- Contenedores en Background.
### Contenedores interactivos

Con los comandos _docker run -i_ y _docker run -t_ se ejecutará el containers y quedara en estado running y modo interactivo (consola con la que podemos trabajar con el).

- `docker run -i [container]` --> Modo interactivo.
- `docker run -t  [container]` --> Abre una terminal virtual (tty).

###### Combinación de parámetros

- `docker run -it ubuntu` --> Ejecuta un container dejando una terminal para interactuar con el.

![[container-interactivo.png | 500]]

Una vez creado el container, esta operativo la terminal de este.

Sin cerrar esta terminal, abrimos otra y ponemos `docker ps` para verificar que esta corriendo de verdad.

![[verificar-container-intercativo.png]]

### Container en Background

La mayoría de veces se ejecuta en background. Pues se quiere interactuar el contenedor sin tener una terminal de este activa.

Con uso de -d, de detach  (despegar, dividir), el container se ejecuta y se mantienen en estado running.

- `docker run -d ubuntu` --> container en running sin terminal abierta.

No todos los containers funcionan en background, necesitan estar preparados, por ejemplo la imagen fedora no esta preparado para trabajar en background.

