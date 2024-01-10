



# ### Patrón de software  DAO - DTO

Fuente: [Patrón de software](https://rjcodeadvance.com/patrones-de-software-que-es-patron-de-diseno-parte-2/)
Fuente: [Blog interesante](https://www.oscarblancarteblog.com/2018/11/30/data-transfer-object-dto-patron-diseno/)
Fuente: []()

Es un patrón de software para el acceso y transporte de los datos.

![[dao_structure.jpg]]


#### DAO

Data Access Object es la clase destinada a la implementación para obtener los datos de la base de datos.

Crearemos una Interface GenericDAO Genérico que marcara el comportamiento mínimo que hacen todos nuestros DAOs:

```c# title='GenericDAO'
public interface GenericDAO<T, ID>
{
    Response create(T entity);
    T read(ID id_entity);
    Response update(T entity);
    Response delete(ID id_entity);
    List<T> findAll();
}
```

[[04 Response y Request|Response]] es la clase que veremos en la siguiente hoja. 

Después se crearan las interfaces DAOs de cada tabla extendiendo de GenericDAO

```C# title='ITemaDAO'
public interface ITemaDAO : GenericDAO<DTO_Tema,int>
{
    // Aqui podran implementarse cosa mas singulares de Temas
    // Ej getTemasByAutor , auqnue haya que liar los libros por medio
}
```

Una vez hecho estas herencias de interfaces, podríamos cambiar entre las distintas implementaciones como TemaDAOMongoDB, TemaDAOFichero.

En nuestro caso implementaremos TemaDAOMySQL.



#### DTO

Fuente: [Video DTO](https://www.youtube.com/watch?v=4p6z6hL8BNg)




#### Mapper

Fuente: [AutoMapper](https://bravedeveloper.com/2021/12/24/aplicando-el-patron-dto-y-mapeando-objetos-con-automapper-en-un-web-api-con-net-core/)
Fuente: [Video AutoMapper](https://www.youtube.com/watch?v=pr_pemcmVAs)

