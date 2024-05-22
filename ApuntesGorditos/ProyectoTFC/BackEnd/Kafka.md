## Que es kafka


### Zookeeper

-> Recurso que Kafka utiliza para poder funcionar correctamente.



## Iniciar Kafka

### Configurar para Windows

Zookeeper por defecto necesita SO Linux, por lo tanto tenemos que configurarlo para Windows.

1. Ir a la carpeta _config_ y abrir el archivo server.properties
	- Buscar _log.dirs_ -> poner la ruta de la carpeta de kafka. Aquí se guardarán los logs de kafka
2. Ir config > zookeeper.properties 
	- Buscar _dataDir_ -> `dataDir=c:/Kafka/zookeeper-data`

![[serverproperties-kafka.png|600]]

![[zookeeperproperties-kafka.png]]


### 🔶 Comandos Zookeeper y Kafka: 

- Ir al directorio descomprimido de kafka.

-  Iniciar Zookeeper
	- `.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties` 

-  Iniciar Kafka 
	- `.\bin\windows\kafka-server-start.bat .\config\server.properties 

-  Crea un nuevo topic en el servidor de kafka 
	- `.\bin\windows\kafka-topics.bat --create --topic {topic-name} --bootstrap-server {host}:9092` 

- Describir los detalles de un topic 
	- `.\bin\windows\kafka-topics.bat --describe --topic {topic-name} --bootstrap-server {host}:9092 `

-  Listar todos los topics que existen dentro del broker 
	- `.\bin\windows\kafka-topics.bat --list --bootstrap-server {host}:9092`

-  Inicia una consola para ver mensajes de un topic específico 
	- `.\bin\windows\kafka-console-consumer.bat --topic {nombreTopic} --bootstrap-server {host}:9092`

-  Inicia una consola para enviar mensajes a un topic específico
	- `.\bin\windows\kafka-console-producer.bat --broker-list {host}:9092 --topic {topic-name}`

