# ¿Que entendemos como unidad en nuestros tests unitarios? Subject Under Test
## Haz tu tests mas legibles
- Aportando semantica ya sea con nombre verbosos
- Se puede usar Patron builder para ser mas semanticos para los TEST
    - El coste de mantenimiento del patron builder empieza a crecer 
- Object Mother donde los primitivos se convierten en ValueObject donde se puede colocar validaciones en estas, donde Podemos crear un **UserStub**
- name Arguments  si tiene el lenguaje se podria usar  pero no todos los lenguajes los soportes
- function params
### Object Mother
El patrón ObjectMother, que consiste en tener una clase encargada de proporcionarnos instancias de distintos objetos que usamos frecuentemente en los tests, es decir, una factoría de objetos pensados concretamente para nuestros tests.
```java
public class ObjectMother
{
    public static readonly User Lucas
    {
        get { return new User("Lucas", "lucas@gmail.com", Role.User); }
    }
 
    public static readonly User Admin
    {
        get { return new User("Lucas", "lucas@gmail.com", Role.Admin); }
    }
}
```

- La principal limitación de este patrón es que si necesitamos construir objetos con diversas características (un cliente de Madrid, otro de Segovia, uno preferente, otro que haya excedido el riesgo, etc.), la clase que hace de ObjectMother empieza a ser un lío y acabamos acoplando unos tests a otros indirectamente a través del ObjectMother.

### Patron Builder
El patrón Builder es más flexible que ObjectMother y todo lo que se puede conseguir con ObjectMother se puede hacer también con un Builder, pero requiere más código y es más complejo de implementar, por lo que hay casos en que no merece la pena.

### Creation Methods
La alternativa que más utilizo actualmente para construir objetos en los tests son los métodos de creación. La idea es encapsular la creación y configuración de objetos auxiliares en un método dentro de la propia clase de test.
Por ejemplo, si estamos testeando un filtro sobre productos en base a la categoría a la que pertenecen y el nombre del producto, esos son los únicos datos que nos interesan y podríamos tener un método así:
```java
private Product Product(string category, string name)
{
  var category = new Category(category);
  var tax = ObjectMother.Tax1;
  var product = new Product(name, tax);
  product.Category = category;
  return product;
}
 
[Test]
public void Filters_Products_By_Full_Text_Search()
{
  var products = new[]
  {
    Product("Ropa", "Camiseta"),
    Product("Ropa", "Pantalón"),
    Product("Menaje", "Copa"),
  };
 
  var result = products.Filter("opa");
  Assert.That(result.Length, Is.Equalto(3));
}
```

- Si vamos por la vía de usar muchos parámetros, tendremos el problema de perder legibilidad en el test cuando tengamos varios parámetros del mismo tipo:
A veces para solventar esto se introduce un parameter object para agrupar los parámetros y poder ponerles nombre. Esto incluso permite aplicar el patrón builder al parameter object para no tener que indicar todos los parámetros si no son necesarios:
```java
[Test]
public void Some_Invoice_Test()
{
  var invoice = Invoice(
    Customer("Paco").Discount(0.1m),
    Product("Paraguas").Price(4),
    1m,
    2.5m);
  // ...
}
```
## Como evitar test lentos y acoplados: Fakes, Stubs y Mocks
- *Fakes* una implementacion falsa de algo de verdad puede ser como crear una implementacion falsa de **UserReporsitory** llamada **InMemoryUserRepository** para evitar la llamada a la base de datos, se utilzaria para ver sus funcionamento del repository, replicando la logica del repositorio
```java
final class InMemoryUsersRepository implements UsersRepository {
    private Map<Integer, User> users;

    public InMemoryUsersRepository(Map<Integer, User> users) {
        this.users = users;
    }
    @Override
    public Optional<User> search(Integer id) {
        return Optional.ofNullable(users.get(id));
    }
}
```
- **Stubs** es lo mismo que un fakes solo que ya viene con valores predefinidos para moldear el caso que queremos testear
```java
final class CodelyTvStaffUsersRepository implements UsersRepository {
    private Map<Integer, User> users = Collections.unmodifiableMap(new HashMap<Integer, User>() {
        {
            put(UserMother.RAFA_ID, UserMother.rafa());
            put(UserMOther.JAVI_ID, UserMother.javi());
        }
    });
    @Override
    public Optional<User> search(Integer id) {
        return Optional.ofNullable(users.get(id));
    }
}
```
- Mocks falsear el resultado con los los valores que queremos

