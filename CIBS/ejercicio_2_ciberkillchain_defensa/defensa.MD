# Ejercicio CiberKillChain - Defensa

## Alumno

Marcelo García

## Enunciado

Mitigar una cyberkillchain usando técnicas de la matriz de Att&ck para un escenario relacionado a tu trabajo práctico.

La defensa se realiza en forma inversa con respecto al ataque, de manera de poder brindar defensa en la mayor cantidad de capas posibles.

### Actions on objectives

Dado que la acción y objetivos del ataque se basan en la destrucción de la información, se efectúan backups programados para la restaruración del sistema y los datos https://attack.mitre.org/mitigations/M1053/.

### Command and control

Una vez que el atacante cuenta con credenciales, la víctima no tiene opción de mitigar el acceso con credenciales mas que una denegación de servicio que también afecatará el sistema.

### Installation

Dado que la conexión SSH es un recurso necesario para el sistema, se decide mitigar le ataque con la incoporación de multiples factores de autenticación y así evitar la conexión al servidor https://attack.mitre.org/mitigations/M1032/, además se reforzará la defensa utilizando buenas prácticas de configuración de firewals para permitir solamente el uso de tráfico y puertos deseados. https://attack.mitre.org/mitigations/M1030/

### Exploitation

La vulnerabilidad se manifiesta por medio de una escalada de privilegios, para ello se busca reforzar la complejidad y seguridad de los passwords https://attack.mitre.org/mitigations/M1027/ y se restringe el acceso SSH a usuarios específicos https://attack.mitre.org/mitigations/M1042/ solo usuarios de alto rango en la red.

### Delivery

EL vector de ataque es una memoria USB, para mitigarlo se limita el uso de dispositivos extraíbles de la red https://attack.mitre.org/mitigations/M1034/ y se deshabilitan características del SO, en este caso el autorun https://attack.mitre.org/mitigations/M1042.

### Weaponization

NO hay medidas aplicables. Esto se desarrolla fuera del alcance de la victima.

### Reconnaissance

Tratándose de un proveedor externo, se capacita al peronal a cargo de la red para concientizar sobre el riesgo que presenta brindar información sensible de la red. Además se define una persona que estará permanente con el proveedor cuando realice los trabajos, redujendo la información a la que puede acceder sin control https://attack.mitre.org/mitigations/M1056/

Conclusiones

Con las medidas adoptadas se presentan defensas en la mayoria de las etapas de la cadena de ataque, teniendo en cuenta que el ataque se verá frustado en el caso de que una sea exitosa, el nivel de defensa es robusto. No por eso deberá ser considerado como final y se deberá ir actualizando de acuerdo a las nuevas vulnerabilidades que se descubran.



