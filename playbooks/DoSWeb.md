# Plantilla del Playbook de la respuesta a incidentes

### Tipo de incidente

Ataque Dos/DoS a aplicaciones web


### Playbook
Este Playbook describe los pasos de respuesta para incidentes de ataques Dos/DDoS a aplicaciones web que puede utilizarse para:

* Reunir pruebas
* Contener y luego erradicar el incidente
* Recuperarse del incidente
* Llevar a cabo las actividades posteriores al incidente, incluyendo los procesos post-mortem y de retroalimentación

## Proceso de respuesta a incidentes
---
### Parte 1: Adquirir, preservar y documentar las pruebas

1.	Usted se da cuenta de que ha habido un posible acceso involuntario a los datos. Esta información podría llegar a través de diferentes medios, por ejemplo:
  - Un sistema de tickets interno (las fuentes del ticket son variadas y podrían incluir cualquiera de los medios que se indican a continuación).
  - Un mensaje de un contratista o proveedor de servicios de terceros.
  - Desde una alerta en uno de sus propios sistemas de monitorización, ya sea interno o externo 
  - A través de una denuncia anónima
  - A través de investigadores de seguridad independientes o externos
2. Confirme que se ha creado un ticket/caso interno para el incidente dentro de su organización. Si no es así, levante uno manualmente.
3. Determine y comience a documentar el impacto/experiencia del usuario final del problema. Esto debe documentarse en el ticket/caso relacionado con el incidente
4. En el caso de los tickets/casos creados automáticamente, determinar qué alarmas/métricas internas indican actualmente un problema (¿qué causó la creación del ticket?)
5. Determine la aplicación afectada (esto puede hacerse rápidamente a través de las etiquetas de recursos)
6. Determine si hay algún evento conocido que pueda estar causando una interrupción en su aplicación (aumento del tráfico debido a un evento de ventas, o similar)
7. Compruebe su base de datos de gestión de la configuración  para determinar si ha habido algún despliegue en su entorno de producción (actualizaciones de código, software o infraestructura) que pueda provocar un aumento del tráfico en la(s) URL(s) afectada(s)
8. Comunicaciones de incidentes:
    1. Identifique los roles de las partes interesadas a partir de la entrada de la aplicación en la CMDB para esa aplicación, o a través del registro de riesgos de la aplicación
    2. Abra una conferencia de comunicación para el incidente
    3. Notificar a las partes interesadas identificadas, incluyendo (si es necesario) el personal legal, las relaciones públicas, los equipos técnicos y los desarrolladores, y añadirlos al ticket y a la sala de guerra, para que se actualicen a medida que se actualiza el ticket
9. Comunicaciones externas:
    1. Asegúrese de que el asesor jurídico de su organización esté informado y se incluya en las actualizaciones de estado a las partes interesadas internas y especialmente en lo que respecta a las comunicaciones externas.
    2. Para los compañeros de la organización que son responsables de proporcionar declaraciones de comunicación pública/externa, asegúrese de que estas partes interesadas internas se agregan al ticket para que reciban actualizaciones de estado regulares con respecto al incidente y puedan completar sus propios requisitos para las comunicaciones dentro y fuera de la empresa.
    3. Si existen normas en su jurisdicción que exijan la notificación de este tipo de incidentes, asegúrese de que las personas de su organización responsables de notificar a los organismos locales o federales encargados de hacer cumplir la ley también sean notificadas del suceso/añadidas al ticket. Consulte a su asesor jurídico y/o a las fuerzas del orden para que le orienten sobre la recogida y conservación de las pruebas y la cadena de custodia.
    4. Es posible que no exista una normativa, pero las bases de datos abiertas, los organismos gubernamentales o las ONG pueden hacer un seguimiento de este tipo de actividad. Su denuncia puede ayudar a otros
10. Determine los recursos implicados en el servicio de la aplicación (comience con los recursos de front-end, incluyendo CDNs, equilibradores de carga y servidores de aplicaciones de front-end, luego pase a los servicios de apoyo, como bases de datos, cachés, etc.)
11. Obtenga la línea de base documentada de la aplicación y localice las métricas para el rendimiento estándar de la aplicación de gestión.
12. Obtenga los registros relevantes para el incidente (serán los registros de los recursos identificados anteriormente, en el punto 4), estos deben incluir lo siguiente:
    1. Registros de acceso al servidor web
        1. Basado en RHEL - /var/log/apache/access.log, o
        2. Basado en Debian - /var/log/apache2/access.log
13. Una vez que haya verificado que tiene acceso a los logs, utilice su herramienta preferida (por ejemplo, Amazon Athena, herramientas internas o de terceros) para revisar los logs y determinar si hay alguna firma de ataque identificable. Dichas firmas pueden ser las siguientes
    1. Un número inusual de solicitudes en un periodo de tiempo determinado
    2. Un conjunto inusual de IPs de origen
    3. Un conjunto de URLs no reconocidas en la sección de peticiones
    4. Parámetros POST o de consulta que no son esperados o soportados por la aplicación
    5. Controles HTTP inesperados (GET, donde esperamos POST, etc)
    6. Un número inusualmente alto de respuestas 2xx, 4xx o 5xx
15. A partir de la inmersión en el registro descrita en los pasos anteriores, determine el vector de ataque probable (overflow HTTP, overflow SYN, relleno de credenciales, ataque de reflexión UDP, etc.)
16. ¿Qué recursos son el objetivo? Anote los nombres de los recursos.

### Parte 2: Recuperarse del incidente

 El siguiente paso es determinar si el ataque ha sido mitigado, o si se necesita un ajuste adicional para erradicar el ataque. Esto incluye la revisión de los registros previos y posteriores a la mitigación para:

* Determinar el impacto de las mitigaciones ya realizadas
* Identificar las firmas de ataque para intentar erradicar o mitigar aún más el ataque

Revise los registros obtenidos una vez detectado el incidente. Ahora que las mitigaciones están en marcha, es necesario volver a obtener esas métricas y registros, y compararlos con las métricas y registros del incidente obtenidos anteriormente. Si la actividad de las solicitudes ha vuelto a los niveles de referencia y se confirma que el servicio está disponible, el ataque ha sido mitigado: Continúe supervisando el servicio después del ataque. Si la tasa de solicitudes del servicio sigue siendo elevada y el servicio está disponible, el ataque ha sido mitigado: Siga vigilando el servicio para ver si se produce un cambio en el método de ataque. Si el servicio no está disponible, vuelva a la Parte 1 y revise los registros y los datos relacionados para determinar si ha identificado correctamente el vector de ataque, o si el atacante ha cambiado el vector en respuesta a la mitigación.

### Parte 3: Actividad posterior al incidente

Esta actividad ayuda a los equipos a evaluar su respuesta al incidente real, determinar lo que funcionó y lo que no, actualizar el proceso basado en esa información y registrar estos hallazgos.

1. Revise el manejo del incidente y el proceso de manejo del incidente con las partes interesadas clave.
2. Documente las lecciones aprendidas, incluidos los vectores de ataque, la mitigación, la configuración errónea, etc.
3. Almacene los artefactos de este proceso con la información de la aplicación en la entrada de la base de datos.
4. Actualizar los documentos de riesgo en base a cualquier combinación de amenaza/vulnerabilidad recientemente descubierta como resultado de las lecciones aprendidas.
5. Si se requiere una nueva configuración de la aplicación o de la infraestructura para mitigar cualquier riesgo recientemente identificado, realice estas actividades de cambio y actualice la configuración de la aplicación.