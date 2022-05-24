## Playbook: XSS

### Identificar

`TODO: Ampliar los pasos de la identificación, incluyendo las herramientas y estrategias clave, para el incidente.`

1. **Identificar el ataque** 
    1. Para identificar estos ataques se puede mantener un log de las acciones realizadas en  el servidor web.
    2. Utilizar herramientas para la deteccion de ataques en servidores web como crashtest security suite.
    3. Realizar analisis de codigo mensuales en busca de problemas relacionados con XSS

1. **Determinar el alcance**
    1. ¿Se puede realizar cualquier tipo de ataque XSS en nuestro servidor web?
        * Se comprueba si los mensajes de error muestran informacion sin sanetizar tras el input de un usuario.
        * comprobar si se permite el input persistente de un usuario a traves de una aplicacion al servidor obteniendo datos sin sanetizar del servidor.
        * Comprobar si se permite la manipulacion del Document object model.
    2. Qué datos se ven afectados? 
        * Comprobar si mediante los ataques son sustraíbles datos de clientes o de la empresa o sólo de la base de datos 
       
1. **Evaluar el impacto** 
    1. Evaluar el impacto funcional: impacto en la empresa:
        * ¿Cuánto dinero se pierde o está en riesgo?
        * ¿Cuántos proyectos se degradan o están en riesgo?
    2. Evaluar el impacto en la información: impacto en la confidencialidad, integridad y disponibilidad de los datos:
        * ¿Cuán críticos son los datos para la empresa/proyecto?
        * ¿Cuán sensibles son los datos? 
        * ¿Cuál es la situación reglamentaria de los datos? 

1. **Encontrar el vector de ataque**  
    * **XSS reflejado:** El XSS reflejado se produce cuando un usuario envía una solicitud al servidor de una web y acaba ejecutando un script maicioso que  le proporciona al atacante informacion de la victima.
    * **XSS almacenado/persistente:**  este ciberataque tiene lugar cuando una aplicación o una web se encuentra afectada por un software de código malicioso que ha infectado sus respuestas HTTP, el atacannte solo tiene que esperar a que una victima acceda o interaccione con su codigo malicioso  que esta camuflado en la pagina.
    * **XSS basado en DOM:** El DOM (Modelo de Objetos del Documento) se crea cuando alguien abre una página web, es lo que permite a un usuario acceder a todo el contenido de una página sin tener que interactuar con el servidor, este tipo de XSS es muy dificil de detectar para ello es neceario un exahustivo analisis manual de la web para poder obtener respuestas.

### Remediar

**Planificar eventos de remediación** en los que estos pasos se lancen juntos (o de forma coordinada), con los equipos apropiados listos para responder a cualquier interrupción.
**Considere el momento y las compensaciones** de las acciones de reparación: su respuesta tiene consecuencias.

#### Contener

`TODO: Personalizar los pasos de contención, tácticos y estratégicos.`

`TODO: especificar las herramientas y los procedimientos para cada paso, a continuación.`

**La contención de este tipo de ataques es necesaria para evitar que se produzcan problemas con los usuarios que accedan al servidore web y con informacion de los mismos.**

El uso de los CSP esta dirigido a la mitigacion de los ataques XSS y otros ataques que se puedan producir, se basa en la restriccion de scripts e imagenes.

* Limiticaion de informacion mostrada en la pagina
* Bloqueo en el uso de imagenes.
* Bloqueo en el uso de Scripts

#### mitigar

`TODO: Personalizar las medidas de erradicación, tácticas y estratégicas.`

`TODO: Especifique las herramientas y los procedimientos para cada paso, a continuación.`

* Siempre que sea posible, prohíba el código HTML en las entradas. Impedir que los usuarios introduzcan código HTML en las entradas de los formularios es una medida sencilla y eficaz.
* Valide las entradas. Si va a aceptar entradas de formularios, será útil validar los datos para asegurarse de que cumplen criterios específicos.
* Asegure sus cookies. Establecer reglas para sus aplicaciones web que definan cómo se manejan las cookies puede evitar el XSS e incluso bloquear el acceso de JavaScript a las cookies.
* Sanear los datos. Al igual que la validación, el saneamiento se produce después de que los datos se hayan publicado, pero antes de que se ejecuten. Busque herramientas en línea como **HTMLSanitizer** para sanear el código HTML en línea en busca de vulnerabilidades XSS.
* Utilice un cortafuegos de aplicaciones web (WAF). Se pueden crear reglas en un WAF para abordar específicamente el XSS bloqueando las solicitudes anormales del servidor. Un WAF robusto debería ser un componente clave de la estrategia de seguridad de su organización.

* **Vigile posibles ataques recurrentes:** considerar el aumento de la prioridad de las alarmas/alertas relacionadas con este incidente.

#### Referencia: recursos de remediación

`TODO: Especificar los recursos financieros, de personal y logísticos para llevar a cabo la reparación`

1. [Remediacion segun el lenguaje que se utilice](https://crashtest-security.com/xss-attack-prevention/)


### Comunicar

`TODO: Personalice los pasos de la comunicación`.

`TODO: Especifique las herramientas y los procedimientos (incluyendo quién debe participar) para cada paso, a continuación, o remítase al plan general.`

1. Escalar el incidente y comunicarlo a la dirección según el procedimiento
2. Documentar el incidente según el procedimiento
3. Comunicarse con los asesores jurídicos internos y externos según el procedimiento, incluyendo discusiones sobre el cumplimiento, la exposición al riesgo, la responsabilidad, el contacto con las fuerzas del orden, etc.
4. Comunicarse con los usuarios (internos)
    1. Comunicar las actualizaciones de la respuesta a incidentes según el procedimiento.
    2. Comunicar el impacto del incidente **y** las acciones de respuesta al incidente (por ejemplo, contención: "¿por qué está caído el archivo compartido?"), que pueden ser más intrusivas/perturbadoras durante los incidentes de Cross site scripting (XSS)
    3. Comunicar los requisitos: "¿qué deben hacer y no hacer los usuarios?" 
5. Comunicarse con los clientes
    1. Centrarse especialmente en aquellos cuyos datos se han visto afectados
    2. Genere las notificaciones necesarias en función de la normativa aplicable `TODO: Ampliar los requisitos y procedimientos de notificación de la normativa aplicable`.
6. Contactar con los proveedores de seguros
    1. Discutir qué recursos pueden poner a disposición, qué herramientas y proveedores apoyan y pagarán, etc.
    2. Cumplir con los requisitos de presentación de informes y reclamaciones para proteger la elegibilidad
7. Comunicarse con los reguladores, incluyendo una discusión sobre los recursos que pueden poner a su disposición (no sólo una notificación de tipo repetitivo: muchos pueden ayudar activamente)
8. Considerar la posibilidad de notificar e involucrar a las fuerzas de la ley del país en cuestión, ya sean locales o nacionales
9. Comunicarse con los proveedores de seguridad y TI
    1. Notifique y colabore con proveedores de seguridad según el procedimiento
    2. Notificar y colaborar con consultorías de seguridad según el procedimiento
