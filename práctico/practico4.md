1. *¿Cuál es, en su opinión, la principal causa de inconsistencias en un diseño?* 
En mi opinión la principal causa es no seguir una metodología ordenada y no ir refinando paso a paso corroborando cada vez la consistencia de las entradas y las salidas.

2. *¿Qué son los patrones de diseño? Describa al menos dos patrones de diseño. 
<!--A qué se refiere con patrones de diseño? -->

**Top-down:**
+ El *refinamiento* de más general a más especifico. Hasta que pueda ser implementado directamente.
+ Ventaja: En cada paso existe una clara imagen del diseño.
+ Desventaja: se puede asumir que un módulo se pueda hacer pero al final no sea posible: *factibilidad desconocida* hasta el final.

**Bottom-up**:
+ Comienza por las componentes de más bajo nivel en la jerarquía.
+ Se usa cuando hay mucho re-uso.

3. *¿Qué es cohesión y acoplamiento?*
Cohesión: Es *intra-modular*. Tiene que ver con la relación de las componentes del mismo módulo. Y determina cuán fuertemente *vinculados* están los elementos de un módulo.
Acoplamiento: El acoplamiento es un concepto *inter-modular*, que determina la forma y nivel de *dependencia* entre módulos.

4. *¿Cómo puede el diseñador evaluar la calidad de sus diseños orientados a objetos?*
El diseño se puede evaluar usando:
+ **Acoplamiento**: Bajo
+ **Cohesión**: Alta
+ **Principio abierto-cerrado**

