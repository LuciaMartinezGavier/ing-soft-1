1. ¿Qué es la ingeniería del software y cuáñ es su relación con la Ciencia de la
Computación?

La Ingeniería del software es el enfoque sistematico al desarrollo, operación y
mantenimiento de softaware.

Su relación con la Ciencia de la Computación es que es englobada por esta. Es 
necesario producir código entendible y eficiente de buena calidad. Y la
ingeniería del software provee métodos para lograrlo.

2. ¿En qué difieren la ingeniería de software de otras ingenierías más
tradicionales, como la ingeniería mecánica o la ingeniería civil?

El software no se ve modificado por la edad. Con otras ingenierías el tiempo
puede deteriorar los componentes.
Otra diferencia es que lo más costoso en esta industria es el tiempo de la
persona. En otras áreas puede suceder que otros recursos son más costosos.

Se debe mantener para adaptarse a las diferentes necesidades.

3. Si el objetivo principal es hacer al software mantenible, liste algunas de
las cosas que usted haría y algunas de las cosas que no haría durante la
implementación y el testing.

En primer lugar usaría herramientas que sé que también son mantenidas y
portables.

Escribiría una buena documentación y haría el código lo más limpio, modularizado
y entendible posible.

Dejaría espacio para que las estructuras sean modificables y se pueda parametrizar
lo más posible.

4. Liste algunos de los problemas que surgirán si los métodos que usted utiliza
para desarrollar aplicaciones pequeñas son utilizados para desarrollar grandes
aplicaciones.

* Habría poca documentación: por lo tanto sería dificil que otras personas
  comprendan y mantengan el código.
* Estaría poco testeado: Haría falta más unit testing.
* La interfaz sería poco usable para usuarios inexpertos
* Habría mas bugs

5. Los atributos de calidad de software pueden clasificarse en externos
(observables por los usuarios del software) e internos (concernientes a los
desarrolladores). Clasifique los seis atributos de calidad fundamentales
mencionados en el capítulo 1 de “An Integrated Approach to Software Engineering”
(Jalote).

| Externos |   Internos      |
| --- | --- |
| funcionalidad | eficiencia
| confiabilidad  | mantenibilidad|
| usabilidad  | portabilidad |
 
 6. En el capítulo 1 de “An Integrated Approach to Software Engineering”(Jalote)
 se explica que una medida comunmente utilizada para la calidad es defectos por
 KLOC en el software entregado. Para un producto de software dado,
¿cómo puede medirse su calidad? ¿cómo puede ser estimada su calidad antes de ser
entregado?

Se puede medir la calidad de acuerdo a los siguientes parámetros:
**Características generales**
- Correctitud: se comporta según especificaciones
- Confiabilidad: < 1 defecto / KLOC
- Robustez: recuperacion de errores o entradas inesperadas.
- Rendimiento: eficiencia. Minimizar la cantidad de instrucciones por tarea.
- Portabilidad: sin que se modifique
- Interoperabilidad: mediante el uso de estándares. interaccion con otros sistemas.
- Seguridad: No cualquiera pueda meterse

**Propiedades del código**
- Verificabilidad: solo se pueden verificar porciones muy chiquitas.
- Mantenibilidad: adaptar, corregir y perfeccionar
- Reutilización
- Diseño y Experiencia del usuario
- Eficiencia del usuario
- Accesibilidad
- Utilidad
- Privacidad: balance entre la información que se provee
- coherencia: reutilizar habilidades.
- Usabilidad
- Sesgo: evitar ser excluyente en la sociedad


7. Suponga que durante el desarrollo de un proyecto de software se le diera
tiempo extra para mejorar la confiabilidad del producto final. ¿En qué
utilizaría ese tiempo extra?

En testing y en verificar algunas porciones críticas de código

8. ¿De que manera un proceso separado en fases ayuda en la obtención de alta Q
& P (calidad y productividad)? Cuándo parece que estamos haciendo más tareas en
un proceso por fases que en uno ad-hoc?

Ayuda porque se puede hacer testing en cada una de las partes (unit testing) y
corregir errores antes de pasar a la siguiente fase.

Cuando es un proyecto de software de tamaño industrial porque se deben hacer más
tareas como documentar y testear.
 
<!-- TODO: REVISAR -->

9. Entre los atributos de calidad enumerados en el cap´ıtulo 1 de “An Integrated
Approach to Software Engineering” (Jalote) no se encuentra la reutilizabilidad.
Defina este atributo, y describa cu´al es la relaci´on entre ´este y portabilidad.

La reutilización de código se refiere al comportamiento y a las técnicas que
garantizan que una parte o la totalidad de un programa informático existente
se pueda emplear en la construcción de otro programa. De esta forma se aprovecha
el trabajo anterior, se economiza tiempo, y se reduce la redundancia.

Si un código es reutilizable y portable puede usarse en una mayor cantidad de
sistemas