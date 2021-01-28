# Introduccion CQRS
- Destionado a aplicaciones de gran carga de rendimiento
- para grandes equipos que quieran trabajar de manera centralizado

# ¿ Que es un Command?
Existen dos command , Uno del patron del diseño, Otro del CQRS
Son DTO (Data Trannsfern Object) que tiene sus propiedades representa una accion, los comandos no devuelve algo
- Solo Sirve para Transferir Datos de un Punto A  (Infraestructurura) a un Punto B (Bus)
- El command solo tiene datos porq para serializar los datos en la transaccion
- Son inmutables porque una vez construimos la instancia del command lo modificamos
- Sirve para Side Deffects sirve para modificar crear, ponmer en cola pero no devuelve nada
- Puede abarcar todo aquel que cambia el estado, CREAR , ACTUALIZAR
- Existen Command Sync, Async (para procedimiento costosos)

```php
final class CreateVideoCommand extends Command
{
    private $id;
    private $title;
    private $url;
    private $courseId;
    public function __construct(
        Uuid $commandID,
        string $id,
        string $title,
        string $url,
        string $courseId
    ) {
        parent::__construct($commandID);
        $this->id       = $id;
        $this->title    = $title;
        $this->url      = $url;
        $this->courseId = $courseId;
    }
    // getter
    public function url()
    {
        return $this->url;
    }
}
```
# ¿ Que es un Query?
Estas pidiendo algo solicitando ando que devuelve algo
Una query solo debe consular y no modificar o crear
La query por ejuemplo cuando vemos un video de youtube que crea un contador por cada vista que ha tenido,
Seria mejor crear un query para solicitar video y un Command Para Aumentar el contador del video


Ejemplo de una Query
```php
interface Query
{

}

final class FindVideoQuery implements Query 
{
    private $id;
    public function __construct(string $id)
    {
        $this->id = $id;
    }
    public function id(): string
    {
        return $this->id;
    }
}
```