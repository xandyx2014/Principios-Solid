# Introduccion a las colas de mensajeria
![Message Broker](./img/05.png)
## Tipo de Exchange (Intercambio)
- Fanout: Duplica el evento recibido por cada cola suscrita el exchange
- Direct: Permite define una binding key a la hora de suscribir una cola al exchange
    - Envia evento a la cola si binding key de la cola == routing key del evento
- Topic: Igual que Directo, pero permitiendo wildcards en binding key
## Protocolos de mensajeria
- AMQP: ADvanced Message Queuing protocol
- MQTT: Message Queuing Telemetry Transport
- STOMP: Simple (or Streaming) Text Oriented Message Protocol
- ...