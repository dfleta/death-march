# Resumen del Capítulo 13 "Component Cohesion" de "Clean Architecture"

El capítulo 13 de "Clean Architecture", titulado "Component Cohesion" (Cohesión de componentes), presenta tres principios que guían la organización de las clases y módulos en componentes:

*   **REP (Principio de equivalencia de reutilización/lanzamiento):** La unidad de reutilización es la unidad de lanzamiento.  Este principio establece que un componente debe ser liberado como una sola unidad, y que todas las clases dentro del componente deben ser reutilizables juntas. Si una clase dentro de un componente se cambia, todo el componente debe ser relanzado.
*   **CCP (Principio de cierre común):** Reúne en un mismo componente aquellas clases que cambien por los mismos motivos y al mismo tiempo. Separa aquellas clases que cambien en momentos distintos o por motivos distintos. Este principio busca agrupar clases que tienden a cambiar juntas por las mismas razones. Si una clase necesita ser modificada, es probable que las otras clases en el mismo componente también necesiten ser modificadas.
*   **CRP (Principio de reutilización común):** No obligues a los usuarios de un componente a depender de cosas que no necesitan. Este principio busca minimizar las dependencias innecesarias entre componentes. Solo las clases que se usan juntas deben estar en el mismo componente.

## Relación entre los principios

Estos tres principios están en tensión entre sí. El **REP** y el **CCP** tienden a crear componentes más grandes, mientras que el **CRP** impulsa la creación de componentes más pequeños.

*   El **REP** busca maximizar la reutilización, lo que puede llevar a incluir muchas clases en un solo componente.
*   El **CCP** busca minimizar el impacto del cambio, lo que también puede llevar a incluir muchas clases en un solo componente para que los cambios afecten solo a un componente.
*   En contraste, el **CRP** busca minimizar las dependencias, lo que lleva a crear componentes más pequeños y especializados.

## Diagrama de tensión

![Cohesion principiles tension diagram](./images/fig%2013.1%20cohesion%20tension%20diagram.png)


El capítulo presenta un diagrama de tensión (Figura 13.1) para ilustrar la interacción entre estos principios. El diagrama muestra que un buen arquitecto busca un equilibrio entre los tres principios.

*   Al inicio de un proyecto, el **CCP** es más importante que el **REP**, ya que la capacidad de desarrollo es más importante que la reutilización. 
*   A medida que el proyecto madura y se reutiliza en otros proyectos, el equilibrio se desplaza hacia el **REP**.

## Conclusión

La cohesión de componentes es un aspecto crucial del diseño arquitectónico. Los principios **REP**, **CCP** y **CRP** proporcionan una guía para organizar las clases y módulos en componentes de manera que se equilibren las necesidades de reutilización, desarrollo y mantenimiento.
