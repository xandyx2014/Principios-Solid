# Gestionar errores de eventos
## Eventos Desordenados
- Definiar numero maximo de reintentos apra evitar bucles infitos
- Encolar en dead letter para no perderlo, cola encargada de almancer los eventos
- La aplicacion es responsable de esta logica
## Eventos duplicados
- Let it crash (dejar que el evento duplicado acabe en la dead letter)
- Mantener registro de los identificadores de eventos ya procesados
    - No eliminariamos problemas al 100% (Concurrencia)
- Idempotencia (Saber )
    - Complejo al gestionar datos de forma agregada (ejemplo: contadores)