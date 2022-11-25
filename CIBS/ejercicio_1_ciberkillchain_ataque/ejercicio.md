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
Se implementa en AWS una SPA para el acceso al sistema On Premise, donde el mismo solo permite el tráfico proveniente de AWS

![](CIBS_ESQUEMARED.jpg)

## Resolución

### Reconnaissance
EL atacante es una proveedor externo que tiene conocimiento de la existencia del sistema IoT, y de la existencia de la red industrial.
Utiliza la técnica de Active Scanning T1595 https://attack.mitre.org/techniques/T1595/ del modelo MITRE ATT&CK para obtener toda la infirmación de la red y elaborar su ataque.

El atacante obtuvo

  - Información de la red industrial 
  - Información de la  existencia del servidor IoT

### Weaponization

 - Se utiliza como vector de ataque 
 - Exploit 15 cero days de la instalación para no despertar sospechas
 - Búsqueda de la PC con acceso a internet.
 - Instalación de backdoor
 - Identificación de bd.

### Delivery

El atacante prepara un pendrive con el malware a insertar en una de las PC con Windows XP de la red industrial

### Exploitation
Vulnerabilidad en winxp



### Installation

Crea punto de persistencia agregando servicios, autorun, etc.


### Command and control
Mediante las PC de la red Industrial llega al servidor Linux que contiene el sistema IoT, eta pc tiene dos placas de red, ambas se conectan a dos vlan, una que se conecta con todas las PC  de la red industrial y otra por la cual se conectar a internet


### Actions on objectives

 - El atacante ingresa a la carpeta de proyecto donde se encuentra el archivo de configuración de docker y obtiene credenciales de acceso a la base de datos.
 - Obtiene acceso a la base de datos y elimina registros 
 - Elimina credenciales de la base de datos imposibilitando el acceso y el servicio.
 - Modifica HTML de la SPA IoT informando el ataque y exponiendo el riesgo que representa el sistema.
 - Obtener información del sistema de IoT
 - Generar pérdida de datos
 - Generar denegación de servicio


  
