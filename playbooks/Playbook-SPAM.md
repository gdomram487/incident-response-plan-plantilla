## Playbook: SPAM

### Identificar

`TODO: Ampliar los pasos de la identificación, incluyendo las herramientas y estrategias clave, para el incidente.`

1. **Identificar el ataque** 
    1. Para identificar estos ataques se debe ver la procedencia del correo y las posibles URL camufladas.
    2. Utilizar herramientas para el bloqueo de mensajería de SPAM.
    3. Realizar análisis de correos todas las semanas.

1. **Determinar el alcance**
    1. ¿Se puede puede recibir correos de SPAM en nuestro servidor de correos?
        * Intentar enviar un correo de SPAM nosotros mismos y ver si realmente llegan al servidor de correos.
        * Ver si el servidor no te lo expresa como SPAM el mensaje enivado.
       
1. **Evaluar el impacto** 
    1. Evaluar el impacto funcional: impacto en la empresa:
        * ¿Cuánto dinero se pierde o está en riesgo?
        * ¿Cuántos proyectos se degradan o están en riesgo?
    2. Evaluar el impacto en la información: impacto en la confidencialidad, integridad y disponibilidad de los datos:
        * ¿Cuán críticos son los datos para la empresa/proyecto?
        * ¿Cuán sensibles son los datos? 
        * ¿Cuál es la situación reglamentaria de los datos? 

1. **Encontrar el vector de ataque**  
    * **Spam por correo electrónico:** el spam más habitual. Inunda la bandeja de entrada y distrae al usuario de los mensajes que sí le interesan. Dé por seguro que puede ignorarlo completamente.
    * **Spam SEO:**  también es conocido como «spamdexing» y es el abuso de los métodos de optimización de los motores de búsqueda (SEO) para mejorar la valoración de búsqueda del sitio web del spammer. 
    * **Spam de redes sociales:** a medida que Internet se va haciendo más social, los spammers tratan de aprovecharse para propagar su spam mediante cuentas falsas de usar y tirar en redes sociales populares.
    * **Spam móvil:** spam en formato SMS. Además de mensajes de texto, algunos spammers utilizan también notificaciones push para llamar la atención sobre sus ofertas.

### Remediar

**Filtros Antispam y Listas Negras** Existen utilidades que filtran los mensajes de spam en función de unas reglas, o simplemente comprobando listas negras. Algunas de estas utilidades se encuentran en el propio servidor de correo, evitando que el usuario tenga que preocuparse de esto.
**Políticas de Privacidad y Uso** Lee con calma la política de privacidad de aquellos sitios donde tengas que introducir tu e-mail, jamás le brindes tu email a quien no tenga política o sea capaz de brindarle tu email a un tercero.

#### Contener

`TODO: Personalizar los pasos de contención, tácticos y estratégicos.`

`TODO: especificar las herramientas y los procedimientos para cada paso, a continuación.`

**La contención de este tipo de ataques es necesaria para evitar que se produzcan problemas con los correos de los usuarios.**

* Lo primero que nos recomiendan los expertos en ciberseguridad es tener dos cuentas de correo electrónico. Una para uso privado con contactos fiables (personas conocidas o para el ámbito laboral) y otra pública para registrarte en foros, publicar en webs, suscribirte a listas de correo etc.
* Utiliza un Software Antispam. Se trata de hacer uso de programas que examinan los correos electrónicos que llegan a tu bandeja de entrada para clasificarlos en “deseados” y “no deseados”. 
* Date de baja. Otra alternativa muy sencilla es bajar hasta el final del correo basura para cancelar la subscripción.
* No compartas cadenas. Llamamos “cadenas” a aquellos mensajes masivos que te recomiendan que reenvíes este mensaje para conseguir un objetivo X. ¡Evita esta práctica! Lo único que lograrás es proporcionar la dirección de tus contactos para ser, a posteriori,víctima de nuevos correos spam.


#### mitigar

`TODO: Personalizar las medidas de erradicación, tácticas y estratégicas.`

`TODO: Especifique las herramientas y los procedimientos para cada paso, a continuación.`

* Borra tu correo de la red. Escribte tu correo en Google y averigua en qué sitios se ha escrito tu dirección de e-mail con el arroba y trata de borrarla o solicitar al propietario de la página que la borre.
* No pongas la dirección con el @. Hay algunas fórmulas habitualmente aceptadas para dar el correo online sin escribirlo entero para que aparezca el enlace. 
* Usa un formulario de contacto. En vez de poner el nombre directo de tu correo en la web, algunas empresas optan por habilitar sólo una página de contacto en su página mediante un formulario en HTML + script en PHP o cualquier plugin útil para WordPress o Joomla.
* No des tu dirección siempre. Hay una mala práctica en Internet al dialogar con alguien en un foro que consiste en darle el e-mail para que puedan hablar por privado.
* Usa un buen servidor de correo. Gmail es uno de los que mejor tratan el SPAM (a diferencia de Yahoo), pero si no quieres usarlo como correo corporativo de la empresa, puedes crear un redireccionamiento desde el correo que tienes en el hosting hasta tu correo personal.


### Comunicar

`TODO: Personalice los pasos de la comunicación`.

`TODO: Especifique las herramientas y los procedimientos (incluyendo quién debe participar) para cada paso, a continuación, o remítase al plan general.`

1. Escalar el incidente y comunicarlo a la dirección según el procedimiento.
2. Documentar el incidente según el procedimiento.
3. Comunicarse con los asesores jurídicos internos y externos según el procedimiento, incluyendo discusiones sobre el cumplimiento, la exposición al riesgo, la responsabilidad, el contacto con las fuerzas del orden, etc.
4. Comunicarse con los usuarios (internos)
    1. Comunicar las actualizaciones de la respuesta a incidentes según el procedimiento.
    2. Comunicar el impacto del incidente **y** las acciones de respuesta al incidente (por ejemplo, contención: "¿por qué está este correo SPAM en mi bandeja?").
    3. Comunicar los requisitos: "¿qué deben hacer y no hacer los usuarios?" 
5. Contactar con los proveedores de seguros
    1. Discutir qué recursos pueden poner a disposición, qué herramientas y proveedores apoyan y pagarán, etc.
    2. Cumplir con los requisitos de presentación de informes y reclamaciones para proteger la elegibilidad
6. Comunicarse con los reguladores, incluyendo una discusión sobre los recursos que pueden poner a su disposición (no sólo una notificación de tipo repetitivo: muchos pueden ayudar activamente)
7. Considerar la posibilidad de notificar e involucrar a las fuerzas de la ley del país en cuestión, ya sean locales o nacionales
8. Comunicarse con los proveedores de seguridad y TI
    1. Notifique y colabore con proveedores de seguridad según el procedimiento
    2. Notificar y colaborar con consultorías de seguridad según el procedimiento
