# Ejercicio CiberKillChain - Defensa

## Alumno

Marcelo García

## Enunciado

Mitigar una cyberkillchain usando técnicas de la matriz de Att&ck para un escenario relacionado a tu trabajo práctico

### Command and control

Una vez informado al atacante las credenciales para el acceo remoto, el atacante toma el control del servidor.
UNa vez tomado el control no hay posibilidad de mitigación automática.

### Actions on objectives

Una vez obtenido el acceso al servidor el atacante destruye los datos presentes en el servidor dando de baja el servicio. https://attack.mitre.org/techniques/T1485/ 
Previo al borrado de informaciòn accede a credenciales de AWS y se copia en la instacia EC2 de AWS a la espera de un nuevo ataque una vez que el servidor sea restaurado.

Dado que la acción se basa en la destrucción de la información, se efectúan backup para la restaruración del sistema y los datos https://attack.mitre.org/mitigations/M1053/.

### Installation

Luego del exploit, el registro de Windows es modificado para que sea llamado luego de reiniciarse la PC genrando persistencia
https://attack.mitre.org/techniques/T1547/001/.
EL adversario puede utilizar credenciales válidads que se encuentran en las PC de la red industrial para conectarse al servidor de manera remota.
https://attack.mitre.org/techniques/T1021/004/

Dado que la conexión SSH es un recurso necesario para el sistema, se decide mitigar le ataque con la incoporación de multiple factoresde autenticación para conectarse https://attack.mitre.org/mitigations/M1032/

El atacante recopila información e informa posibilidad de acceso remoto https://attack.mitre.org/techniques/T1048/.
Se mitigará utilizando buenas prácticas de configuración de firewals para permitir solamente el uso tráfico y puertos deseados. https://attack.mitre.org/mitigations/M1030/

### Exploitation

Como el malware ya se encuentra en la terminal, se realiza un exploit de escala de privilegios para poder dirigir el ataque al Servidor IoT
https://attack.mitre.org/techniques/T1078/003/ 
Se refuerza la complejidad y seguridad de los passwords https://attack.mitre.org/mitigations/M1027/

Con privilegios sobre la PC con windows XP, busca entrar al servidor por medio de la manipulación de cuentas 
https://attack.mitre.org/techniques/T1098/004/

Se restringe el acceso SSH a usuarios específicos https://attack.mitre.org/mitigations/M1042/

### Delivery

El atacante prepara un pendrive con el malware a insertar en una de las PC con Windows XP de la red industrial, siendo este el punto mas débil de la red en cuestión de seguridad.
Utiliza el ataque https://attack.mitre.org/techniques/T1091/ para replicarse por medio de dipositivos extraíbles

Se limita el uso de dispositivos extraíbles de la red https://attack.mitre.org/mitigations/M1034/.
Se deshbailitan características del SO, en este caso el autorun https://attack.mitre.org/mitigations/M1042/
IPC en rack con llaves

### Weaponization

El atacante luego de la etapa de reconocimiento decide atacar por el eslabón mas débil mediante el uso de malware en un pendrive https://attack.mitre.org/techniques/T1587/001.

 - Se utiliza como vector de ataque un pendrive
 - Exploit zero day de la instalación.
 - Búsqueda de la PC con acceso a internet (Servidor).


### Reconnaissance

EL atacante es una proveedor externo que tiene conocimiento de la existencia del sistema IoT, y de la existencia de la red industrial.
Utiliza la técnica de Active Scanning T1595 https://attack.mitre.org/techniques/T1595/ y https://attack.mitre.org/tactics/TA0008/ del modelo MITRE ATT&CK para obtener infirmación de la red / redes adyacentes para luego planificar su ataque.
Ademas un técnico que no conoce las intenciones del atacante puede brindar informaciòn sobre la red e incluso sobre el sistema IoT sin que presente sospechas.
El atacante puede obtener información sobre el tipo de acceso al servidor, hasta incluso su IP y sistema operativo.

Se prohibe al persona brindar infomración sobre la infraestructura de la red, se define una persona que estará permanente con el proveedor cuando realice los trabajao, reduciendo la infomración a la que puede acceder sin cpntrol https://attack.mitre.org/mitigations/M1056/




