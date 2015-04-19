XP para Dinosaurios
======

Tags:
---


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

Con eso empezamos a aplicar TDD en las funcionalidades nuevas, y 





Conclusión
---
