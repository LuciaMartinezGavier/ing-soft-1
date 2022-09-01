# Diseño detallado
<!--Hasta esta clase entra al parcial-->
Especifica la lógica.

## Process Design Language PLD
Tipicamente se usan lenguajes naturales pero es impreciso, ambiguo,... por ello a veces se usan lenguajes formales, pero son muy complejos.

Idealmente queremos:
+ Sea tan preciso como sea posible
+ No requiera demasiado detalle
+ Sea independiente del lenguaje de implementación: Pero no tanto en la práctica porque nuestro cerebro siempre va a estar resolviendo los problemas con las herramientas (lenguajes) que más usamos. Además es bastante funcional. 
+ Pueda convertirse fácilmente en la implementación

PLD tienen la sintaxis externa de un lenguaje de programación estructurado

Existen algunos automatizadores de PLD, para ciertos lenguajes. Son generadores de código.

PLD es un tipo de pseudocódigo
```PLD
minmax (in file) ARRAY a
DO UNTIL end of input
	READ an item ...
```
### Diseño de la lógica/algoritmo
captura la lógica
	
**Constructurores básicos de PDL**
El criterio de iteración no necesita establecerse formalmente

Paso a paso se va *refinando* del lenguaje natural a la *formalización* de la descripción.
Es importante que el lenguaje natural utilizado sea acotado, por ejemplo evitar tiempos verbales.

## Verificación
+ Recorrido del diseño: 
+ Revisión crítica del diseño:
+ Verificadores de consitencia:

## Métricas 
+ Complejudad ciclomática: chequea condiciones y sentencias de control. Sirve para vender
+ Vínculos de datos: De ello depende el acomplamiento
+ Métricas de cohesión: Si cada ejecución posible del módulo usa todos los recursos del módulo.

