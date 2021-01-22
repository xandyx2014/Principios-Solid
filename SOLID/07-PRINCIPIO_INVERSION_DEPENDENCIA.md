# Principio inversion de dependencias
- Concepto:
    - Modulo de alto nivel no deberia depende de los de bajo nivel. Ambos deberian depende de abstracciones,
- Como
    - inyectar depedencias (parametros recibidos idealmente en constructor)
    - depende de las interfaces de estas dependencias y no d elas implementaciones concretas
    - LSP como premisa
Finalidad
    - Facilitar la modificacion y substitucion de implementaciones
    - Mejor testabilidad de clases