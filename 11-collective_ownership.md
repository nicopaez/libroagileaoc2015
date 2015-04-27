El próximo paso hacia el collective code ownership
===

Por Thomas Wallet, @WalletThomas

Tags
---
collective code ownership, pair programming, scrum


Contexto
---
Un equipo de cinco desarrolladores, evolucionando y manteniendo seis aplicaciones de gestión administrativa para una corporación petrolera. Cada desarrollador con responsabilidad, conocimiento funcional y/o técnico sobre una o dos de las aplicaciones, y en un solo caso dos desarrolladores trabajando sobre la misma aplicación. 

Desafíos
---
Si bien los desarrolladores poseían un gran expertise funcional y/o técnica sobre su aplicación que les permitía ser muy eficientes en su trabajo, el servicio en general estaba muy expuesto a licencias, vacaciones, rotaciones, picos de demanda o incidentes urgentes. Cualquier evento que afectaba el esfuerzo de un desarrollador dejaba tambaleando el servicio e incrementaba la presión sobre el desarrollador involucrado.
Por otro lado, más allá de la gran amistad que existía entre los desarrolladores, la extrema segmentación de las responsabilidades en cada aplicación destruía cualquier intento de construir un equipo de trabajo verdadero, con sentido de pertenencia y colaboración.

El camino a recorrer para revertir esta situación parecía imposible, demasiado largo y siempre aparecían excusas contundentes para mantener el status quo.

Solución
---
Se estaba empezando a implementar **_Scrum_** en el equipo. En las primeras iteraciones, las ceremonias de **_Planificación de iteración_**, **_Sincronización Diaria_** y **_Revisión_** parecían un poco forzadas por el poco involucramiento que tenía cada desarrollador en las aplicaciones que no eran de su responsabilidad. Las primeras **_retrospectivas_** (bien catárticas) dejaron claros los desafíos mencionados previamente, pero más claros aún los frenos, las dificultades y las excusas para no encarar el cambio. 
En una de estas **_retrospectivas_** iniciales, en forma de ejercicio sarcástico y utópico, se construyó entre todos una visión de cómo funcionaría el equipo si todos pudieran mantener y evolucionar el código de cualquiera de las aplicaciones (concepto de Collective Code Ownership), e hicimos foco en los grandes beneficios que representaría para el cliente, el servicio, el equipo y las personas.
Las primeras reacciones eran de risa por el carácter utópico e imposible de esta visión, pero hubo un gran "click" cuando el equipo acordó probar un próximo paso muy acotado que parecía alcanzable sin demasiado esfuerzo en un muy corto plazo. Este primer paso consistía en hacer **_programación de a pares_** entre el responsable de una aplicación y otro desarrollador que no la conocía para resolver un solo incidente durante la próxima iteración. Insistieron en abandonar el experimento si llevaba más de dos horas de esfuerzo. Se revisó con ojos bien críticos el resultado del experimento en la **_retrospectiva_** siguiente: no había sido particularmente bueno pero permitió un pequeño avance hacía la visión acordada.
Este primer paso nos dio pie para probar otro, y otro, y otros a medida que pasaban las iteraciones. Algunos pasos funcionaron muy mal y se abandonaron, otros funcionaron muy bien, pero siempre nos mantuvimos en movimiento con pequeños pasos todo el tiempo.
Los principales experimentos que hicimos fueron:
- CDC (Capacitación Despiadada Continua): espacio fijo de dos horas por semana donde un responsable de aplicación capacitaba a todo el equipo sobre un aspecto funcional o técnico de su aplicación
- DCW (Documentación Cruzada en Wiki): armado de documentación funcional y técnica de una aplicación por desarrolladores ajenos a la aplicación (en Wiki)
- VDC (Visualización de la Dependencia de Conocimiento): durante la Planificación, destacar visualmente el nivel de confianza del equipo para resolver un requerimiento sin el responsable de la aplicación involucrada
- OIE (Observación Interesada del Experto): un desarrollador observa y eventualmente documenta (en Wiki) el trabajo de un responsable de aplicación en la resolución de un incidente
- RAI (Resolución Ajena de Incidente): un desarrollador resuelve un incidente de otra aplicación con coaching del responsable de aplicación
- RAE (Requerimiento Auto-Escuela): elegir un requerimiento **_(Historia de Usuario)_** por iteración a resolver por dos desarrolladores ajenos, con coaching del responsable de aplicación
- PAP (Programación de A Pares): el responsable de la aplicación y un desarrollador ajeno trabajan en una sola maquina (Pair Programming)
- IBM (Incidentes Bien Matados): además de resolver un incidente puntual de una aplicación ajena, trabajar con coaching del responsable de aplicación para extender la mejora a todos los incidentes del mismo tipo en la aplicación y/o en todas las aplicaciones, implementar mejoras para simplificar la resolución futura de incidentes parecidos (por ejemplo mejorando un log), etc.
- EDD (Ensayo De Desastre): probamos sobrevivir durante uno, dos o tres días sin el responsable de aplicación (que está disponible igual por si realmente las cosas se descontrolan)

Conclusión
---
En unos pocos meses, y casi sin darnos cuenta, llegamos al periodo de vacaciones estivales, donde pudimos dejar unas guardias en cada aplicación que funcionaron muy bien aunque los responsables principales de las aplicaciones estaban de licencia. Si bien faltaba mucho camino para recorrer fue un momento clave donde el equipo pudo apreciar el avance logrado de a un pasito a la vez.
No fue todo color de rosa, pero cada uno de estos pasitos permitió acercar este objetivo del Collective Code Ownership que parecía inalcanzable, o por lo menos descartar experimentos para probar otros mejores.
El repago de toda esta inversión de esfuerzo y energía fue más que positivo, ya que de a poco el equipo tenía cada vez más flexibilidad para cubrir ausencia de un responsable de aplicación, cubrir picos de demanda entre varios, más creatividad al trabajar de a varios en los problemas, mejor propagación de las buenas prácticas y de los estándares de código en todo el equipo. Y lo más importante fue el increíble desarrollo de identidad y pertenencia del equipo a través de colaboración y auto-organización constante.
Todo llegó dando un paso a la vez, enfocándose únicamente en el próximo paso, que es el más importante.
