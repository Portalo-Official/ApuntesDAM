
## Maven 

## Instalación

GUIA: [Mozilla](https://dev.to/vanessa_corredor/instalar-manualmente-maven-en-windows-10-50pb)

- Tener Java_Home como variable de entorno
- Descargar maven 

## Comandos Básicos

Situándose en el directorio donde está el fichero **pom.xml**, podemos ejecutar cualquiera de los siguiente comandos. Cuando decimos jar, queremos realmente decir el fichero resultado de la compilación y empaquetado, que puede ser jar, war, ear, ...

- *mvn clean*-> Borra todos los .class y .jar generados.
- *mvn compile*-> Compila el proyecto.
- *mvn package* ->Genera el jar.
- *mvn install*-> Lleva el jar a nuestro repositorio local de jars. Queda "visible" para otros proyectos maven en nuestro ordenador.
- *mvn deploy*-> Lleva el jar a nuestro servidor de jars. Queda "visible" para otros proyectos maven en otros ordenadores. Este comando necesita que a maven se le haya indicado dónde está dicho servidor de jars.
- *mvn javadoc:javadoc*-> Genera la documentación javadoc de nuestro proyecto.
- *mvn site*-> Genera documentación html del proyecto. Por supuesto, necesitamos haber escrito en determinados ficheros el contenido de esa documentación.