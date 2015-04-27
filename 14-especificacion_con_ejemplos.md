Especificación con ejemplos en la academia 
======
Por Nicolás Paez, @inicopaez

Tags
----
academia, desarrollo dirigido por pruebas, especificación con ejemplos

Contexto del proyecto
---
En la cátedra de Algoritmos y Programación 3 de la Facultad de Ingeniería de la Universidad de Buenos tenemos como principal tema la enseñanza de Programación Orientada a Objetos. Adicionalmente desde el año 2003 hemos ido incluyendo en la materia distintas prácticas de ingeniería surgidas desde el movimiento ágil como ser **_desarrollo dirigido por pruebas_** e **_integración continua_**.

Desafío
----
Como parte de la materia los alumnos deben resolver una serie de trabajos prácticos de programación. Tradicionalmente la consigna de estos trabajos prácticos consistía en un documento de texto y en algún caso algún diagrama. Esto solía generar diversas interpretaciones de la consigna y asociado a ellas, soluciones bastante dispares. 

Solución
---
En 2010 decidimos experimentar cambiando la forma de generar las consignas de los trabajos prácticos. En lugar de entregar simplemente un documento de texto, decimos incluir un conjunto de ejemplos en forma de test automatizados para cada trabajo práctico que ejemplificaran el comportamiento esperado de la pieza de software que los alumnos debían generar. De cara a no ser muy intrusivos en la solución de los alumnos, dichos tests eran de alto nivel y cubrían solamente algunos casos centrales pero que resultaban suficientes para dejar en claro lo esperado, despejando muchas ambigüedades. El experimento fue exitoso ya que además de despejar muchas de las ambigüedades permitió contar con un conjunto de pruebas automatizadas:

* Para los docentes, dichas pruebas eran un forma rápida de verificar que la solución entregada por el alumno satisfacía mínimamente la consigna del trabajo.
* Para los alumnos, los tests funcionaban como una guía que dirigía el desarrollo de sus trabajos.

Conclusión
----
Desde aquel exitoso experimento todos los trabajos prácticos de la materia cuentan con una parte especificada en forma de ejemplos (tests) que describen el comportamiento esperado.
