# AEE. Bitácora III.UD06 y 7T 04: Conexiones Empresariales.

## 1. Fundamentos de Seguridad y Auditoría

### 1.1. Anatomía de Syslog: El Sistema de Mensajería Vital
El estándar **Syslog** es la piedra angular de la observabilidad en sistemas tipo Unix. Su arquitectura permite categorizar cada evento generado por el kernel o las aplicaciones mediante dos variables críticas:

Facility: Define la categoria o de donde proviene el mensaje es decir el origen del mismo.
Severity:Esto nos dice el nivel de urgencia o importancia de un suceso o un evento en una escala de hasta 8 niveles como puede ser debug, o emerg. 

 ## Análisis de Seguridad en /var/log/auth.log ##

 Permitir que usuarios no privilegiados tengan permisos de lectura sobre `auth.log` es una vulnerabilidad crítica. Un atacante con acceso limitado podría realizar **reconocimiento pasivo**, identificando patrones de conexión de administradores, nombres de usuarios válidos del sistema o incluso detectar si otros atacantes están intentando vulnerar la máquina, facilitando el movimiento lateral o la escalada de privilegios [4].

 ## Diferenciación de eventos SSH ##
Un intento de conexión remota fallido se distingue de un error local por la presencia de la **dirección IP de origen** y el "puerto efímero",un fallo local registra el terminal físico (`tty`), un ataque remoto registra `sshd` junto con la IP externa, permitiendo diferenciar un error humano interno de un ataque de fuerza bruta coordinado.

### 1.2. Cumplimiento y Log Management (Gestión Centralizada)
En el marco del **RGPD** y estándares de cumplimiento industrial, la gestión de registros no es solo técnica, es legal. La centralización de logs en un servidor externo (SIEM o servidor Syslog remoto) ofrece ventajas estratégicas:

1. Integridad de la Evidencia: Si un atacante logra privilegios de *root*, lo primero que intentará será borrar los logs locales para eliminar su rastro. Si los logs se envían en tiempo real a un servidor externo, la evidencia queda fuera de su alcance
2.  Correlación de Eventos: Permite analizar ataques que afectan a múltiples máquinas simultáneamente.
3.  Cumplimiento Legal: Facilita la retención de datos exigida por normativas de auditoría sin saturar el almacenamiento del servidor de producción.


## 2. Referencias Bibliográficas (Formato IEEE)
Trabajo final de Master:[https://reunir.unir.net/bitstream/handle/123456789/3618/ALONSO-ALEGRE%20DIEZ%2C%20MARIA%20BEGO%C3%91A.pdf]
 (https://reunir.unir.net/bitstream/handle/123456789/3618/ALONSO-ALEGRE%20DIEZ%2C%20MARIA%20BEGO%C3%91A.pdf)
Documento de información de ubuntu server: [https://ubuntu.com/server/docs/explanation/intro-to/security/](https://ubuntu.com/server/docs/explanation/intro-to/security/)
