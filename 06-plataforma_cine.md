Desarrollo de una plataforma de sitios de cine para canales de tv en América Latina
===

Por Diego Fontdevila, @dfontde y Marcelo Gore, @marcelogore

Tags
---
cine, plataforma, software libre, scrum, tdd, integración continua, errores

Contexto
---
Nuestro cliente buscaba desarrollar una nueva plataforma para los sitios de sus canales de tv de cines y series. A partir de un socio estratégico común, comenzamos a conversar para definir un proyecto conjunto de desarrollo. El sponsor del proyecto era el responsable de cine y series para América Latina, y se encontraba en Miami. Junto al equipo local de cine y series del cliente realizamos un taller de varios encuentros para definir los objetivos y las características básicas del producto, usando casos de uso.


Desafíos
---
Los sitios que el cliente deseaba montar sobre la plataforma abarcaban 18 países de América Latina, dos idiomas (español y portugués), contenidos compartidos (entre varios sitios), workflows de aprobaciones múltiples, requerimientos de escalabilidad exigentes durante eventos de cine y soporte para extensibilidad con módulos específicos (por ejemplo, “votá la película que se va a transmitir”, etc.).
Durante el desarrollo del proyecto tuvimos que facilitar la interacción y alinear los intereses dispares de dos áreas cliente distinta, la de cine y series y la de IT. Para cine y series, el foco estaba en el sitio inicial que estaban intentando desarrollar, y para IT en la creación de una plataforma que facilitara el desarrollo de ese sitio, y de otros, incluyendo a otros clientes dentro de la compañía.

Solución
---
Nuestro equipo decidió experimentar con Scrum como método para el desarrollo del producto, y conformamos el equipo con cinco desarrolladores y un tester, además de un especialista (externo) que había trabajado en el equipo original de desarrollo del producto realizando tareas de optimización de performance.
El primer desafío que encontramos en el arranque del proyecto fue un desfasaje en la definición de los requerimientos que habíamos desarrollado antes de definir el uso de la plataforma Liferay. Decidimos adaptar el lenguaje de dominio (por ejemplo, cambiar sección por página) en nuestros casos de uso, para que primara el lenguaje de dominio de Liferay, aplicando la premisa de utilizar un lenguaje común (ubiquitous language [1]), en el que la herramienta tuviera primera prioridad porque era muy costoso modificarla. El segundo fue reconciliar nuestro modelo de mental de los requerimientos con la exploración de un producto cuyas características detalladas no conocíamos a priori. Para esa tarea, nuestro tester propuso utilizar la técnica de especificar la funcionalidad creando un manual de usuario, que al mismo tiempo nos permitía documentar lo que aprendíamos al explorar Liferay.

Un conflicto interesante fue el causado por un giro en la visión del proyecto, cuando el equipo de cine y series decidió utilizar la plataforma para crear el sitio de una marca nueva, una comunidad de amantes del cine, que no correspondía a uno sus canales de tv como había sido concebido al principio del proyecto. El análisis superficial de los requerimientos parecía indicar que el cambio de dirección no afectaría al proyecto, pero en la práctica implicó que la definición detallada y validación del producto se hiciera mucho más compleja porque la nueva marca no estaba definida y por lo tanto, el desarrollo de la plataforma avanzaba sin concretizar el sitio y sus contenidos.

Cuando hicimos nuestras pruebas tempranas de desempeño y escalabilidad cometimos uno de nuestros errores más pintorescos y vergonzosos. Dejamos las pruebas en manos de nuestro especialista experto quien, por su condición de asesor externo, no conocía en detalle la funcionalidad de la plataforma, y que preparó una mezcla de carga base y picos de carga que parecía significativa pero en realidad resultó insuficiente. Cuando eventualmente tuvimos problemas de escalabilidad en producción, meses después, rastreamos el problema a la configuración de la base de datos, y a partir de ahí a que las pruebas no habían llegado a estresar a la base de datos.

Menor fue el fallo cuando intentamos que el equipo de diseño del cliente realizara sus tareas de producción de imágenes y contenidos en paralelo con nosotros, que usábamos Scrum con iteraciones de 2 semanas. Esto nunca funcionó, hasta que les recordamos que se acercaba la fecha de entrega de la primera versión (release) para producción. Esto no es decir que dejaron el trabajo para último momento, sino que nuestro equipo no tuvo la convicción suficiente ni el empuje necesario para convecer a los demás de la necesidad de fallar tempranamente. Por suerte, la fecha límite logró nuestro cometido por nosotros.

La solución técnica que diseñamos y luego desarrollamos consistía en la implementación y extensión de una plataforma de software libre Java para portales (Liferay), desarrollada como implementación del estándar JSR-168 de JEE. Liferay tenía varias características atractivas:
* Soporte para Content Management Systems configurable, con una implementación por defecto de la Fundación Apache llamada Jackrabbit.
* Infraestructura extensible mediante el agregado de sub aplicaciones web (portlets).
* Configurable masivamente mediante xml.
* La plataforma contaba con pruebas unitarias automatizadas, no así la configuración.

Durante el proyecto, creamos un conjunto de aplicaciones y extensiones (plugins) a Liferay, además de realizar múltiples correcciones de bugs que agregamos a nuestro proyecto como ganchos (hooks) a ser desplegados junto con el resto de los componentes de la aplicación (Liferay proveía soporte para este tipo de extensiones). Cometimos otro error grave (además de las pruebas de escalabilidad inútiles) cuando intentamos utilizar la estructura de módulos funcionales como estructura de subproyectos en el código, con la consecuencia de que la estructura de subproyectos no seguía una nomenclatura homogénea y que nunca tuvimos después tiempo de refactorizar.

Aplicamos Scrum básico sin modificaciones, y creamos nuestro primer tablero sobre hojas de acetato de colores, para poder transportarlo y compartirlo con el equipo cliente durante las reuniones, que tenían lugar en su lugar de trabajo. Intentamos también, casi siempre infructuosamente, compartir un espacio físico con el equipo cliente. Utilizamos varias prácticas ágiles de ingeniería, TDD (Test-driven Development) para los modelos de clases que creamos desde cero, unas pocas (4 o 5 porque eran costosas de crear y ejecutar, además de frágiles) pruebas de usuario en Selenium sobre los flujos clave (por ejemplo, publicación de contenidos) que contra lo que creíamos que sucedería fueron suficientes, puesto que se rompían con cierta frecuencia y nos daban información valiosa. También hicimos múltiples pruebas unitarias que se integraban contínuamente (en un entorno destinado a tal fin) aunque no logramos correr las pruebas de usuario en forma automática porque el servidor consumía más recursos de los que teníamos en ese entorno (obligándonos a correr esas pruebas periódicamente en forma manual).


Conclusión
---
Durante el proyecto aprendimos muchísimo, en particular a disfrutar de practicar Scrum y del delicioso momento de resolver un problema en producción usando nuestra pruebas unitarias creadas con TDD (alguna nos había faltado). Cometimos múltiples errores, algunos graves y otros no tanto, colaboramos cercanamente y pusimos varias versiones sucesivas del sitio en producción. A partir de esta interacción construimos con el área de IT del cliente una relación que duraría muchos años, no así con el área de cine y series, que eligió culpar a la solución de la falta de resultados de negocio.


[1] Evans, Eric, Domain Driven Design, Tackling Complexity in the Heart of Software, Addison-Wesley, 2003.
