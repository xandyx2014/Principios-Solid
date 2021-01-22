# Principio de sutitución de Liskov
## Que veremos
- Concepto
    - Si **S** es un subtipo de **T**, instancias de **T** deberian poder sustituir por las instancias de **S** sin alterar las propiedades del programa
- Como:
    - El comportamiento de subclases debe respetar el contrato d ela superclase
- Finalidad:
    - Mantener correctitud para poder aplicar OCP