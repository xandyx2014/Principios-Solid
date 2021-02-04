# Introduccion
## Que es un test
## Test unitarios
```php
// PHP
public function it_should_return_fizz_for_multiples_of_3()
{
    $this->assertEquals('fizz', FizzBuzz::calculate(3));
}
```
```js
// JEST
test('return fizz for multiples of 3', () => {
    expect(fizzbuzz(3)).toBe('fizz');
});
```
## Test aceptacion
```
Feature: Api status
    In orde to know the server is up and runnning
    As a health check
    I want to check the api status
    Scenario: Check the api status
    Given I send a GET request to "/status"
    Then the response content should be:
    """
    {
        "status": "OK"
    }
    """
```
## Pipeline CI
- Jenkins
    - Se puede crear pipeline una serie de pasos para hacer la build
- Circle
- Travis
## Porque?
- ✅Evidencia empirica de que el software funciona como esperamos
- Reproducir facilmente csaso complejos
- Evitar Bugs
- Refactorizar y añadir funcionalidades en paz
- Explorar funcionalidades

> "A la gente no le importa la calidad hasta que les cuesta dinero"