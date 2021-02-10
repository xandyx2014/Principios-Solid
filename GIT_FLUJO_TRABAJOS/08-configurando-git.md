# Deshaciendo entuertos y rollback y a correr
Si queremos deshacer un commit revert
> git revert -n 0c019...95
- se crea un nuevo commit riviertiendo los cambios del commit seleccionado pero no modifica el historico, el historico de commit sigue manteniiendose
> git reset HEAD~1 --mixed
- se va un paso atras
- desecha el commit y los archivos los ponen el working tree
- desecha el commit pero no lo guarda en el historico de commits
> git reset --hard 
- Quita los commits y quita los archivos del local
- lo saca del working tree
> git reset --soft 
- Quita el commits pero lo los archivos los deja listo para el commit y se puede ver las difeencias entre los archivos
## Detectando por que se hicieron los cambios X
> git bisect start 0gf0 8fj45
> git bisect good
> git bisect bad
> git bisect reset
