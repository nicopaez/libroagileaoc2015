Aplicación de scrum en un equipo de testing
===

Por Juan José Zapico, @JJZapico

Tags
---
scrum, testing 

Contexto
---

Initech es una empresa que brinda servicios financieros y posee un área de informática muy grande, ya que además del desarrollo y mantenimiento de los sistemas que soportan su propia operatoria, desarrolla los sistemas para otras sociedades del mismo rubro que son las dueñas de la mayor parte de su capital social.

Hacía un par de meses que estaba facilitando la implementación de Scrum en un grupo de desarrolladores que hacía mantenimiento de sistemas existentes. A pesar de que se comenzaron a observar mejoras en el trabajo diario, se hizo evidente un gran problema derivado de la organización en silos que existía en la empresa: las tareas de desarrollo se volvieron más visibles cuando se empezó a aplicar Scrum pero seguía siendo muy poco predecible el momento en que iba a implementarse en producción lo que se estaba programando, porque luego de finalizado el desarrollo el software pasaba a un área de testing donde se hacían pruebas funcionales sobre el mismo, y más adelante pasaba a un área completamente distinta la cual era la encargada de su instalación en los ambientes productivos.

Por cuestiones de política interna y organización de la empresa (que no viene al caso contar en este momento) no se podía avanzar en una implementación de Scrum que integrara a los desarrolladores con los testers. Dada esta imposibilidad de armar equipos multidisciplinarios se propuso trabajar con Scrum, de manera independiente, con el sector de testing, para mejorar ese proceso.

Como el jefe formal del equipo de mantenimiento era el mismo para el equipo de testing, la idea de hacer Scrum en ese segundo equipo surgió de manera casi natural. El lector pensará que teniendo ambos grupos de trabajo el mismo jefe debiera haber sido más fácil integrar un único equipo conformado por los desarrolladores y los testers trabajando de manera colaborativa. Es cierto, en teoría podría haber ocurrido eso, pero creanmé, no se debe subestimar el espesor del tejido burocrático y político de algunas organizaciones...

Desafío
---

Un desafío que tenía como Scrum Master de ambos equipos, el de mantenimiento y el de testing, era que sincronizaran de alguna manera su trabajo, para facilitar la estimación de la potencial puesta en producción de algo que se estaba desarrollando y que luego iba a pasar por testing.

Pero el desafío principal fue aplicar Scrum en un equipo que no era de desarrollo como en los escenarios clásicos que se enseñan cuando se aprende Scrum, sino en un sector que sólo hacía testing. Hacer esto en una organización donde no se fomentaba el trabajo en equipo y era inviable armar equipos multidisciplinarios contribuía a aumentar el desafío.


Solución
---

Dado que ninguno de los miembros del equipo tenía experiencia previa trabajando con Scrum lo primero que hicimos fue una capacitación muy breve para introducirlos al tema, básicamente a
modo de referencia y con la aclaración de que lo que íbamos a hacer se iba a salir de la teoría, adaptando sobre la marcha lo que fuera necesario.

Comenzamos haciendo daily meetings con la fórmula clásica (un timebox de 15 minutos y contestando las preguntas “¿qué hice ayer?”, “¿qué voy a hacer hoy?”, “?tuve algún impedimento?”).

Debido a que en el proceso de testing que se estaba manejando era usual que muchas de las tareas se extendieron por más de un día, las dailies pronto comenzaron a ser reiterativas y sin mucho valor para el equipo, por lo que en una de las primeras retrospectivas ellos mismos propusieron dejar de hacerlas de manera diaria, y se hacían a demanda, cada dos o tres días.
Finalmente se abandonó como práctica, debido a que además el equipo estaba físicamente en el mismo lugar (cuatro personas compartían un box y había dos más en el box contiguo) y tenían una comunicación fluída durante el día, por lo que todos estaban informados permanentemente respecto del estado general del trabajo en curso.

