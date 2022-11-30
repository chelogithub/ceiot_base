# Ejercicio CiberKillChain - Ataque

Haga una copia de este documto

## Alumno

Marcelo García

## Enunciado

Armar una cyberkillchain usando técnicas de la matriz de Att&ck para un escenario relacionado a tu trabajo práctico


## Datos trabajo práctico

El trabajo consiste en un Sistema de monitoreo de servicios de planta de bajo costo. Los nodos sensores se encuentran instalados en zonas apartadas de la planta donde se utiliza la tecnología LoRa / WiFi para tener acceso a los mismos.
Los nodos reportan a Gateways que se encunentran instalados en una red LAN industrial en la cual se dispone de una VLAN IoT exclusiva para estos dispositivos.
Se instala un Linux Server On premise donde se ejecuta el Backend, Frontend y base de datos de la aplicaciòn.
El servidor cuenta con un acceso a internet para la visualización de datos desde el exterior.
Se implementa en AWS una SPA para el acceso al Servidor On Premise.
![](CIBS_ESQUEMARED.jpg)

## Resolución

### Reconnaissance

EL atacante es una proveedor externo que tiene conocimiento de la existencia del sistema IoT, y de la existencia de la red industrial.
Utiliza la técnica de Active Scanning T1595 https://attack.mitre.org/techniques/T1595/ del modelo MITRE ATT&CK para obtener toda la infirmación de la red y elaborar su ataque.
Ademas un técnico que no conoce las intenciones del atacante puede brindar informaciòn sobre la red e incluso sobre el sistema IoT sin que presente sospechas.
El atacante puede obtener información sobre el tipo de acceso al servidor, hasta incluso su IP y sistema operativo.

### Weaponization

El atacante desarrolla un malware para obtener acceso al servidor. https://attack.mitre.org/techniques/T1587/001/

### Delivery

El atacante prepara un pendrive con el malware a insertar en una de las PC con Windows XP de la red industrial, siendo este el punto mas débil de la red en cuestión de seguridad.
Utiliza el ataque https://attack.mitre.org/techniques/T0847/ para replicarse por medio de dipositivos extraíbles

### Exploitation

Como el malware ya se encuentra en la terminal, se realiza un exploit de escala de privilegios para poder dirigir el ataque al Servidor IoT
https://attack.mitre.org/techniques/T0847/
Con privilegios sobre la PC con windows XP, busca entrar al servidor por medio de la manipulación de cuentas 
https://attack.mitre.org/techniques/T1098/004/


### Installation

Luego del exploit, el registro de Windows es modificado para que sea llamado luego de reiniciarse la PC genrando persistencia
https://attack.mitre.org/techniques/T1547/001/.
El atacante recopila información e informa posibilidad de acceso remoto https://attack.mitre.org/techniques/T1048/


### Command and control

EL adversario puede utilizar credenciales válidads que se encuentran en las PC de la red industrial para conectarse al servidor de manera remota.
https://attack.mitre.org/techniques/T1021/004/


### Actions on objectives

Una vez obtenido el acceso al servidor el atacante destruye los datos presentes en el servidor dando de baja el servicio. https://attack.mitre.org/techniques/T1485/ 





  
