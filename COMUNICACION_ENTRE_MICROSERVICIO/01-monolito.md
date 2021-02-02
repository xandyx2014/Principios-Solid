# Comunicacion entre microservicios
## Monolito: uando es un problema
UN solo monolito donde esta todo el codigo donde estan todo el equipo de desarollo,
empieza a ser muy costoso y mucho esfuerzo el monolito
- La base se datos se hace muchas peticiones y empieza a sufrir la base de datos
- Cuando tenemos un pico de trafico los usuarios son afectados
## Recap etapa 1: Al rico Monolito
Benefios si es un sistema pequeño/mediano
- Menos niveles de indereccion
- Añadir nuevas funcionalidades y encontrar bug
Contras:
- Escabilidad infraestructura (cuello de botella)
- Escabilidad aplicacion (mismo recursso y ecosistema apra distinta necesidades)
- Escabilidad equipo de desarrollo (Gestion CVS)
## Alternativa 1:
Microlitos sin infraestructura
- Escabilidad aplicacion (distinto ecosistema y recursos por necesidad)
- Escabilidad equipo de desarollo
- Añadimos niveles de indireccion
## Alternativa 2:
Microlitos por Http
- Los modulos se hacen peticiones Http entre modulos
- Los modulos se pueden sobrecargar
- Escalabilidad infraestructura
- Escalabilidad equipos de desarollo
- Escabilidad implementacion (consumidores condiciones definicion)
- Escabilidad dependiente de otros servicios
- Añadimos latencia de comnicaion entre servicio
- Añadimos niveles de inderrecion
- Independiende del protoclo Http, Websockets, etc
## Circuit breaker: Hystrix
Hystrix una library para Microlitos por HTTP
- Es un Circuit breaker: Evita saturar otros servicios si ya estan caidos
- Caching de resultados
- Monitorizacion y cambios de configuracion en tiempo real
- Concurrencia: Operaciones En batch
- github netflix Hystrix




