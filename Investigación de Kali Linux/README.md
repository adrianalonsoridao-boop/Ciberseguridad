Práctica de Laboratorio: Investigación de Kali Linux 

Este repositorio contiene la documentación de una práctica de laboratorio centrada en la familiarización con el sistema operativo Kali Linux.


Autor: Adrián Alonso Ridao 


Asignatura: CIBERSEGURIDAD 


Curso: 2°ASIR 


Evaluación: 1º EVALUACIÓN 

📜 Descripción del Proyecto
Kali Linux es una distribución de Linux especializada, diseñada para auditorías de seguridad y pruebas de penetración. A diferencia de otros sistemas operativos de uso general, Kali viene preempaquetado con un vasto conjunto de herramientas organizadas para tareas específicas de ciberseguridad.


Esta práctica sirve como una introducción fundamental al entorno de Kali Linux, cubriendo tanto la interfaz gráfica de usuario (GUI) como la interfaz de línea de comandos (terminal o shell).

🎯 Objetivos
Los objetivos principales de este laboratorio fueron:

Familiarizarse con la GUI (Interfaz Gráfica de Usuario) de Kali Linux.

Familiarizarse con el ambiente de la terminal de Kali Linux.

📂 Parte 1: Familiarización con la GUI de Kali Linux
La primera parte de la práctica se centró en explorar el entorno de escritorio de Kali.


Inicio de Sesión y Escritorio: Se realizó el inicio de sesión con las credenciales kali/kali. Se exploraron los elementos básicos del escritorio, como los iconos (Home, File System, Trash) y el "Panel" (similar a la barra de tareas).





Personalización del Panel: Se investigaron las opciones para añadir nuevos elementos al panel y modificar sus preferencias.



Menú de Aplicaciones: Se navegó por el menú principal de "Aplicaciones" , observando cómo las herramientas de seguridad están organizadas por categorías (p. ej., 01-Reconnaissance, 05-Persistence, 15-Forensics, etc.).






Apertura de Terminal: Se finalizó la exploración de la GUI abriendo una ventana de terminal para la segunda parte.

💻 Parte 2: Uso de la Terminal (Shell)
La segunda parte se centró en el uso de la terminal, el intérprete de comandos de Linux. Se practicaron los siguientes comandos y conceptos:

Documentación

man: Se utilizó para acceder a las páginas del manual de otros comandos (p. ej., man ls o man man) y entender su funcionamiento y opciones.


Navegación y Directorios

pwd: Para imprimir el directorio de trabajo actual (Print Working Directory).


ls: Para listar el contenido de un directorio. Se usaron las opciones -l (formato de lista detallado) y -a (mostrar todos los archivos, incluidos los ocultos).






cd: Para cambiar de directorio (Change Directory).



mkdir: Para crear nuevos directorios (Make Directory), como kali_folder1, kali_folder2 y kali_folder3.


Conceptos Clave de Rutas

Rutas Completas (Absolutas): Rutas que comienzan desde el directorio raíz (/).


Rutas Relativas: Rutas basadas en el directorio actual.


~: Representa el directorio de inicio del usuario actual (p. ej., /home/kali).



.: Una referencia al directorio actual.




..: Una referencia al directorio padre (un nivel más arriba).



Redirección de Entrada/Salida

echo: Se usó para imprimir texto en la terminal.


> (Redirección): Se utilizó para enviar la salida de un comando (como echo) a un archivo, sobrescribiendo el contenido existente. (Ej. echo "mensaje" > text_file.txt ).



>> (Anexión): Se usó para redirigir la salida y añadirla al final de un archivo sin borrar su contenido previo. (Ej. echo "otro mensaje" >> text_file.txt ).



cat: Para mostrar el contenido de un archivo en la terminal.

Manipulación de Archivos y Directorios

rm: Para eliminar archivos (Remove). (Ej. rm text_file.txt ).



rm -r: Opción recursiva para eliminar directorios y todo su contenido. (Ej. rm -r kali_folder1 ).



mv: Para mover o renombrar archivos y directorios (Move). (Ej. mv kali_folder2/text_file.txt . o mv kali_folder3/ kali_folder2/ ).




💡 Reflexión
Esta práctica de laboratorio proporcionó una base sólida sobre cómo navegar y operar en Kali Linux, tanto gráficamente como a través de la terminal. La fortaleza de Kali reside en su colección de herramientas, y para aprender más sobre ellas, el método más efectivo es consultar sus manuales (man) y textos de ayuda integrados.
