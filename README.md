# HackOn-Workshop

Material del taller [**Introducción al Hardening Linux**](https://hackon.es/talleres/Alejandro_y_Javi.html) impartido el 16 de Febrero de 2023 en #HackOn2023, la 5ª edición de la conferencia [HackOn](https://hackon.es/).

## Introducción :wave:

En este taller se muestra la importancia de la securización de entornos Linux, y se introduce a los asistentes en el desarrollo de tests de bastionado con la herramienta [Lynis](https://github.com/CISOfy/lynis) y scripts de hardening con la herramienta de automatización [Ansible](https://www.ansible.com/).

Las diapositivas utilizadas como hilo conductor del taller se encuentran en [hardening_linux_hackon2023.pdf](https://github.com/R00tedSec/HackOn-Workshop/blob/master/hardening_linux_hackon2023.pdf).

## Pasos del taller :scroll:

1. Presentación de los ponentes
2. Introducción al bastionado de sistemas y por qué es importante
3. Arquitectura del laboratorio preparado, consistente en una máquina virtual vulnerable en la que se ejecutarán los tests y que será bastionada
4. Puntos de control que se van a verificar y bastionar: el propio sistema operativo Linux, y los servicios `ssh` y `apache`.
5. Desarrollo de los tests de hardening, incluyendo distintos ejemplos, y ejecución de los mismos
6. Desarrollo de los scripts de hardening y ejecución de los mismos para bastionar los puntos de control
7. Ejecución de los tests de nuevo para comprobar que se han resuelto los aspectos que daban error previamente
8. Presentación de una posible solución desarrollada por los autores

## Material del taller :hammer_and_wrench:

- 3 scripts de Lynis preparados para que desarrollen tests que comprueben el estado del hardening.
    - Dichos scripts, con las soluciones incluidas, se pueden encontrar en el directorio [lynisHackOn/include/](https://github.com/R00tedSec/HackOn-Workshop/tree/master/lynisHackOn/include) bajo los nombres `tests_apache`, `tests_linux` y `tests_ssh`.
- 3 ficheros de *tasks* de Ansible preparados para que desarrollen los pasos que modifiquen las configuraciones y solucionen los problemas de seguridad.
    - Dichos ficheros, con las soluciones incluidas, se pueden encontrar en el directorio [ansibleScripts/hardeningScripts/](https://github.com/R00tedSec/HackOn-Workshop/tree/master/ansibleScripts/hardeningScripts) bajo los nombres `apache.yml`, `linux.yml` y `ssh.yml`. Estos ficheros se ejecutan desde el Playbook de Ansible, denominado [`ansibleHardening.yml`](https://github.com/R00tedSec/HackOn-Workshop/blob/master/ansibleScripts/ansibleHardening.yml).
- [1 máquina virtual Ubuntu 22.04 LTS en formato OVA (VirtualBox)](https://gofile.io/d/gdmVpx) con Ansible instalado y servicios vulnerables sin hardenizar.

### Ejecución de Lynis :rocket:

Para ello, es necesario situarse en el directorio en el que se encuentra el ejecutable de Lynis, proporcionado en este mismo repositorio, y lanzarlo:

```sh
cd lynisHackOn
./lynis audit system
```

### Ejecución de Ansible :rocket:

Para ello, es necesario situarse en el directorio en el que se encuentra el Playbook de Ansible `ansibleHardening.yml` y ejecutar el comando [`ansible-playbook`](https://docs.ansible.com/ansible/latest/cli/ansible-playbook.html):

```sh
cd ansibleScripts
ansible-playbook ansibleHardening.yml --check # Check mode, don't make changes
ansible-playbook ansibleHardening.yml # Normal mode
```

### Para saber más :wave:

* Repositorio [Hardening a Server](https://github.com/Kaputt4/hardening_server), con un playbook de Ansible ejecutado desde GitHub Actions.

## Autores :busts_in_silhouette:

* **Javier Sánchez** - [`@Javi_sanchez04`](https://twitter.com/javi_sanchez04)
* **Alejandro Bermejo** - [`@R00tedSec`](https://twitter.com/r00tedsec)
