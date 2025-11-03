Práctica: Reconocimiento Activo y Escaneo de Vulnerabilidades
Este repositorio documenta la práctica de laboratorio sobre reconocimiento activo y escaneo de vulnerabilidades, como parte de la asignatura de Ciberseguridad.


Autor: Adrián Alonso Ridao 


Asignatura: CIBERSEGURIDAD 


Curso: 2º ASIR 


Evaluación: 1º EVALUACIÓN 

🎯 Objetivo General
El objetivo de esta práctica es aplicar técnicas de reconocimiento activo utilizando Nmap, realizar enumeración de servicios y ejecutar un escaneo básico de vulnerabilidades.

🛠️ Metodología y Comandos
La práctica se dividió en dos fases principales: una exploración inicial de los comandos de Nmap y un laboratorio práctico comparativo.

1. Exploración de Comandos de Nmap
En esta fase inicial, se probaron diferentes tipos de escaneos de Nmap contra un objetivo (192.168.1.10):


Escaneo SYN Básico (-sS): Envía paquetes SYN para detectar puertos.


Escaneo de Conexión TCP (-sT): Completa el handshake TCP; es más ruidoso.


Escaneo UDP (-sU): Se utilizó para escanear puertos UDP comunes.


Detección de Hosts (-sn): Confirma si un host está activo.



Plantillas de Tiempo (-T0 vs -T4): Se probó el modo "paranoico" (-T0), que es muy lento para evadir detección , y el modo "agresivo" (-T4), que es mucho más rápido.



Detección de Versiones (-sV): Se usó para obtener información detallada de los servicios.



Scripts NSE: Se ejecutaron scripts para enumerar servicios web (http-enum) y SMB (smb-enum-shares).


2. Práctica de Laboratorio: Escaneo Comparativo
En esta fase, se realizó un escaneo detallado en un entorno de laboratorio controlado con tres máquinas: Kali (Atacante), Windows 10 (Objetivo) y Metasploitable2 (Objetivo Vulnerable).

PARTE 1: Escaneo Básico de Red
Ejercicio 1.1 - Descubrimiento de Hosts:

Se identificaron 3 hosts activos en la red.


Kali: 192.168.1.11 


Windows: 192.168.1.10 


Metasploitable: 192.168.1.12 

Ejercicio 1.2 - Escaneo de Puertos por Defecto (-sS):


Windows: Resultó en 1000 puertos filtrados (no-response).


Metasploitable: Mostró 23 puertos abiertos , incluyendo FTP (21), SSH (22), Telnet (23), HTTP (80), SMB (445) y MySQL (3306) .



Conclusión: La máquina Windows no proporcionó información, mientras que Metasploitable demostró ser altamente vulnerable.

PARTE 2: Técnicas Avanzadas de Escaneo
Ejercicio 2.1 - Escaneo Completo de Puertos (1-65535) (-sT):


Windows: Nuevamente mostró 1000 puertos filtrados. Tiempo: 24.27 segundos.



Metasploitable: Encontró los mismos servicios y un servicio "unknown" en el puerto alto 8180. Tiempo: 0.54 segundos.



Ejercicio 2.2 - Escaneo UDP:

Se escanearon los puertos UDP 53, 67, 68, 69, 123, 161 y 162.

Tanto en Windows como en Metasploitable, todos los puertos consultados reportaron el estado open|filtered .


Ejercicio 2.3 - Técnicas de Evasión (Timing):


Modo Paranoico (-T0): No se recibió respuesta ni de Windows ni de Metasploitable.


Modo Agresivo (-T4):

Windows: Escaneo completado en 22.56 segundos.

Metasploitable: Escaneo completado en 0.58 segundos.

PARTE 3: Enumeración de Servicios
Ejercicio 3.1 - Detección de Versiones (-sV y -sC):


Windows: No se detectaron servicios.


Metasploitable: Se identificaron versiones detalladas de los servicios:


FTP (21): vsftpd 2.3.4 (con login anónimo permitido ).



SSH (22): OpenSSH 4.7p1 Debian 8ubuntu1.


Telnet (23): Linux telnetd.


SMTP (25): Postfix smtpd.


Domain (53): ISC BIND 9.4.2.


HTTP (80): Apache httpd 2.2.8 ((Ubuntu) DAV/2).

Ejercicio 3.2 - Enumeración Específica (Scripts NSE):

HTTP (Puerto 80):

Se confirmó el servidor Apache/2.2.8 (Ubuntu) DAV/2.

Se detectó X-Powered-By: PHP/5.2.4-2ubuntu5.10.

Se encontraron directorios de interés como /tikiwiki/ , /test/ , /phpinfo.php y /phpMyAdmin/.




SSH (Puerto 22):

En Windows, el puerto 22 estaba filtrado.

En Metasploitable, se enumeraron las claves de host (DSA y RSA) y los algoritmos soportados para kex , cifrado y MAC.




SMB (Puerto 445):

Tanto en Windows como en Metasploitable, el puerto 445 se reportó como filtrado al usar los scripts de enumeración de SMB.


PARTE 4: Análisis y Reporting
Ejercicio 4.1 - Generación de Reportes:

Los resultados de los escaneos se exportaron a los tres formatos principales de Nmap:

Formato Normal (-oN) 

Formato XML (-oX) 

Formato Grepable (-oG) 

Ejercicio 4.2 - Análisis de Resultados:

Se identificaron y priorizaron 3 servicios con versiones potencialmente vulnerables en la máquina Metasploitable:

1. vsftpd 2.3.4 (Puerto 21):


Vulnerabilidad: Permite la ejecución remota de código a través de una puerta trasera oculta.


Riesgo: Crítico.


Recomendación: Actualizar o deshabilitar el servicio FTP y restringir el acceso con firewall.

2. Apache httpd 2.2.8 (Puerto 80):


Vulnerabilidad: Versión susceptible a desbordamiento y ejecución remota de código.


Riesgo: Alto.


Recomendación: Actualizar a una versión estable (2.4.x o superior) y habilitar HTTPS.

3. Samba smbd 3.0.20:


Vulnerabilidad: Permite la ejecución de código remoto.


Riesgo: Alto.


Recomendación: Restringir el servicio SMB solo a redes internas seguras y actualizar a una versión más reciente.
