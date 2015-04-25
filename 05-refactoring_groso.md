Refactoring groso 
===
Por Carlos Peix, @carlospeix

Tags
===
refactoring, clean code, ood/oop

Contexto
===
La aplicación Web estaba desarrollada en ASP.NET MVC. Desde el principio habíamos prestado atención a algunos detalles. Por ejemplo, el modelo de objetos había crecido sin influencias de la base de datos, usamos NHibernate para el mapeo y otros detalles que probaron facilitarnos el trabajo pero, sobre todo, teníamos muchas pruebas automatizadas, cerca de 1000.

Ese miércoles nos sentamos con Luis, luego de 3 o 4 años de desarrollo (yo como mentor del equipo). Un brillo inusual en sus ojos adelantaba que no era una reunión cualquiera.

Nos dijo: muchachos, esta aplicación necesita Roles.

- ¿Qué querés decir con Roles Luis?
- No puede ser que tengamos que cargar a una misma empresa como cliente y como proveedor, quiero que una empresa pueda ser cliente y proveedor al mismo tiempo.
- ¡Hmmm! Interesante...

Desafío
===
Cliente y Proveedor eran dos entidades distintas en el modelo y, lógicamente, dos tablas distintas en la base de datos. El software que llevaba años funcionando. Efectivamente muchos datos (los de cualquier empresa) estaban duplicados en las tablas y las entidades.

Perfecto, pensamos, una entidad Empresa, una Cliente y una Proveedor pero, ¿cómo las relacionamos entre sí?

Luis nos había dado una pista: Roles.

En primer lugar evaluamos la herencia, atractiva a primera vista, puesto que todo Cliente es una Empresa, lo mismo que el Proveedor. Serviría para reutilizar lógica pero rápidamente encontraríamos como la reutilización basada en herencia se queda corta respecto de la reutilización basada en composición.

Por otro lado, esa solución no nos resolvería la carga doble de datos de una empresa que fuese cliente y proveedor a la vez, porque la herencia es solo estructural, a nivel de clases.

La solución basada en roles es distinta. Tenemos una entidad autónoma llamada Empresa y otras dos, separadas, que modelan el rol que esa empresa representa en otro contexto, en este caso, el rol Cliente y el rol Proveedor y esos roles se “adjuntan” a una Empresa que deba desempeñarlo.

El desafío era como pasar desde dos entidades/tablas monolíticas no relacionadas a un modelo basado en roles. Además, en cambios pequeños que pudieran subirse a producción continuamente, intercalados con otros cambios no relacionados.


Solución
===
El cambio implicaba modificar la estructura de la base de datos y la información contenida, por lo que decidimos encararlo en varias etapas pequeñas que pudieran ser completadas en menos de medio día (“ventana inestable”). Completadas significa que pudieran ser integradas a la rama principal del repositorio y subidos a producción (en caso de ser necesario).

Primer paso
---
Como primer paso definimos la clase abstracta Empresa (que no existía en el modelo anterior) que utilizaríamos como clase base de Proveedor y Cliente, que ya existían.
Pasamos las propiedades y métodos comunes de esas dos entidades a la entidad Empresa. En la base de datos no fue necesario hacer ningún cambió puesto que utilizamos mapeo de herencia de NHibernate (table per concrete class).

Fue un cambio rápido, no llevó más de dos horas en pequeños pasos de cinco minutos verificando que pasaban las más de mil pruebas.

Todo fue a la rama principal y pasó sin problemas en el servidor de integración continua. Estábamos en condiciones de ir a producción.

Segundo paso
---
Era hora de que enfrentáramos la separación de las tablas de la base de datos y de la información.

El próximo paso pequeño era separar las tablas dejando tal cual las entidades (Empresa, Cliente y Proveedor).

Generamos una migración de base de datos (el proyecto ya usaba Fluent Migrator) para hacer lo siguiente:
* crear la nueva tabla Empresa
* copiar la información común en las tablas Cliente y Proveedor a la tabla Empresa
* generar las relaciones de integridad referencial entre estas tablas

Por supuesto, también generamos la migración inversa, en caso de que algo saliera mal.

Decidimos no borrar las columnas que ya no se utilizaban en la tabla empresa. Esto es una práctica usual en migraciones de este tipo difiriendo los cambios irreversibles (borrar columnas y sus datos) a una próxima migración.

Alteramos los mapeos de NHibernate (esta vez con table per class) y corrimos las pruebas. Logramos pasar las 1000 pruebas en pocos minutos.

Este cambio, aunque pequeño, era complejo puesto que incluía cambios en la base de datos, pero, ya que pasó sin problemas en dos o tres corridas consecutivas, decidimos integrarlo a  la rama principal.

De nuevo pasó sin problemas en el servidor de integración continua. Estaba en condiciones de ir a producción.

Tercer Paso 
---
En los pasos anteriores solo hicimos cambios de “infraestructura”, no tocamos sensiblemente el modelo y, por lo tanto, aún no estábamos en condiciones de satisfacer el pedido de Luis.

Decidimos dar un paso pequeño, para variar. En todos los lugares en los que fuese posible usar el tipo Empresa en lugar de Proveedor o Cliente reemplazamos el tipo de la variable.

Este cambio, en términos de Domain Driven Design, significa que utilizamos el tipo correcto en cada “bounded context”. Donde el código interactuaba con empresas independientemente de su condición de proveedor o cliente, usamos el tipo Empresa, en los demás usamos el tipo correspondiente. Como valor agregado, el código quedó más claro y más coherente.

Cuarto Paso (aún pendiente)
---
En este paso el plan es desdoblar a nivel de modelo a la entidad Empresa de las entidades Cliente y Proveedor de manera que estas dos últimas tengan una instancia de Empresa, asociada por composición.

En el caso de que la misma empresa sea Proveedor y Cliente, entonces la instancia de cada uno tendrá una referencia a la misma instancia de Empresa.

Convertir a una empresa en proveedor significa crear una nueva instancia de la clase Proveedor asociada a esa empresa.

Conclusión
===
Creo que este cambio hubiese sido mucho más traumático si no hubiésemos tenido 1000 pruebas automatizadas, tan traumático, que seguramente no lo hubiéramos hecho.

Muchos proyectos de software bien intencionados pero que no tienen una buena cantidad de pruebas automatizadas, postergan este tipo de cambios generando deuda técnica que, poco a poco, termina por paralizarlos.

En mi opinión, todo equipo que decide no escribir y mantener pruebas automatizadas, compromete el proyecto a largo plazo. Probablemente sea debatible si un equipo decide esto o no (mi opinión es que sí), pero eso es material de otro artículo.

Hay otras decisiones que facilitaron el proceso: Integración continua y migraciones de base de datos automatizadas.
