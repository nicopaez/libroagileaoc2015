Trabajando con Materia Oscura
===

Por Fernando Claverino y Martín Salías, @ferclaverino y @martinsalias

Tags
---
legacy, aplicaciones corporativas, motivación


Contexto
---

Charlando entre los dos, encontramos casos muy similares en experiencias con aplicaciones Enterprise, mantenidas a lo largo de años, por mucha gente diferente, usualmente sin mantener gran consistencia de diseño, y también con gran cantidad de código repetido, incluyendo "sedimentos", o código que está ahí y nadie se anima a sacar, arrastrado de generaciones pasadas, y que es difícil determinar si alguna vez se ejecuta o no.

El caso que le resuena a Fernando es una aplicación de miles reportes ad-hoc procesando información de otros sistemas corporativos. El proyecto trataba de migrar la aplicación (no los reportes) a una nueva tecnología para conseguir mejoras de performance y aumentar la mantenibilidad ya que era una de las herramientas que usaban en la compañía para tomar decisiones.

El caso que recuerda Martín es el core de una compañía de seguros cuya lógica estaba por completo escrito como procedimientos en la base de datos. Otra vez las capas geológicas de código y la cantidad de manos que habían pasado a lo largo del tiempo habían llegado a una situación donde ciertas necesidades del negocio no podían ser siquiera consideradas.

Desafío
---

En ambos casos el temor a romper el código que ya es complejo, hace que en vez de modificar o mejorar lo que está haya una tendencia a agregar condicionales, duplicar código y generalmente lo que queda en desuso no se elimina ni se desactiva, aumentando así la complejidad y generando una espiral negativa.

En estas plataformas que no son nuevas, donde el conocimiento está concentrado en pocas personas y esas personas quizás no pertenecen más al equipo, los nuevos integrantes aprenden mirando el código existente y construyendo código nuevo a partir de su interpretación, perpetuando y hasta empeorando los viejos malos hábitos.

Como resultado las personas hacen lo que pueden, tienen que seguir respetando esos patrones oscuros y no tienen lugar para la innovación o siquiera para el riesgo. La consecuencia de aceptar esto como algo imposible de modificar los sumerge en una especie de pantano de desmotivación. Al sentirse alienados por el código, tampoco generan una dinámica de equipo y lo que suele pasar es que duran poco. Con lo que el ciclo de degradación hace que se pierda la inteligencia colectiva.


Solución
---

En los dos casos que nos tocó (Fer como miembro del equipo y Martín como consultor), lo primero que nos funcionó fue inventar un hack que muestre alguna alternativa, un pequeño haz de luz.

En paralelo a buscar unas estrategias nuevas, también hicimos foco en los dos casos en tratar entender mejor la plataforma, reconocer los patrones en el código, entender qué cosas funcionan bien o mal y desarrollar algunas buenas prácticas y consensuarlas. Eso recupera el espacio de equipo perdido y un poquito de la motivación de trabajar en algo que nos va a facilitar la vida.

A partir de ahí otras alternativas que aplicamos fue desarrollar algunas herramientas faltantes, aunque sea en versiones preliminares que mejoraran el flujo, sobre todo de testing, que nos permitan automatizar algunas pruebas.

Lo primero que pasa en ese estado inicial, es que el equipo siente que hay vida después de la muerte. Y puede empezar a trabajar por lo menos en no seguir sufriendo. Si podemos aplicar la regla del boy scout (dejar el campamento en igual o en mejores condiciones que cuando llegamos), las partes de código que tocamos más frecuentemente irán perdiendo oscuridad poco a poco.

En el caso de la compañía de seguro continuaron con la espiral virtuosa y pudieron comprender las partes más críticas. A partir de entender lo que hace podés empezar a tomar desiciones, mejorarlo, extraer y robustecerlo con más pruebas.


Conclusión
---
Si no salís de ese espiral negativo, sobre todo en los sistemas centrales, lo que termina pasando es que la compañía queda en un callejón sin salida.

Invertir en revertir la situación genera el efecto contrario, los equipos ganan autonomía, motivación, confianza, conocimiento y esto re-habilita nuevas oportunidades para el negocio.