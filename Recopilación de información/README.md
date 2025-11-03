Práctica 1: Recopilación de Información (OSINT)
Este repositorio documenta una práctica de recopilación de información pasiva (OSINT) como parte de la asignatura de Ciberseguridad.


Curso: 2º ASIR 


Evaluación: 1º EVALUACIÓN 


Tema: TEMA 3 

🎯 Objetivo General
El objetivo de esta práctica es aplicar técnicas de reconocimiento pasivo contra un dominio objetivo, utilizando motores de búsqueda, herramientas OSINT especializadas y el buscador Shodan.


Dominio Objetivo: salesianosatocha.es 

metodologías y Hallazgos
La investigación se dividió en tres partes principales:

Parte 1: Búsqueda con Motores de Búsqueda (Google Dorks)
El objetivo de esta fase fue investigar la presencia digital y la reputación de la organización utilizando operadores de búsqueda avanzados.

Hallazgos Clave:


Subdominios: Se identificaron subdominios, incluyendo aula.salesianosatocha.es (Aula Virtual) y salesianosatocha-salesianos-madrid.educamos.com.




Correos Electrónicos: Mediante el operador mailto:, se descubrió la dirección de correo escuela.empresa@salesianosatocha.es. Otra búsqueda reveló la dirección salesianosatocha.madrid@educa.madrid.org.




Documentos Públicos: El dork filetype:pdf reveló múltiples documentos PDF públicos en el sitio , incluyendo información sobre ciclos formativos como "Audiovisuales" , "Fabricación Mecánica" y "Artes Gráficas".





Menciones en Noticias: Una búsqueda en elpais.com encontró artículos que mencionan a "Salesianos Atocha", destacando el éxito de empleabilidad de sus alumnos de especialidades industriales.


Parte 2: OSINT con Recon-ng (y Sherlock)
El objetivo era utilizar Recon-ng para recopilar información de redes sociales y fuentes públicas.


Desafío: Durante la práctica, los módulos de Recon-ng (como twitter_mentioned y twitter_mentions ) no pudieron ejecutarse correctamente debido a que requerían claves de API que no estaban configuradas.



Herramienta Alternativa: Para solventar este problema, se utilizó Sherlock Project.


Comando Ejecutado: sherlock salesianosatocha.


Hallazgos: Sherlock identificó 12 resultados, confirmando la presencia del nombre de usuario "salesianosatocha" en plataformas como:

Blogger 

GitHub 

Slack 

WordPress 

YouTube 

Parte 3: Investigación con Shodan
El objetivo de esta fase fue aprender a usar Shodan para identificar sistemas expuestos en Internet.


¿Qué es Shodan? Shodan es un buscador especializado que, en lugar de indexar páginas web, indexa servicios y equipos conectados a Internet como servidores, cámaras IP, routers y sistemas de control industrial. Escanea direcciones IP , recoge información de puertos abiertos y guarda los "banners" (respuestas) de los servicios.




Consulta Realizada: org:"Salesianos" country:ES 

Hallazgos Clave:


Resultados Totales: La búsqueda arrojó 50 resultados para la organización "Salesianos" en España.


IPs Identificadas: Se identificaron varias IPs asociadas a "SALESIANOS ATOCHA" en Madrid , incluyendo 194.224.19.81 y 194.224.19.82.





Puertos Abiertos: Se detectaron múltiples puertos abiertos, destacando el Puerto 443 (HTTPS) y el Puerto 161 (SNMP).




Servicios y Dispositivos Expuestos:

En la IP 194.224.19.82 , se identificó un servidor web que se presenta como un dispositivo "Z USG FLEX 700".




Este dispositivo es un producto de Zyxel Communications Corporation y utiliza un certificado SSL autofirmado.


En otras IPs (...81 y ...87), el servicio SNMP estaba expuesto , revelando información del fabricante del dispositivo, en este caso, "HUAWEI Technology Co.,Ltd"
