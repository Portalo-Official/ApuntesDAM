
# MapStruct

## Introducción

MapStruct es una biblioteca de mapeo de objetos en Java que facilita la conversión entre diferentes tipos de objetos. Utiliza anotaciones y genera implementaciones en tiempo de compilación, lo que mejora el rendimiento al eliminar la necesidad de reflexión en tiempo de ejecución. Esto hace que MapStruct sea una herramienta ideal para proyectos que requieren mapeo de objetos eficiente y mantenible.

## Instalación

Su instalación se puede hacer mediante descarga de su binario o gestor de dependencias como maven o gradle.

Enlaces: 
- [Pagina Principal](https://mapstruct.org/)
- [Instalación](https://mapstruct.org/documentation/installation/)
- [Blog ArquitecturaJava](https://www.arquitecturajava.com/java-mapping-con-mapstruts-y-anotaciones/)  
- [Blog ParadigmaDigital](https://www.paradigmadigital.com/dev/mapstruct/)
 
## Implementación

La versión 1.5.5.Final es una de las mas estables de 2023 y tiene resueltos muchos bugs. Esta versión viene con anotaciones.

- _@Mapper_ -> de _org.mapstruct.Mapper_, anotación para las interfaces donde se mapeará, en el indicamos en que entorno esta actuando este mapper.
- @MapperConfig

### @Mapper

Con @Mapper indicamos como MapStruct inyecta en el mapper en el contexto de nuestra aplicación. 

Es un parámetro esencial para integrar MapStruct en diferentes frameworks. Valores comunes para la configuración:

- _componentModel_: Con este parámetro indicamos en que entorno estamos y donde debe inyectar el mapper, en nuestro caso es Spring. Para ello, hay diferentes constantes para indicar el entorno. 

![[interface-mapper.png]]

### Métodos para mapeo

Para mapear, MapStuct lee los atributos del objeto origen y del objeto destino, si hay alguna incoherencia, tirará error o te avisara el IDE con el que trabajes.

En este ejemplo UsuarioDTO tiene el atributo ref, pero la clase usuario tiene el nombre de referencia, como son distintos nombres, MapStruct salta un warning de que no se puede mapear ref.

@Mapping --> Configura lo necesario para llevar a cabo el mapeo, en este caso usamos source y target para indicar que esos atributos serán los que se tienen que mapear entre ellos. source para Usuario y target para UsuarioDTO.

```java title='Metodo para mapear'
@Mapper(componentModel = MappingConstants.ComponentModel.SPRING)
public interface UsuarioMapper {

@Mapping(source = "referencia", target = "ref")
UsuarioDTO entityToDTO(Usuario usuario);

}
```


