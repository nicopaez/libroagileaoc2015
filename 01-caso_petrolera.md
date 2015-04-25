Agilismo en la industria petrolera
======

Por Nicolás Paez, @inicopaez

Tags
----
scrum, alcance variable

Contexto del proyecto
---

Este artículo describe un proyecto en el que participé hace un par de años cuyo objetivo era la informatización del proceso de gestión de licitaciones de una empresa del rubro petrolero. El mismo fue realizado por un equipo de 4 personas en un plazo de 5 meses, trabajando con prácticas ágiles de gestión en el marco de un contrato de alcance variable.

Trabajaba yo en aquel momento en un empresa de desarrollo de soluciones informáticas y nos había contactado una empresa del rubro petrolero para informatizar su proceso de gestión de licitaciones. 

Desafío
----

Hasta aquel momento esta empresa tenía un proceso de licitaciones totalmente manual lo cual implicaba:

* Gran volumen de información en papel
* Alto costo de gestión
* Licitaciones más largas de lo deseable

El objetivo del proyecto era resolver estas cuestiones a partir de la informatización de proceso y adicionalmente lograr:

* Mayor transparencia del proceso de licitaciones
* Mayor visibilidad del proceso de licitaciones
* Métricas del proceso de licitaciones que permitan detectar posibles puntos de mejora


Un detalle técnico relevante era que la solución debía ser implementada sobre una plataforma de gestión de contenidos (CMS) que el cliente ya estaba utilizando.



Solución
---

La venta del proyecto fue llevada a cabo por el gerente del área de desarrollo con mi asistencia, que en aquel momento era líder técnico. Ambos hicimos un primer relevamiento a partir del cual, mi equipo de técnicos y yo hicimos una estimación de esfuerzo. Luego junto con el gerente del área de desarrollo, hicimos un plan tentativo de versiones tomando como base la estimación realizada por el equipo, los riesgos detectados y las fechas deseables que había manifestado el cliente.

Es importante destacar que antes de la presentación formal de la propuesta tuvimos una reunión con el cliente en la que hicimos una presentación informal de la misma, para explicar nuestra forma de trabajo y así asegurarnos que la propuesta escrita fuera bien interpretada. La propuesta tenía algunas particularidades interesantes.

Indicaba explícitamente que tendríamos reuniones semanales para validar el trabajo realizado y así tener feedback temprano y constante. Esto nos permitiría asegurarnos de estar construyendo el producto que el cliente efectivamente necesitaba.
Establecía un alcance variable, lo cual estaba justificado por la incertidumbre que había respecto de cómo se informatizarían ciertas cuestiones del proceso de licitación. Si bien la empresa ya tenía un proceso de licitaciones que venía utilizando, el mismo era manual y su informatización implicaba ciertos cambios en dicho proceso. Algunos de esos cambios era bien claros cómo debían ser, pero había otros que no y que requerían algo de experimentación.
Al mismo tiempo la empresa de desarrollo se comprometía a entregar un sistema informático de soporte a la gestión de licitaciones. No se establecía el alcance completo de ese sistema pero estaba claro que ciertas funcionalidades debían ser cubiertas por el sistema.
El acuerdo tenía un alcance un año, donde los primeros 5 meses estaban destinados a generar la versión inicial de sistema con un equipo a tiempo completo. Los restantes 7 meses se preveía un esquema de soporte y mantenimiento evolutivo con un compromiso de unas 80 horas mensuales.

Aproximadamente 2 semanas después de haber presentado la propuesta, el cliente confirmó que haría el proyecto con nosotros. Para mi satisfacción el equipo encargado de la ejecución estaba conformado por los mismos técnicos que habíamos realizado la estimación inicial. De esta forma, por parte de la empresa desarrollo los involucrados éramos:

* Danilo: gerente de desarrollo y responsable comercial del proyecto
* Ramiro: era el responsable de sistemas del cliente.
* Nicolás (yo): líder técnico del equipo de desarrollo y facilitador del proyecto
* Camilo y Roberto: dos técnicos del equipo de desarrollo

Por parte de la empresa cliente los involucrados eran:

