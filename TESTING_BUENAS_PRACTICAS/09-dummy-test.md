# Cumpliendo firmas de metodos: Dummy
Dummy Algo que utilizamos  como una prueba  es un Dummy
## SPY
sirve  observar si se ha interracionado con los elementos 
– **Dummy:** Son objetos que se envían, pero nunca se utilizan en el test.
Por ejemplo, imaginemos que tenemos un objeto de la clase GestorDeTareas, que gestiona objetos Tarea, que necesita una lista de parámetros Tarea para funcionar. Si en el test solo queremos comprobar que uno de sus métodos me devuelva el número de Tareas que contiene ese gestor de tareas, podemos utilizar dummies para rellenar el gestor de tareas. Muchas veces los dummies se rellenan con valores NULL.
– Spy: Estos objetos guardan las acciones que se hacen sobre ellos. Hace una especie de seguimiento sobre qué métodos se han llamado y con qué parámetros.
Cuando para que un test sea un éxito no es suficiente ver el estado de los objetos disponibles, podemos usar un spy y comprobar cosas como cuántas veces se ha llamado a un método, qué valores han devuelto, etc. 
Dummy objects  se pasan pero nunca se usan realmente. Por lo general, sólo se utilizan para rellenar las listas de parámetros.

-Fake tienen realmente implementaciones que funcionan, pero suelen tomar algún atajo que los hace no aptos para la producción (una base de datos en memoria es un buen ejemplo).

-Los stubs proporcionan respuestas enlatadas a las llamadas realizadas durante la prueba, normalmente no responden a nada fuera de lo programado para la prueba.

-Los Spy son stubs que también registran alguna información basada en cómo fueron llamados. Una forma de esto podría ser un servicio de correo electrónico que registra cuántos mensajes se enviaron.

-Los mocks son lo que estamos hablando aquí: objetos preprogramados con expectativas que forman una especificación de las llamadas que se espera que reciban.

