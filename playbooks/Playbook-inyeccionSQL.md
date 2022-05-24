## Playbook: Inyección SQL

**Identificar, remediar (contener, erradicar) y comunicar en paralelo.**

Asigne pasos a individuos o equipos para que trabajen simultáneamente, cuando sea posible; este Playbook no es puramente secuencial. Utilice su mejor criterio.

### Identificar

`TODO: Ampliar los pasos de la identificación, incluyendo las herramientas y estrategias clave, para el incidente.`

1. **Identificar el ataque** 
    1. Realizar una detección temprana de ataques inyecciones SQL:
        * Utilizar herramientas tipo Dynamic Application Security Testing (DAST)
        * Realizar pruebas de caja negra en una nueva versión de la aplicación web durante las fases de desarrollo y comprobaciones
    1. Otros métodos de detectar el ataque:
        * Revisar regularmente los registros del servidor
        * Monitorizar los errores de la base de datos
        * Utilizar cortafuegos de aplicaciones web (WAF) para inspeccionar peticiones HTTP en busca de comandos SQL

1. **Determinar el alcance:**
    1. Es posible cualquier tipo de inyección? 
        * Realizar test unitarios durante el desarrollo con los diferentes tipos de ataque SQL 
        * Poner en producción la aplicación en entornos virtuales para medir su resiliencia ante ataques mediante pruebas exhaustivas
    1. Qué datos se ven afectados? 
        * Comprobar si mediante los ataques son sustraíbles datos de clientes o de la empresa o sólo de la estructura de la base de datos 
       
1. **Evaluar el impacto** para priorizar y motivar los recursos
    1. Evaluar el impacto funcional: impacto en la empresa o en la misión:
        * ¿Cuánto dinero se pierde o está en riesgo?
        * ¿Cuántas (y cuáles) misiones se degradan o están en riesgo?
    1. Evaluar el impacto en la información: impacto en la confidencialidad, integridad y disponibilidad de los datos:
        * ¿Cuán críticos son los datos para la empresa/misión?
        * ¿Cuán sensibles son los datos? 
        * ¿Cuál es la situación reglamentaria de los datos? 

1. **Encontrar el vector de infección.**  
    * Ataques por error: es el ataque más común y el más fácil de explotar ya que es la propia aplicación la que va indicando los errores de la base de datos al realizar las diferentes consultas. Con este error es muy sencillo obtener cualquier dato de la base de datos ya sean estructura, tablas, campos e incluso los datos almacenados.
    * Ataques por unión: este tipo de ataque consiste en que el portal devuelva un resultado, y a partir de ahí, añadir al resultado original el resultado de otra query de tal forma que se muestren junto con los datos del portal, los datos sensibles del mismo que no debería de poderse obtener.
    * Ataques ciegos: es el ataque más complicado y el más avanzado, es la última opción cuando ninguno de los ataques anteriores funcionan. En este caso hay que ser muy creativos y se deben de realizar preguntas a la base de datos mediante booleanos, es decir, verdadero o falso, todo aquello que se necesite saber. Aquí podemos separar en dos tipos más:
        * Basado en condicionales: si la consulta está bien mostrará los resultados, si no no mostrará nada.
        * Basado en tiempo: si la consulta es correcta devolverá los resultados a los n segundos, si no no mostrará nada.

### Remediar

**Planificar eventos de remediación** en los que estos pasos se lancen juntos (o de forma coordinada), con los equipos apropiados listos para responder a cualquier interrupción.
**Considere el momento y las compensaciones** de las acciones de reparación: su respuesta tiene consecuencias.

#### Contener

`TODO: Personalizar los pasos de contención, tácticos y estratégicos.`

`TODO: especificar las herramientas y los procedimientos para cada paso, a continuación.`

**La contención rápida es muy importante en este tipo de ataques, para evitar la posible inyección a más de una base de datos en caso de tener varias y para eliminar persistencia del atacante en el sistema.**

