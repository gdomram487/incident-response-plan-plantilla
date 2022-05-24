## Playbook: Spyware

### Identificar

`TODO: Ampliar los pasos de la identificación, incluyendo las herramientas y estrategias clave, para el incidente.`

1. **Identificar el ataque** 
    1. Para identificar estos ataques se debe prestar atención al rendimiento del equipo o posibles mensajes emergentes.
    2. Utilizar software de detección y eliminación de Spyware.
    3. Programar análisis de detección de Spyware diaria.

1. **Determinar el alcance**
    1. ¿Se puede infectar algún equipo o servidor de la empresa de Spyware y que éste se propague?
        * Intentar establecer un plan para que el malware no se propague a el resto de equipos de la red.
       
1. **Evaluar el impacto** 
    1. Evaluar el impacto funcional: impacto en la empresa:
        * ¿Cuánto dinero se pierde o está en riesgo?
        * ¿Cuántos proyectos se degradan o están en riesgo?
    2. Evaluar el impacto en la información: impacto en la confidencialidad, integridad y disponibilidad de los datos:
        * ¿Cuán críticos son los datos para la empresa/proyecto?
        * ¿Cuán sensibles son los datos? 
        * ¿Cuál es la situación reglamentaria de los datos? 

1. **Encontrar el vector de ataque**  
    * **Archivos adjuntos por correo electrónico:** Uno de los métodos más habituales para infectar un equipo con Spyware. En muchos de los casos de usa la suplantación de identidad para engañarnos y que descarguemos el archivo adjunto malicioso.
    * **Descarga de Spyware por navegación:**  Páginas engañosas o anuncios pop-up pueden llevarnos a la descarga accidental de Spywarte. Este método es muy popular y suele ser uno de los más propensos a infectar los equipos si la persona no está debidamente informada.
    * **Vulnerabilidad en aplicación web:** Mediante la explotación de vulnerabilidades de la aplicación web de la empresa es posible infectar el servidor con Spyware realizando una previa escalada de privilegios.


### Remediar

**Software de mitigación de Spyware** Utilizar un software especializado en eliminar malware y Spyware para mantener limpio el equipo de software malicioso.
**Concienciación de los trabajadores de la empresa** Aplicar un plan de concienciación para que los empleados conozcan y sepan actuar ante los posibles vectores de ataque que pueden contener Spyware.

#### Contener

`TODO: Personalizar los pasos de contención, tácticos y estratégicos.`

`TODO: especificar las herramientas y los procedimientos para cada paso, a continuación.`

**La contención de este tipo de ataques es necesaria para un correcto funcionamiento de los equipos y servidores de la empresa.**

* Utiliizar un bloqueador de anuncios en el navegador web para evitar mensajes pop-up y otros anuncios que puedan llevarnos a la descarga de Spyware.
* Desconectar el equipo infectado de la red para evitar una posible propagación del Spyware por toda la red.
* Estudiar y reconecer el vector de ataque por el que se ha infectado el equipo mediante malware y bloquear el dominio donde se ha descargado el archivo malicioso o bien actualizar la aplicación web para eliminar la posible vulnerabilidad.
* Antes de volver a conectar el equipo a la red, hay que asegurarse de que el Spyware ha sido eliminado completamente del sistema mediante un software especializado.


#### Mitigar

`TODO: Personalizar las medidas de erradicación, tácticas y estratégicas.`

`TODO: Especifique las herramientas y los procedimientos para cada paso, a continuación.`

* Restringir el acceso a sitios web sospechosos. Esto resulta particularmente útil cuando existen múltiples usuarios que acceden a Internet en su equipo. Existen módulos Antivirus y Antispyware que permiten bloquear ciertos sitios web o dominios completos.
* Evitar el phishing y el spam. No abrir correos de remitentes desconocidos. Hay que analizar todos los archivos adjuntos antes de abrirlos o descargarlos.
* Utilizar un bloqueador de ventanas emergentes. Algunas de las ventanas emergentes pueden ser parte de un intento de fraude electrónico o una puerta de enlace para la descarga del Spyware. Para ello se utilizará una extensión de navegador web que elimine este vector de ataque por completo.
* Mantener actulizado todos los sistemas y software de los equipos y servidores de la empresa para eliminar posibles vulnerabilidades existentes en versiones antiguas.
* Realizar siemrpe la descarga de software por medio de fuentes oficiales. Nunca descargar software a través de fuentes de terceros, ya que esto puede llevar a la descarga no deseada de Spyware.
* Bloquear los puertos USB en caso de que no sean necesarios, para evitar la infección del equipo a través de una memoria USB.


### Comunicar

`TODO: Personalice los pasos de la comunicación`.

`TODO: Especifique las herramientas y los procedimientos (incluyendo quién debe participar) para cada paso, a continuación, o remítase al plan general.`

1. Escalar el incidente y comunicarlo a la dirección según el procedimiento.
2. Documentar el incidente según el procedimiento.
3. Comunicarse con los asesores jurídicos internos y externos según el procedimiento, incluyendo discusiones sobre el cumplimiento, la exposición al riesgo, la responsabilidad, el contacto con las fuerzas del orden, etc.
4. Comunicarse con los usuarios (internos)
    1. Comunicar las actualizaciones de la respuesta a incidentes según el procedimiento.
    2. Comunicar el impacto del incidente **y** las acciones de respuesta al incidente (por ejemplo, contención: "¿por qué mi equipo trabaja de forma más lenta de lo habitual?").
    3. Comunicar los requisitos: "¿qué deben hacer y no hacer los usuarios?" 
5. Contactar con los proveedores de seguros
    1. Discutir qué recursos pueden poner a disposición, qué herramientas y proveedores apoyan y pagarán, etc.
    2. Cumplir con los requisitos de presentación de informes y reclamaciones para proteger la elegibilidad
6. Comunicarse con los reguladores, incluyendo una discusión sobre los recursos que pueden poner a su disposición (no sólo una notificación de tipo repetitivo: muchos pueden ayudar activamente)
7. Considerar la posibilidad de notificar e involucrar a las fuerzas de la ley del país en cuestión, ya sean locales o nacionales
8. Comunicarse con los proveedores de seguridad y TI
    1. Notifique y colabore con proveedores de seguridad según el procedimiento
    2. Notificar y colaborar con consultorías de seguridad según el procedimiento

### Recuperar

`TODO: Personalizar los pasos de recuperación.`

`TODO: Especifique las herramientas y los procedimientos para cada paso, a continuación.`

* Reconstruir los sistemas infectados a partir de medios conocidos y buenos
* Restaurar a partir de copias de seguridad conocidas y limpias.
* Establecer parches de seguridad en los sistemas y todo el software de los equipos.