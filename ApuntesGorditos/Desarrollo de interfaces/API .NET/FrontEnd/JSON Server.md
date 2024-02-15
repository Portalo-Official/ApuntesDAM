#BackEND #BackEdnDev #JSON
# JSON server

Es un servidor que nos permite hacer muchas cosas simulando que estamos conectados a una BBDD real estando en *Desarrollo*.

Fuente: [Descarga NPM](https://www.npmjs.com/package/json-server)

Con JSON Server se pueden hacer paginaciones, filtros, ordenaciones... 

Instalación para desarrollo:

`{bash}npm i --save-dev json-server`

## Base de datos

La base de datos sera una archivo json con todos los registros recogidos

```json title="bd.json"
{
"temas":[
	
]

}
```

Una vez instalado podemos poner en el package.json un script para   