Respecto de las iteraciones, como Scrum Master definí que realizaríamos sprints con una duración de dos semanas. Pensaba que de menos tiempo hubiera resultado impráctico por el overhead (percibido, no necesariamente real) de reuniones respecto del total de tiempo de la iteración. Además consideré que si era de más de dos semanas no hubiera resultado demasiado efectivo respecto de establecer un ritmo de trabajo constante y sustentable a lo largo del tiempo. Dos semanas siempre me ha parecido un tiempo adecuado para balancear flexibilidad con disciplina.

En algunos casos particulares el testing abarcaba más de un sprint (continuaba en el siguiente) pero eran casos excepcionales que trataban de evitarse, y ya se sabía en la planificación que sería así. De todos modos esa situación no alteró el ritmo sustentable que se generó. Mientras escribo esto estoy pensando que para las tareas de testing de algún sistema que se extendían por más de un sprint, la pausa para hacer la retrospectiva y la revisión de la planificación del próximo sprint, funcionaba como el entretiempo de los partidos de fútbol. Los jugadores saben que el partido todavía no terminó, pero tienen un momento para tomar distancia del juego, repasar los aciertos y errores del primer tiempo, planificar la estrategia para el segundo, distenderse y reenfocarse para seguir jugando. Haber respetado siempre el timebox de las dos semanas de cada sprint generó un ritmo sustentable que fue parte importante de esta experiencia.

Para facilitar la sincronización del trabajo del área de desarrollo con el de la de testing, los sprints, que tenían la misma duración, estaban desplazados una semana. Un sprint de testing comenzaba una semana después de la finalización de un sprint de desarrollo, lo que daba tiempo para disponibilizar la versión a testear o tomar contacto con la documentación funcional previamente a realizar la reunión de planning del sprint de testing.

En la planificación del sprint, donde en una aplicación más clásica de Scrum un equipo de desarrollo seleccionaría del backlog las user stories que va a implementar durante la iteración, en nuestro caso el equipo seleccionaba qué sistemas serían testeados durante la iteración.

Teníamos post­-its que identificaban a un sistema y su versión, lo cual era el recordatorio de un documento que recibía el equipo de trabajo al serle solicitado el testing (llamado Solicitud de Testing, donde se detallaba el alcance del testing necesario, los accesos y usuarios a utilizar, la versión del software, etc.).

Utilizamos planning poker con la escala de los tamaños de remeras (S, M, L, XL y XXL) para decidir si el testing de un sistema determinado se podía incorporar a un sprint. Respecto de la efectividad de esta técnica, M., un miembro del equipo, recuerda “las cartas... era muy util comparar los esfuerzos de prueba de los sistemas y cada vez podíamos dar estimaciones más precisas”. El equipo con el tiempo fue ajustando un equivalente a la velocity de los equipos de desarrollo, que hacía muy dinámicas las reuniones de planificación del sprint.

El equivalente al product owner era el jefe de ambos equipos, él era quien priorizaba los sistemas que debían testearse primero, dado que era quien conocía también las necesidades respecto de poner cada cosa en producción, y con quien negociábamos eventuales cambios de alcance (por ejemplo, hacer un smoke test en lugar de una regresión, para incorporar al sprint algo que sino quedaría afuera).

Al principio resultaba un poco incómodo para el equipo realizar las retrospectivas y las reuniones para acordar las tareas a comenzar o continuar en la nueva iteración. Con el transcurso del tiempo esa percepción fue cambiando porque las reuniones de planificación se fueron agilizando en su desarrollo, debido a la experiencia que iba adquiriendo el equipo.

Uno de los miembros del equipo, V., recuerda como una incomodidad del proceso “la duración de las retrospectivas (iniciales); si bien eran necesarias, creo que demandaban mucho tiempo”. Esta misma percepción se había dado en el otro equipo, había una incomodidad referida a “muchas reuniones” o “mucho tiempo de reuniones”, cuando en la práctica las retrospectivas rara vez ocupaban más de una hora y media. Las reuniones de planificación iniciales eran de a lo sumo dos horas y luego se fueron haciendo cada vez más breves. En el total del tiempo del sprint, el tiempo dedicado a reuniones era casi marginal, pero siempre estaba esa queja en los equipos.

