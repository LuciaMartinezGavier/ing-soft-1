1. _¿Cuál es, en su opinión, la principal causa de inconsistencias en un diseño?_
   En mi opinión la principal causa es no seguir una metodología ordenada y no ir refinando paso a paso corroborando cada vez la consistencia de las entradas y las salidas.

2. \*¿Qué son los patrones de diseño? Describa al menos dos patrones de diseño.
<!--A qué se refiere con patrones de diseño? -->

**Top-down:**

- El _refinamiento_ de más general a más especifico. Hasta que pueda ser implementado directamente.
- Ventaja: En cada paso existe una clara imagen del diseño.
- Desventaja: se puede asumir que un módulo se pueda hacer pero al final no sea posible: _factibilidad desconocida_ hasta el final.

**Bottom-up**:

- Comienza por las componentes de más bajo nivel en la jerarquía.
- Se usa cuando hay mucho re-uso.

3. _¿Qué es cohesión y acoplamiento?_
   Cohesión: Es _intra-modular_. Tiene que ver con la relación de las componentes del mismo módulo. Y determina cuán fuertemente _vinculados_ están los elementos de un módulo.
   Acoplamiento: El acoplamiento es un concepto _inter-modular_, que determina la forma y nivel de _dependencia_ entre módulos.

4. _¿Cómo puede el diseñador evaluar la calidad de sus diseños orientados a objetos?_
   El diseño se puede evaluar usando:

- **Acoplamiento**: Bajo
- **Cohesión**: Alta
- **Principio abierto-cerrado**
