Práctica 4: Simulación de Campaña de Phishing
Este repositorio documenta la realización de una simulación de campaña de phishing como parte de la asignatura de Ciberseguridad del 2º curso de ASIR.



Autor: Adrián Alonso Ridao 


Evaluación: 1ª Evaluación 

🎯 Objetivo de la Práctica
El objetivo principal de esta práctica es comprender el funcionamiento y la mecánica de un ataque de ingeniería social. Esto se logra mediante la configuración de un entorno controlado para simular una campaña de phishing de principio a fin, desde la instalación de las herramientas hasta el análisis de los resultados.

🛠️ Herramientas Utilizadas

Gophish: Framework de phishing de código abierto utilizado para crear y gestionar la campaña de simulación.


Ngrok: Herramienta que expone servidores locales a Internet. Se utilizó para hacer pública la landing page de Gophish y que fuera accesible desde fuera de la red local.


📋 Metodología de la Simulación
El proceso siguió varias etapas clave para construir una campaña funcional:

1. Instalación y Configuración

Gophish: Se descargó la versión para Windows desde el repositorio de GitHub y se ejecutó el archivo .exe. Al iniciar, Gophish genera una contraseña de administrador temporal.





Ngrok: Se realizó el registro en la web de Ngrok y se instaló la herramienta. Se configuró el authtoken y se creó un túnel HTTP para exponer el servidor local.




2. Preparación de la Campaña en Gophish
Una vez Gophish estuvo accesible a través de la URL https://127.0.0.1:3333 y se cambió la contraseña inicial, se procedió a configurar los componentes de la campaña:



Sending Profile (Perfil de Envío): Se configuró un perfil de envío de correo utilizando un servidor SMTP (en este caso, smtp.gmail.com:587) y credenciales de una cuenta de Gmail. Se realizó un envío de prueba para verificar la configuración.






Landing Page (Página de Aterrizaje): Se creó una página de aterrizaje importando el sitio de Facebook. Se activaron las casillas Capture Submitted Data y Capture Passwords para registrar las credenciales introducidas por la víctima.






Email Template (Plantilla de Correo): Se creó una plantilla de correo electrónico simulando ser una notificación de Facebook. Se importó el código fuente de un correo real y se utilizó la opción Change Links to Point to Landing Page para que todos los enlaces del correo redirigieran a la landing page falsa.





Users & Groups (Usuarios y Grupos): Se creó un grupo de usuarios objetivo, añadiendo manualmente el nombre y el correo electrónico de la víctima.


3. Lanzamiento y Ejecución
Se creó la campaña final en la pestaña Campaigns.

Se seleccionaron la plantilla de correo (Invitación Facebook) , la landing page (Facebook) , el perfil de envío (Pruebas) y el grupo de usuarios (Facebook grupo).




En el campo URL, se introdujo la dirección pública generada por Ngrok.


Se lanzó la campaña (Launch Campaign).

4. Recolección de Resultados
Tras el envío, el correo fue recibido por el usuario. Al hacer clic en el enlace, fue redirigido a la página de Facebook clonada.



El dashboard de Gophish reflejó los resultados de la campaña, mostrando:


Email Sent: Correos enviados.


Email Opened: Correos abiertos.


Clicked Link: Clics en el enlace.


Submitted Data: Datos (credenciales) enviados.

💡 Conclusiones y Lecciones Aprendidas
Esta práctica demostró la alta eficacia de las técnicas de ingeniería social. Algunas de las lecciones clave aprendidas son:


Factor Humano: El éxito de un ataque de phishing no depende solo de la complejidad técnica, sino de la capacidad del atacante para generar confianza y urgencia en la víctima. El factor humano sigue siendo el eslabón más débil.



Apariencia de Legitimidad: El uso de logos, dominios similares y lenguaje corporativo es fundamental para inducir confianza en el destinatario.


Facilidad de Ejecución: Herramientas como Gophish y Ngrok demuestran que es posible recrear un escenario de phishing funcional con recursos limitados.

🛡️ Medidas de Mitigación Recomendadas
Basado en el análisis de la práctica, se proponen las siguientes estrategias de mitigación para una organización:


Formación Continua: Implementar programas periódicos de capacitación sobre el reconocimiento de phishing y la verificación de URLs.


Autenticación Multifactor (MFA): Incorporar MFA para mitigar el impacto del robo de credenciales.


Políticas de Seguridad de Correo: Configurar correctamente los registros SPF, DKIM y DMARC, además de usar filtros antiphishing.


Gestión Segura de Contraseñas: Promover el uso de gestores de contraseñas y evitar la reutilización de las mismas.


Monitorización y Respuesta: Establecer procedimientos de detección temprana y protocolos de respuesta ante incidentes.


Evaluaciones Periódicas: Realizar simulaciones controladas de phishing (como esta) para medir la resiliencia de la organización.

⚠️ Aspectos Éticos y Descargo de Responsabilidad
Esta práctica se desarrolló exclusivamente en un entorno controlado y con fines académicos. Todas las simulaciones se realizaron sobre cuentas y servidores de prueba, sin afectar a sistemas, datos o usuarios reales. No se ha llevado a cabo ninguna actividad ilícita ni se han vulnerado sistemas externos. Los datos recopilados fueron eliminados al finalizar el ejercicio