Yo creo que la percepción de mucho tiempo en reuniones (cuando creo que objetivamente no era así) estaba causada por años de inercia organizacional donde ir a una reunión era sinónimo de entre cinco y diez personas alrededor de una mesa, hablando de temas que sólo eran de interés para dos o tres de los presentes, lo cual representaba escaso tiempo neto de atención para la mayoría de la gente. El tiempo de las ceremonias de scrum, sin ser extenso, era tiempo de participación directa permanente, algo para lo cual no se estaba entrenado, y podía producir esa percepción de que transcurría mucho tiempo. En el caso del equipo de testing, en la segunda retrospectiva se estableció de manera consensuada por todos que no habría ninguna reunión propia del equipo que fuera de más de 30 minutos y así fue a partir de ese momento.

También en algún momento del proceso hicimos una dinámica donde el equipo se dio la libertad de pensar cómo sería un dar un salto cualitativo más grande en sus tareas, qué cosas serían necesarias para ello, y se elaboró una lista bastante amplia de potenciales recursos que podrían adquirirse o gestionarse para mejorar el proceso de testing de las aplicaciones. Lo importante es que esta lista se hizo sin restringir el pensamiento a lo que se sabía que era posible en la organización, sino que se hizo con total libertad, pensando en una organización ideal.

Respecto de la gestión del backlog, creo importante señalar que manejábamos dos taskboards físicos, con post­-its.

Uno de los tableros era una especie de Kanban, armado en una pizarra en una sala de reuniones, donde teníamos una serie de etapas (columnas) por las que pasaba cada versión de un sistema, desde el desarrollo hasta la puesta en producción. Tenía varios carriles (filas) para los distintos proyectos vigentes y uno para el mantenimiento evolutivo en general. Ese tablero brindaba una visión global que permitía optimizar el testing de sistemas que iban a requerir pasar más de una vez por el sector, porque requerían control de calidad por cambios propios al sistema y por proyectos de actualización de infraestructura, por ejemplo. Brindaba una visión que permitía un planeamiento de tipo estratégico de las actividades, ya que se sabía con tiempo que sistemas estaban por alcanzar la etapa en la que iban a requerir ser testeados y se podían juntar las necesidades de testing de diversos carriles para el mismo sistema. Esto resultaba muy útil para minimizar el cambio de contexto que tenían que hacer los testers cada vez que cambiaba el sistema que tenían que probar.

El otro tablero era más pequeño y estaba en uno de los cubículos del área de trabajo del equipo, armado sobre el propio mobiliario del box. En ese tablero se gestionaban las tareas del sprint, que constituían un workflow bastante repetitivo (revisar la documentación del sistema, actualizar casos de prueba, crear casos nuevos, verificar que el software estuviera instalado, etc.), por lo que cada ítem había sido impreso prolijamente y eran reutilizados, poniendo post­-its pequeños encima para identificar a las personas que estaban tomando la tarea.

Otro problema que tenía el equipo antes de comenzar con este proceso de trabajo era que muchas veces un tester adquiría conocimiento de un sistema determinado y siempre que se requería un nuevo ciclo de testing, ese sistema caía en manos de la misma persona, la que ya tenía conocimiento del mismo, dado que no era posible capacitar a otra persona por los tiempos en los que se necesitaba tener los resultados . Esto desgastaba a la gente, que tenía que testear una y otra vez lo mismo... Para mejorar esa situación copiamos una práctica que se usa en equipos ágiles de desarrollo: pair programming. En este caso lo que se hacía era pair testing, es decir se trataba de que hubiera dos personas testeando juntas, para que el conocimiento fuera compartido y no hubiera personas dedicadas exclusivamente a un sistema determinado. Las parejas iban rotando con el tiempo, para que todos supieran un poco de todos los sistemas.

Finalmente quiero destacar que en un momento del proceso hicimos una actividad donde el equipo definió qué valores los identificaban, para tenerlos de referencia ante situaciones que pudieran poner en peligro la armonía interna o para tener un norte al cual volver cuando la inercia organizacional sacara al equipo del camino de evolución y mejora continua que estaba recorriendo. El resultado de esa actividad arrojó: Compañerismo, Buena predisposición, Coordinación, Diálogo, Cooperación y Respeto.

