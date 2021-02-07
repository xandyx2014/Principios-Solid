# otros paradigmas de testing: Mutantion y property based testing
## Mutation testing
```java
final class Calculator {
    public int sum(Integer a, Integer b) {
        return a + b;
    }
}
final class CalculatorShould {
    void sum_two_integer_numbers() {
        final Calculator calculator = new Calculator();
        calculator.sum(3, 4);
    }
}
```
- Aqui Obtenemos full coverage
- Mutar nuestro estado cambiar el **a + b** a **a - b** deberia de no pasar la prueba y deberia fallar
- Matar los mutantes que genera la library de tests
- Tenemos un mutante ya que cambiamos **a - b** ya que el codigo logicamente no pasa
## Property-based testing
Se basa en testear las propiedades de nuestros datos
- basarse en los requisitos de nuestra propiedades
- que nuestras propiedades sigan nuestra regla de negocio o de integridad
- ejemplo que el video tenga un limite de tiempo, la maxima cantidad de subscriptores
- determinamos las caracteristicas, particulares de cada propiedad definida por la logica de negocio