## Propuesta
- 1 exchange por servicio
    - No deberemos añadir infra al crear nuevos eventos
    - Exchange Topic: Permitira filtrar por tipo de evento incluyendo wildcars
    - Ejecutar todos los casos de uso de todos los consumers (no "robar" eventos)
- 1 cola por consumer y evento
    - Optimizacion de coste al consumir solo le tipo mde evento que nos interesa
    -   ejecutar todos los casos de uso los consumers
    - Posiiblidad de reencolar eventos por haber fallado 1 caso de uso concreto
- OCP: Evitar modificar publisher por el hecho de añadir un consumer
## Optimizacion
- 1 cola por consumer y N eventos
    - Siempre y cuando la accion sea unica (actualizar el estado de un usuario)
## Nomenculatura routing keys (atributo typoe del evento)
**codelytv.video.1.event.video.published**
- Empresa
- Nombre del evento
- Version del evento (cambiara si este no rompe la compatilibdad hacia)
- Tipo de mensaje
- Entidad
- Evento
## nomenclaturas colas
- user.notification.notify_user_on_video_published