Las cuarentenas (lógicas, físicas o ambas) evitan la propagación desde los sistemas infectados y evitan la propagación hacia los sistemas y datos críticos. Las cuarentenas deben ser exhaustivas: incluir el acceso a la nube/SaaS, el inicio de sesión único, el acceso a sistemas como el ERP u otras herramientas empresariales, etc.

* Poner en cuarentena los sistemas infectados
* Poner en cuarentena a los usuarios y grupos afectados.
* Poner en cuarentena las bases de datos compartidas (no sólo los servidores infectados conocidos; proteja también las bases de datos no infectadas)
* Bloquear los dominios y direcciones de comando y control.

`TODO: Considere la posibilidad de automatizar las medidas de contención mediante herramientas de orquestación.`

#### Erradicar

`TODO: Personalizar las medidas de erradicación, tácticas y estratégicas.`

`TODO: Especifique las herramientas y los procedimientos para cada paso, a continuación.`

* Sanitizar entradas de datos en la aplicación, tanto en el frontend como en el backend, por ejemplo, mediante expresiones regulares, límite de carácteres y carácteres que no se pueden escribir
* Utilizar sentencias preparadas y parametrizadas en el código de la aplicación web
* Verificar los datos que se introducen en las entradas antes de enviarse
* Asignar mínimos privilegios a los usuario que se conectan a la base de datos
* Mostrar sólo mensajes de error genéricos
* Almacenar la información de la base datos de forma segura, por ejemplo, las contraseñas hasheadas

* **Vigile posible reinfección:** considerar el aumento de la prioridad de las alarmas/alertas relacionadas con este incidente.

#### Referencia: recursos de remediación

`TODO: Especificar los recursos financieros, de personal y logísticos para llevar a cabo la reparación`

### Comunicar

`TODO: Personalice los pasos de la comunicación`.

`TODO: Especifique las herramientas y los procedimientos (incluyendo quién debe participar) para cada paso, a continuación, o remítase al plan general.`

1. Escalar el incidente y comunicarlo a la dirección según el procedimiento
1. Documentar el incidente según el procedimiento
1. Comunicarse con los asesores jurídicos internos y externos según el procedimiento, incluyendo discusiones sobre el cumplimiento, la exposición al riesgo, la responsabilidad, el contacto con las fuerzas del orden, etc.
1. Comunicarse con los usuarios (internos)
    1. Comunicar las actualizaciones de la respuesta a incidentes según el procedimiento
    1. Comunicar el impacto del incidente **y** las acciones de respuesta al incidente (por ejemplo, contención: "¿por qué está caído el archivo compartido?"), que pueden ser más intrusivas/perturbadoras durante los incidentes de inyección SQL
    1. Comunicar los requisitos: "¿qué deben hacer y no hacer los usuarios?" 
1. Comunicarse con los clientes
    1. Centrarse especialmente en aquellos cuyos datos se han visto afectados
    1. Genere las notificaciones necesarias en función de la normativa aplicable `TODO: Ampliar los requisitos y procedimientos de notificación de la normativa aplicable`.
1. Contactar con los proveedores de seguros
    1. Discutir qué recursos pueden poner a disposición, qué herramientas y proveedores apoyan y pagarán, etc.
    1. Cumplir con los requisitos de presentación de informes y reclamaciones para proteger la elegibilidad
1. Comunicarse con los reguladores, incluyendo una discusión sobre los recursos que pueden poner a su disposición (no sólo una notificación de tipo repetitivo: muchos pueden ayudar activamente)
1. Considerar la posibilidad de notificar e involucrar a las fuerzas de la ley del país en cuestión, ya sean locales o nacionales
1. Comunicarse con los proveedores de seguridad y TI
    1. Notifique y colabore con proveedores de seguridad según el procedimiento
    1. Notificar y colaborar con consultorías de seguridad según el procedimiento

### Recuperar

`TODO: Personalizar los pasos de recuperación.`

`TODO: Especifique las herramientas y los procedimientos para cada paso, a continuación.`

* Reconstruir los sistemas infectados a partir de medios conocidos y buenos
* Restaurar a partir de copias de seguridad conocidas y limpias.
* Confirmar que los parches se despliegan en todos los sistemas (priorizando los sistemas, los SO, el software, _etc._).