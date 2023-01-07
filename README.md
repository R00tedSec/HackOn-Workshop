# HackOn-Workshop

## IDEA
La idea es que los alumnos del workshop aprendan a crear tests de hardening en lynis y posteriormente fixes que los apliquen.


## Pasos del taller
1. Se les hace una presentacion sobre el hardening linux y la importacia
2. Se les enseña un diagrama con las dos maquinas que van a usar
3. Se les explican los puntos a comprobar y se empiezan a programar los tests
4. Se lanzan los tests en la maquina vulnerable
5. Se desarrollan los scripts de ansible que solucionen los fallos de seguridad
6. Se lanzan los scripts de ansible
7. Se vuelven a lanzar los tests y comprobamos que se ha solucionado los errores de seguridad.

## Material que se les entrega
- Se les proporciona 3 scripts de lynis preparados para que desarrollen tests que comprueben el estado del hardening.
- Se les proporciona 3 scripts de ansible preparados para que desarrollen los pasos que modifiquen las configuraciones y solucionen los problemas de seguridad.
- 1 maquina ubuntu 22.04 con ansible instalado
- 1 maquina ubuntu 22.04 con ssh, apache y linux con configuraciones inseguras que deben solucionar.


## To Do
- Terminar de preparar los tests -> con solucion y sin solucion
- Preparar scripts de ansible -> con solucion y sin solucion
- Preparar diapositivas
- Preparar maquinas virtuales.
