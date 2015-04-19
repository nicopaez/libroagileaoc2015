XP para Dinosaurios
======

Por Martín Salías, @MartinSalias


Tags:
---
xp, tdd, pruebas unitarias, pruebas de aceptación, integración continua


Contexto
---

Un cliente me había pedido que lo ayudara a mejorar sus prácticas de desarrollo, desde temas de arquitectura y diseño, como en cuanto a la metodología de trabajo.

Era alrededor del 2007, y en esa empresa la particularidad era que sus desarrollos los hacían en Visual FoxPro (VFP). Más allá de aprovechar mi experiencia previa con esa plataforma para buscar mejores soluciones técnicas en cuanto a la implementación, la intención era ayudarlos a mejorar cómo se organizaban.

La posibilidad de moverse a otro lenguaje o plataforma estaba fuera de discusión, porque además de ser varios equipos que ya estaban muy familiarizados con ese entorno, sus aplicaciones se utilizaban en muchos miles de usuarios del mercado de retail en Argentina, y se utilizaban en computadoras que muchas veces tenían capacidades muy escasas, donde lo auto-contenido y liviano de las aplicaciones VFP resultaba ideal.


Desafío
---

Dada la plataforma en que trabajaban, y que su producto había iniciado en FoxPro para DOS, que no era siquiera orientado a objetos, tenían mucho código "heredado" que era muy poco flexible, propenso a errores, y acarreaban prácticas de desarrollo _cowboy_ que reconocían como problemáticas.

Como me conocían, me pidieron que les explicara los principios y prácticas de XP. El Juego de Planificación y la comunicación permanente con el cliente les parecía bien y los adoptaron gradualmente pero sin titubeos. Al llegar a las prácticas técnicas más específicas, como TDD, Pruebas de Aceptación e Integración Contínua sintieron que por la plataforma en que trabajaban todo ese mundo les estaba vedado.


Solución
---

A pesar de ser ya por esa época una plataforma que no se estaba actualizando, la comunidad alrededor de VFP era y sigue siendo muy activa, y un pequeño grupo con el que yo había colaborado había generado un framework básico para pruebas unitarias llamado FoxUnit; básicamente un port de jUnit, con una interfaz de usuario para ejecutar las pruebas a nivel individual o de fixture.

Con eso empezamos a aplicar TDD en las funcionalidades nuevas, e incluso a romper poco a poco dependencias en el código viejo que teníamos que modificar y agregarle pruebas también.

Ya con más confianza y acostumbrados a historias de usuarios más pequeñas que favorecían commits frecuentes, el equipo se acostumbró a actualizar los cambios del resto todo el tiempo y ejecutar todas las pruebas del proyecto antes de cada cambio, para detectar rápidamente problemas de integración. Estaban listos para automatizar esta parte del trabajo.

Como no había un motor de integración continua que tuviese un soporte específico para VFP, propuse que escribiésemos uno, y aunque al principio les pareció una locura, aceptaron hacer la prueba. Estudiamos el API del repositorio que usaban y pronto encontramos lo que necesitábamos: cómo obtener el número del último commit, y cómo actualizar la copia local.

Escribimos un servicio que verificaba si había un commit nuevo cada cierto intervalo, y en ese caso actualizaba su copia local y a continuación ejecutaba las pruebas de FoxUnit (que tuvimos que retocar para poder ejecutarlas _silenciosamente_).

Cuando empezamos a tener muchos casos de pruebas unitarias que validaban lo mismo con diferentes series de parámetros, noté que eran casos ideales para Fit. Obviamente, Fit no soporta VFP en forma nativa, así que... escribimos el nuestro. Atacamos primero las pruebas tabulares, que reciben una matriz en las que las columnas son los diferentes parámetros de entrada y los valores de salida correspondientes; las filas son los diferentes escenarios a probar. Esto habilitó trabajar con los usuarios directamente, suministrando series de valores para probar. Más tarde imlementamos otro tipo de pruebas que Fit soporta.


Conclusión
---

Muchos equipos, al adoptar prácticas ágiles, sienten que sus plataformas "anticuadas" no les permiten seguir las prácticas técnicas, pero esto es bastante fácil de salvar. Las herramientas básicas para pruebas unitarias, de aceptación, integración continua y demás, son -en su versión más básica- bastante sencillas. Una vez que entendemos la práctica, no es muy duro generar una primera versión, y con diferentes equipos, a partir de esa primer experiencia, pude lograr cosas parecidas en Cobol, Fortran, Clipper y otros entornos más raros.

Por supuesto, la primer versión no será muy seductora, ni tendrá características sofisticadas, pero si cubre la expectativa básica, el valor que nos brinda rápidamente alienta a los equipos a mejorarlas, y ojalá, a compartirlas con la comunidad.
