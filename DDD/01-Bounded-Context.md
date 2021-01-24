# Como definir Bounded Context

Crear un desarrollo de una especificacion es facil si la especificacion esta congelada
clave para hacer aplicaciones complejas es no hacer aplicaciones complejas
Lo primero que pensamos es dividir
- Frontend
- Backend

Pero Podemos divirlo en


> Mooc y BackOffice pueden estar mismo repositorio o divididos

- Mooc BC* (lo que consume el usuario)
    - Video Module*
    - Courses Mod*
    - ...
    - Students Mod*
- MoocFrontend App*(esta esta fuera del mooc context)
- MoocBackend App*

- Backoffice (lo que administra)
    - Courses Mod*
    - Tickets Mod*
    - ...
    - Students Mod*
- BackFrontend App*(esta esta fuera del Backend context)
- BackBackend App*

- Blog (la parte del blog)

## Alternativas
- Mooc BC*
    - Frontend App*
        - Videos Mod*
        - Courses Mod*
        - Paths mod*
        - ...
    - Backend App*
        - videos Mod*
        - Courses Mod*
        - ...
- Backoffice BC*
    - Frontend App*
    - Backend App*