* Felipe: sponsor, era el directivo de la empresa cliente que estaba pagando por el proyecto
* Gabriel: era el responsable del  área de compras y en el contexto del proyecto ocupaba el rol experto de negocio y  product owner
* Manuel y Matías: eran dos empleados del área de compras y como tales eran los futuros usuarios del sistema

La primer iteración fue particular pues duró sólo 1 semana y la dedicamos a algunas típicas del inicio de proyecto como ser configuración de ambientes y capacitación de los expertos de negocio sobre la dinámica de trabajo.

Para la gestión del proyecto utilizamos la herramienta Trac, que era la herramienta estándar utilizada por nuestra empresa de desarrollo en aquel momento. Dicha herramienta brindaba:

* Gestión de tickets y plan de versiones
* **_Wiki_**
* Acceso web
* Almacenamiento de documentos
* Integración con sistema de gestión de código Subversion
* Envío de notificaciones ante determinados cambios en los artefactos del proyecto

El equipo de desarrollo trabajaba en sus oficinas, las cuales se encontraban a 10 minutos de a pié de las oficinas del cliente. En líneas generales la dinámica de trabajo estaba dada por :

* Iteraciones time-boxed (de duración fija) de 2 semanas
* Reuniones presenciales de planificación al comienzo de cada iteración
* Reuniones presenciales de revisión y demostración al final de cada iteración

Dado que la informatización del proceso requería repensar algunos pasos del mismo, era común durante las iteraciones, hacer algunas reuniones adicionales a para ir analizando/definiendo los “nuevos pasos” del proceso de licitación.

Durante las reuniones de planificación se definían las funcionalidades a implementar en la iteración actual y establecían los criterios de aceptación de las mismas. Dichos criterios eran luego refinados y bajados a detalle por los especialistas de negocio en un plazo máximo de 3 días luego de la reunión de planificación. De esta forma el equipo de desarrollo podía contar con los criterios de aceptación antes de finalizar el desarrollo de las stories.

Apenas finalizada una funcionalidad, la misma era validada con un experto del negocio de forma de tal llegar al final de la iteración con la mayor parte de las funcionalidades con cierto grado de validación. La reunión de revisión al fin de la iteración no solía era un momento tenso, pues el cliente ya sabía lo que sea se iba a encontrar. Si una funcionalidad había sido completa, el cliente ya la había visto y había dado algo de feedback. Al mismo tiempo, si alguna funcionalidad no había sido completada, el cliente también lo sabía previamente, pues el equipo comunicaba este cualquier tipo de desvío apenas lo detectaba.

Había un detalle importante respecto de la forma en que el equipo planificaba las iteraciones. Las reuniones de planificación se hacían los lunes de la primera semana de la iteración, preferentemente por la mañana. Las reuniones de revisión de hacían los viernes de la segunda semana de la iteración. Sin embargo, el equipo planificaba de cara a completar el desarrollo el miércoles de la segunda semana de la iteración, lo cual dejaba un día y medio para hacer prueba de regresión y realizar ajustes correspondientes al feedback temprano obtenido de los expertos de negocio.

Tanto la definición del proceso, como las user stories y sus correspondientes criterios de aceptación, eran escritos en la **_wiki_** del proyecto , en muchos casos por los mismos especialistas de negocio y luego eran revisados por algún miembro del equipo de desarrollo. También se pretendía que los expertos del negocio se encargaran de ejecutar las pruebas de aceptación, aunque esto no siempre se lograba.

La fase de desarrollo se completó con algunas variaciones respecto de lo planificado pero sin problemas graves. Una vez que el sistema estuvo productivo, se pasó a mantenimiento tal como estaba previsto.

Conclusión
----

No todos los clientes están dispuestos a trabajar de la forma aquí descrita ni tampoco todos los proyectos lo requieren. Tal vez el proyecto se podría haber realizado utilizando otra dinámica de trabajo, pero en su momento creímos que esa era la forma apropiada de llevar ese proyecto. Hoy en día sigo pensando lo mismo.

Entre los puntos que considero fueron claves para el éxito del proyecto no puedo dejar de mencionar:

* El alto grado de involucramiento de los expertos de negocio
* Comunicación constante
* Confianza del cliente en el equipo y vice versa
* Compromiso y transparencia
