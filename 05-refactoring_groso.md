Refactoring groso
===

Tags
===

Contexto
===
Nos sentamos con Luis, un miércoles, luego de 3 o 4 años de desarrollo. Un brillo inusual y su respiración agitada adelantaba que no era una reunión cualquiera. Nos dijo: muchachos, esta aplicación necesita Roles.

La aplicación Web estaba desarrollada en ASP.NET MVC escrita en C#. Habíamos prestado atención a algunos detalles, por ejemplo: el modelo de objetos habia crecido sin influencias de la base de datos, usamos NHibernate para el mapeo y otros detalles que probaron facilitarnos el trabajo pero, sobre todo, teníamos muchas pruebas automatizadas, más de 1000.

- ¿Qué querés decir con Roles Luis?
- No puede ser que tengamos que cargar a una misma empresa como cliente y como proveedor, quiero que una una empresa pueda ser cliente y proveedor al mismo tiempo, usando el mismo sistema.
- ¡Hmmm! Interesante...

Desafío
===
Cliente y Proveedor eran dos entidades distintas en el modelo y, lógicamente, dos tablas distintas en la base de datos de un software que llevaba años funcionando. efectivamente muchos datos (los de cualquier empresa) estaban duplicados en las tablas y las entidades.

- Perfecto, dijimos, una entidad Empresa, una Cliente y una Proveedor pero, ¿cómo las relacionamos entre si? - Luis nos habia dado una pista, Roles.

La herencia, atractiva a primera vista, puesto que todo Cliente es una Empresa, lo mismo que el Proveedor, serviría para reutilizar lógica pero rápidamente encontraríamos como la reutilización basada en herencia de queda corta respecto de la reutilización basada en composición.

Por otro lado, esa solución, no nos resolvería la carga doble de datos de una empresa que fuese cliente y proveedor a la vez, porque la herencia es solo estructural, a nivel de clases.

La solución basada en roles es distinta, tenemos una entidad autonoma llamada Empresa y otras dos, separadas, que modelan al rol que esa empresa representa en otro contexto, en este caso, el rol Cliente y el rol Proveedor y esos roles se “adjuntan” a una Empresa que deba desempeñarlo.

El desafío es como pasamos desde dos entidades/tablas monoliticas a e entidades/tablas separadas. Todo esto en cambios pequeños que pudieran subirse a producción continuamente, intercalados con otros cambios.


Solución
===
El cambio implicaba cambios en la estructura de la base de datos y sobre la información contenida, por lo que decidimos encarar el cambio en varias etapas pequeñas que pudieran ser completadas en menos de medio dia. Completadas significa que pudieran ser integradas a la rama principal del repositorio y subidos a producción (en caso de ser necesario).

Primer paso
---
Como primer paso definimos la clase abstracta Empresa (que no existía en el modelo anterior) que utilizaríamos como clase base de las clases Proveedor y Cliente, que ya existían.
Pasamos las propiedades y métodos comunes de esas dos entidades a la entidad Empresa. En la base de datos no fue necesario hacer ningun cambió puesto que utilizamos mapeo de herencia de NHibernate (table per concrete class).

Fue un cambio rapido, en unas horas teníamos las mas de mil pruebas automatizadas en verde. Siempre en pequeños pasos de no más de 5 minutos.

Todo fue a la rama principal y estaba en condiciones de ir a producción.

Segundo paso
---
Era hora de que enfretáramos al monstruo temido, la separación de las tablas de la base de datos y de la información.

El próximo paso pequeño era separar las tablas dejando tal cual las entidades. Generamos una migración (el proyecto ya usaba Fluent Migrator) para hacer lo siguiente:
* crear la nueva tabla Empresa
* copiar la información de la empresa desde las tablas Cliente y Proveedor a la tabla Empresa
* generar las relaciones de integridad referencial entre ambas

Por supuesto, también generamos la migración inversa, en caso de que algo saliera mal.

Decidimos no borrar las columnas que ya no se utilizaban en la tabla empresa, 

Alteramos los mapeos de NHibernate (esta vez con table per class) y corrimos las pruebas. Logramos pasar las 1000 pruebas en pocos minutos.

Este cambio, aunque pequeño, era mas complejo puesto que incluía cambios en la base de datos, pero, ya que pasó sin problemas en dos o tres corridas conseutivas, decidimos integrarlo a  la rama principal.

De nuevo pasó sin problemas por el servidor de integración contínua. Estaba en condiciones de ir a producción.

Paso tres
---

Conclusion
===
