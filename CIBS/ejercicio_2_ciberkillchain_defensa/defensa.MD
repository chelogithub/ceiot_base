# Ejercicio CiberKillChain - Defensa

## Alumno

Marcelo García

## Enunciado

Mitigar una cyberkillchain usando técnicas de la matriz de Att&ck para un escenario relacionado a tu trabajo práctico.

La defensa se realiza en forma 

### Actions on objectives

Dado que la acción y objetivos del ataque se basa en la destrucción de la información, se efectúan backup para la restaruración del sistema y los datos https://attack.mitre.org/mitigations/M1053/.

### Command and control

Una vez que el atacante cuenta con credenciales no puede tomarse acción de mi


### Installation

Dado que la conexión SSH es un recurso necesario para el sistema, se decide mitigar le ataque con la incoporación de multiple factores de autenticación y así evitar la conexión al servidor https://attack.mitre.org/mitigations/M1032/ además se reforzará la defensa utilizando buenas prácticas de configuración de firewals para permitir solamente el uso tráfico y puertos deseados. https://attack.mitre.org/mitigations/M1030/

### Exploitation

La vulnerabilidad se manifiedta cpor medio de una escalada de privilegios, para ello se busca reforzar la complejidad y seguridad de los passwords https://attack.mitre.org/mitigations/M1027/ y se restringe el acceso SSH a usuarios específicos https://attack.mitre.org/mitigations/M1042/


### Delivery

EL vector de ataque se espera que sea por medio de una memoria USB, para mitigarlo se limita el uso de dispositivos extraíbles de la red https://attack.mitre.org/mitigations/M1034/ y se deshbailitan características del SO, en este caso el autorun https://attack.mitre.org/mitigations/M1042/
IPC en rack con llaves

### Weaponization

NO hay medidas aplicables. Esto se desarrolla fuera del alcance de la victima.

### Reconnaissance

Tratándose de un proveedor externo, se capacita al peronal a cargo de la red para concientizar y ecitar brindar información sensible de la red. Además se define una persona que estará permanente con el proveedor cuando realice los trabajos, reduciendo la infomración a la que puede acceder sin control https://attack.mitre.org/mitigations/M1056/