De todas las prácticas, momentos, acuerdos y situaciones que caracterizaron este proceso, haber llegado a identificar esos valores, donde el compañerismo, el respeto, la buena predisposición y el diálogo tenían la mayor preponderancia, fue clave para el desarrollo de un equipo motivado, auto­-organizado, efectivo, feliz y solidario, cada vez más unido e integrado a partir de ellos.


Conclusión
---

Resultó una experiencia muy gratificante este escenario de aplicación de Scrum en un contexto que no es el usual, porque se logró que un equipo olvidado por la organización, al que casi nadie le prestaba atención, se transformara en un equipo altamente productivo, de personas motivadas que compartían valores que excedían el ámbito laboral. Pude ver en acción el espíritu de Scrum, del que habla Alan Cyment, que logró crear un contexto de abundancia allí donde había escasez.

Me parece que una buena forma de concluir el relato de esta experiencia es recuperar parte de las devoluciones que me enviaron los integrantes del equipo cuando a modo de restrospectiva final les pedí feedback sobre cómo habían vivido el trabajo y cómo habían percibido mi desempeño como facilitador.

Los cito a ellos, comenzando por C., que destaca la organización del trabajo y de las prioridades: “A nivel personal, me pareció sumamente útil. Nunca había trabajado con ninguna metodología definida y me gustó como aprendizaje. Lamento que el contexto no haya sido favorable como para integrar a la gente de desarrollo. Sé que llegué en una etapa en la que [scrum] estaba medio ‘personalizado’ a Testing, pero me sirvió para introducirme en la práctica (...) A nivel equipo, me parece que sirvió para estimar y organizar el trabajo.(...) Se tenía muy claro qué hacer y qué postergar. Llegado el caso de parar una prueba ya se tenía preparado con qué seguir.“ Otro miembro del equipo, A., destacaba, entre otros aspectos positivos, el “tener presente siempre nuestras opiniones”. Para M. la ventaja de trabajar con estas prácticas “es poder detectar los problemas rápido y poder ayudarse entre compañeros a resolverlos, el poder resolver las cosas en tiempo y forma y sentirse respaldado por el grupo (lo que) crea un clima de laburo ideal”.

La evolución que fue haciendo el equipo se resume en el relato personal de G., que cuenta lo siguiente: “cuando llegué (....) y puse el primer papelito lo sentí como una tontería, por otro lado estaba desacostumbrada a tantas reuniones, por eso me daba la sensación de que el cumplir con la metodología de trabajo nos llevaba mas tiempo que el trabajo en sí, entonces no le veía el lado positivo del todo. En el medio hubo un quiebre que me pareció super positivo, cuando comenzamos a ser más flexibles y nos fuimos adaptando, un día nos encontramos haciendo la daily sin que estés vos y creo que todos coincidimos en que realmente nos servía mucho.”

En las películas gran parte de los relatos concluyen con un final feliz para los protagonistas principales. Como esto que narro está tomado de la realidad y no es una película, no se puede guionar un final feliz y las cosas terminan sucediendo de la manera menos pensada. En el caso de este equipo de testing que se volvió muy efectivo aplicando prácticas de scrum, sólo un miembro era empleado en relación de dependencia directa con Initech, todos los demás estaban tercerizados y su empleador era una consultora contratada por la empresa para proveerle recursos humanos con perfil de tester. Un día alguien en las altas esferas de la organización consideró que los contratos que se tenían con esa consultora eran caros y decidió rescindirlos, de manera inmediata, sin ninguna evaluación del impacto para los proyectos y mucho menos para el equipo.

Lamentablemente la burocracia y la política dinamitaron de un día para otro a uno de los equipos de trabajo más efectivos que tenía la compañía.

La historia podría terminar ahí, pero como en muchas películas, lo que parecía el final no lo es, queda una vuelta de tuerca más en el guión, para que el aparente final se resignifique y después de todo aparezca un final feliz. En el caso de este relato, sólo me queda por agregar que los miembros de ese equipo aún nos seguimos viendo periódicamente y se generó una relación de amistad que trascendió el tiempo y espacio que nos tocó compartir laboralmente. Scrum, y sobre todo las retrospectivas, tienen mucho que ver con eso.