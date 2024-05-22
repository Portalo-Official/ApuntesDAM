Fuente: 
- [Multi-Module Project](https://www.baeldung.com/maven-multi-module)
- [Bill Of Materials BOM](https://www.baeldung.com/spring-maven-bom)
- [Spring Boot Multi-Module](https://www.baeldung.com/spring-boot-multiple-modules)
- [Spring Boot multi-module-project](https://www.geeksforgeeks.org/spring-boot-multi-module-project/)


El enfoque de trabajo del proyecto que se ha optado por tener un solo repositorio que contendrá todos los demás microservicios de spring, para gestionar las dependencias y todo lo que sea común entre ellos.

A nivel de despliegue, este repositorio deja de tener sentido porque no es un ejecutable, dentro de él tiene mas módulos que son los microservicios y cada uno de ellos generan un JAR que serán independientes de los demás. 


![[Pasted image 20240515212443.png]]

El repositorio principal contiene otros dos: negocio e infraestructura. 

El proyecto de _negocio_ contiene toda la parte que tiene que ver con la lógica del negocio de la aplicación, el estarán incluidas la librerías o dependencias que son comunes en estos microservicios.
- Spring Web
- SpringData (en nuestro caso todas las bbdd son posgrest)

El proyecto _infraestructura_ tienen un grupo de microservicios que se van a encargar de la parte que tiene que ver con la infraestructura de microservicios. Son microservicios que implementan funcionalidades comunes para todos los otros microservicios del dominio del negocio. En este paquete, van incluidos las dependencias comunes a estos microservicios.
- Spring Cloud
## Crear un proyecto padre en Eclipse

Crear un proyecto padre para englobar a los demás microservicios.

El proyecto padre, es el proyecto general que contiene los microservicios y por lo tanto todas las dependencias que tenga este las heredan los módulos hijos (en este caso los microservicios).

Crear un _Maven Project_ en eclipse, para los arquetipos buscamos maven-archetype-quickstart y elegimos las versión 1.4 (recomendada en su [web](https://maven.apache.org/archetypes/maven-archetype-quickstart/)).

![[Pasted image 20240515225238.png]]

### Limpiar recursos por defecto

Una vez creado el proyecto hacemos lo siguiente:

1. Borramos la carpeta src, pues este proyecto no tendrá código, solo los módulos que pertenecen a los microservicios.

2. Limpiar el pom.xml
	1. Quitar tag url
	2. Cambiar version de java (por defecto 1.7)
	3. Limpiar tag dependencies
	4. Limpiar tag build

![[pom.xml-limpio.png]]

### Rellenar pom.xml

Poner los plugins en el tag build que utilice Spring  (en su ultima version)

```xml title='Plugins de Spring'
<build>
	<pluginManagement>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
				<version>3.2.5</version>
			</plugin>
		</plugins>
	</pluginManagement>
</build>
```

Indicar el modo de empaquetado con el tag `{xml}<packaging>pom</packaging>`

![[pom-padre-modificado.png]]

Indicar que Spring Framework es el padre de este proyecto, ya que todos los microservicios heredarán de Spring Framework.

![[Pasted image 20240515232035.png]]
## Crear Módulos hijos



![[Pasted image 20240515230832.png]]





## Como heredan los hijos

### Heredar dependencias
Con la etiqueta `<dependencyManagement>` en el archivo `pom.xml` del proyecto Maven 'Planealo', se utiliza para centralizar y definir versiones y configuraciones de dependencias que pueden ser utilizadas por los submódulos de este.

Propósito de `<dependencyManagement>`

1. **Centralización de Configuración:**
    
    - Permite centralizar la configuración de dependencias en el proyecto padre para que los submódulos hereden estas configuraciones sin necesidad de redefinirlas.
2. **Definición de Versiones:**
    
    - Al definir las versiones de las dependencias en el proyecto padre, todos los submódulos utilizarán las mismas versiones, evitando incompatibilidades y problemas de mantenimiento.
3. **Evita Redundancia:**
    
    - En lugar de repetir la versión de una dependencia en cada submódulo, la versión se define una sola vez en el proyecto padre.
4. **Coherencia y Control:**
    
    - Proporciona un punto central de control sobre las versiones de las dependencias utilizadas en todo el proyecto. Esto asegura la coherencia y facilita la actualización de versiones.

Fragmento del pom.xml del Repositorio modulo _Planealo_:
```xml title='Gestionar herencia de las dependencias'
<dependencyManagement>     
	<dependencies>
		<dependency>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-dependencies</artifactId>
		<version>3.2.5</version>
		<type>pom</type>
		<scope>import</scope>
		</dependency>
	</dependencies>
</dependencyManagement>`
```

De esta forma indicamos que los hijos tienen que importar el pom del proyecto _org.springframework.boot_, para tener la gestión de versiones de las dependencias propias de spring boot, asegurando __coherencia y compatibilidad__ en el proyecto.

`{xml}<type>pom</type>` -> Indica que la dependencia es un archivo POM. donde describe que versiones utilizar sobre otras dependencias de spring boot.

`<scope>import</scope>`-> Indica que se importe dicho pom de _spring-boot-dependencies_.
#### Resumen

El bloque `<dependencyManagement>` en el `pom.xml` del proyecto padre es crucial para gestionar las versiones y configuraciones de dependencias en un proyecto multi-módulo. Proporciona un punto central de control, asegura la consistencia de versiones y simplifica el mantenimiento.

### Heredar la configuracion de Plugins Maven

`<dependencyManagement>` en el `pom.xml` del proyecto padre es crucial para gestionar las versiones y configuraciones de dependencias en un proyecto multi-módulo. Proporciona un punto central de control, asegura la consistencia de versiones y simplifica el mantenimiento.