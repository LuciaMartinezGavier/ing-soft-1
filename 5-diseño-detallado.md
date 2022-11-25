# Diseño detallado

Especifica la lógica.

## Process Design Language PLD

Típicamente se usan _lenguajes naturales_ pero son imprecisos, ambiguos, y
conducen a problemas de comprensión. En el otro extremo están los
_lenguajes formales_, pero son muy complejos y tienen demasiado detalle.

Idealmente queremos:

- Sea tan preciso como sea posible
- No requiera demasiado detalle
- Sea independiente del lenguaje de implementación: Pero no tanto en la práctica porque nuestro cerebro siempre va a estar resolviendo los problemas con las herramientas (lenguajes) que más usamos. Además el PLD es bastante funcional.
- Pueda convertirse fácilmente en la implementación

_PLD_ tiene la sintaxis externa de un lenguaje de programación estructurado,
pero el vocabulario de un lenguaje natural.

Existen algunos automatizadores de PLD, para ciertos lenguajes. Son generadores
de código.

PLD es un tipo de pseudocódigo; captura la lógica completa del procedimiento,
aunque revela pocos detalles de implementación.

En PLD, el diseño puede expresarse en el nivel de detalle más adecuado para el
problema y permite un enfoque de _refinamientos_ sucesivos del lenguaje natural
a la _formalización_ de la descripción. Se deben refinar tanto las instrucciones
como los datos.

**Constructores básicos de PLD**

- `IF-THEN-ELSE`
- `CASE`
- `DO (WHILE/UNTIL/FOR) criterio (EXCEPT criterio) sentencia ENDDO`

El criterio de iteración, condiciones y sentencias no necesitan establecerse
formalmente.
Es importante que el lenguaje natural utilizado sea acotado, por ejemplo evitar
tiempos verbales.

## Verificación

El objetivo es mostrar que el diseño detallado cumple con las especificaciones
dadas en el diseño del sistema.

**Métodos de verificación**

- _Recorrido del diseño_: Reunión informal entre diseñador y líder donde el autor _explica_ el diseño paso a paso.
- _Revisión crítica del diseño_: Asegura que el diseño detallado satisface las especificaciones que se propusieron durante el diseño de alto nivel. Se trata de una reunión entre diseñador detallado, diseñador de alto nivel y programador. Se usan listas de control.
- _Verificadores de consistencia_: Si el diseño se realiza en PLD o en algún lenguaje formal, asegura consistencia automáticamente.

## Métricas

- _Complejidad ciclomática_: Mide la complejidad de un módulo. Depende de las condiciones y sentencias de control.
- _Vínculos de datos_: Captura la interacción de datos entre las distintas porciones del software. Estas interacciones determinan el acoplamiento.
- _Métricas de cohesión_: Mide la dependencia de los distintos elementos dentro de un módulo. El valor aumenta si cada ejecución posible del módulo usa todos los recursos del módulo.
