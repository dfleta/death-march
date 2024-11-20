# Ideas principales del capítulo 32 "Frameworks are details" de "Clean Architecture"

El capítulo 32 de "Clean Architecture", titulado "Frameworks Are Details" (Los frameworks son detalles), argumenta que los frameworks de software, aunque útiles, deben considerarse como detalles de implementación y no deben dictar la arquitectura de un sistema. 

El capítulo comienza estableciendo la naturaleza asimétrica de la relación entre un desarrollador y un autor de framework. El desarrollador se compromete significativamente con un framework al usarlo, mientras que el autor del framework no tiene ninguna obligación con el desarrollador.

*  El autor del framework diseña el framework para resolver sus propios problemas, no los del desarrollador. 
*  El framework puede evolucionar en una dirección no deseada por el desarrollador. 
*  Puede surgir un framework mejor y más nuevo.

El capítulo también destaca que los frameworks a menudo violan la Regla de Dependencia. 

*  Los frameworks suelen solicitar que heredemos su código en nuestros objetos de negocio, lo que crea una dependencia no deseada.

La solución propuesta es no casarse con el framework. 

*  Se puede usar un framework, pero sin acoplarse a él. 
*  Se debe mantener el framework detrás de un límite arquitectónico, si es posible, durante el mayor tiempo posible. 

El capítulo utiliza la analogía de "obtener la leche sin comprar la vaca" para ilustrar este punto.

En resumen, el capítulo 32 de "Clean Architecture" aboga por un enfoque cauteloso al usar frameworks. 

*  Se deben considerar como herramientas útiles, pero no como la base de la arquitectura de un sistema. 
*  La arquitectura debe estar impulsada por los casos de uso del sistema, no por los frameworks utilizados para implementarlo. 
*  Esto permite flexibilidad y facilita la adaptación a cambios futuros en la tecnología o en las necesidades del sistema.
