# Principio de responsabilidad Unica
## Que entendemos por SRP?
- Concepto:
    - Una clase = Un concepto y responsabilidad
    - Una clase deberia tener solo 1 razon para cambiar
- Como:
    - Clases de servicios pequeñas con objectivos acotados
- Finalidad
    - Alta cohesion (Que esten juntos) y robustez
    - Permitir composicion de clases
    - Evitar duplicidad
## Niveles de granularidad
- Order | user
    - Son modelos de dominio, no servicio
- OderAnalyzer | OrderProcessor | OrderService
    - Terminos genericos llevan a mas de 1 responsablidad
- OrderTrustabilityChecker | OrdernMarginCalculator son buenos nombres
- EJEMPLO: Conexion de base de datos en clase de obtencion de datos

```java
class Book {
    public String getTitle() {
        return "A great book";
    }
    public String getAuthor() {
        return "John Doe";
    }
    public void printCurrentPage() {
        // System.out.println("Current page");
        return "current page content";
    }
}
interface Printer
{
    public void printPage(String page);
}
final class StandartOutputPrinter implements Printer
{
    public void printPage(String page)
    {
        System.out.println(page);
    }
}
final class Client
{
    public Client() {
        Book book = new Book(...);
        book.printCurrentPage();
    }
}
```
