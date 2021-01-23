# Que es la arquitecura hexagonal
Es una arquitectura basada en Clean Architecture
- Capas de la arquitectura hexagonal
    - Infrastructure todo lo que cambie un estado externo evento, consulta, cosas que varia por decisiones externas
    - Application donde van los casos de uso, features, son servicio de aplicacion 
    - Domain todo los que nos interese como regla de negocio, interfaces de dominio servicio de dominio
- Capas de layered architecture donde el dominio conoce a la basede datos y la abrasa donde la aisla a los cambios de la base de datos
    - Presentation
    - Domain
    - Database

**>>** Controller >> Aplication Service >> Models || Services || Respos << Implementation
                                   