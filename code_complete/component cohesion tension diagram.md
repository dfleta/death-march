# El Diagrama de Tensión en la Cohesión de Componentes: Un Análisis Detallado

![Component cohesion tension diagram](./images/fig%2013.1%20cohesion%20tension%20diagram.png)

El diagrama de tensión presentado en la figura 13.1 de "Clean Architecture" ilustra la interacción dinámica entre tres principios de cohesión de componentes: REP, CCP y CRP.  Estos principios, como se mencionó en nuestro resumen anterior, a menudo se encuentran en conflicto, lo que obliga a los arquitectos a encontrar un equilibrio adecuado en función de las necesidades específicas del proyecto.

## Los Principios en Juego

*   **REP (Principio de Equivalencia de Reutilización/Lanzamiento):** Este principio dicta que la granularidad de la reutilización debe ser igual a la granularidad de la liberación. En términos más sencillos, los componentes que se reutilizan juntos deben liberarse juntos como una sola unidad. Este principio fomenta la creación de componentes más grandes que encapsulan una funcionalidad completa.
*   **CCP (Principio de Cierre Común):** Este principio recomienda agrupar clases que cambian juntas por las mismas razones en el mismo componente. Su objetivo es minimizar el impacto del cambio al aislarlo dentro de un solo componente. Al igual que el REP, el CCP tiende a favorecer componentes más grandes.
*   **CRP (Principio de Reutilización Común):** Este principio, en contraste con los dos anteriores, aboga por componentes más pequeños. Su objetivo es minimizar las dependencias innecesarias entre componentes al agrupar solo las clases que se utilizan juntas.

## El Triángulo de Tensiones

El diagrama de tensión representa estos tres principios como vértices de un triángulo.  Cada lado del triángulo describe el costo de abandonar el principio en el vértice opuesto.

*   **REP vs. CCP:**  Enfocarse únicamente en estos dos principios puede resultar en componentes demasiado grandes, lo que hace que el sistema sea menos flexible y más difícil de mantener. Los cambios, aunque se limiten a un solo componente, podrían tener un impacto significativo debido al tamaño del componente.
*   **CCP vs. CRP:**  Si se priorizan estos dos principios, se corre el riesgo de liberar componentes con demasiada frecuencia.  Aunque los componentes sean pequeños, los cambios en un componente pueden obligar a la liberación de otros componentes que dependen de él.
*   **REP vs. CRP:**  Priorizar estos dos principios puede llevar a que demasiados componentes se vean afectados por cambios simples.  Si bien los componentes son pequeños y reutilizables, la interdependencia entre ellos puede propagar el impacto de los cambios a través del sistema.

## Encontrando el Equilibrio

El arquitecto debe encontrar un punto dentro de este triángulo de tensiones que satisfaga las necesidades del proyecto en cada etapa de su desarrollo. 

*   Al principio, la **capacidad de desarrollo** es primordial, lo que favorece el CCP sobre el REP. Los componentes más grandes y cohesivos permiten cambios rápidos sin preocuparse demasiado por la reutilización.
*   A medida que el proyecto madura y la **reutilización** se vuelve más importante, el equilibrio se desplaza hacia el REP. Los componentes se diseñan para ser reutilizables en otros proyectos, incluso a costa de un mayor impacto del cambio.

## Ejemplos

**Ejemplo 1:** En las primeras etapas del desarrollo de una aplicación web, el equipo puede optar por agrupar todas las clases relacionadas con la interfaz de usuario en un solo componente. Esto cumple con el **CCP** al mantener unidas las clases que cambian juntas. A medida que la aplicación crece y se requieren diferentes tipos de interfaces de usuario (web, móvil, etc.), el equipo puede optar por dividir este componente en componentes más pequeños que se especializan en cada tipo de interfaz, satisfaciendo así el **CRP**.

**Ejemplo 2:** Un equipo que desarrolla una biblioteca de software puede priorizar el **REP** al crear componentes que encapsulan una funcionalidad completa y reutilizable. Sin embargo, al integrar esta biblioteca en un proyecto específico, el equipo puede usar el **CRP** para extraer solo las clases que necesitan, minimizando así las dependencias y la complejidad del proyecto.

## Conclusión

El diagrama de tensión ilustra la naturaleza dinámica de la cohesión de componentes. No existe una única "mejor" manera de organizar los componentes. El arquitecto debe navegar por este triángulo de tensiones, encontrando un equilibrio que satisfaga las necesidades cambiantes del proyecto a lo largo de su ciclo de vida.
