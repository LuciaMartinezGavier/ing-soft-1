# Diseño del software
1. Requerimientos definidos  
2. Antes de la implementación
3. Es el lenguaje intermedio entre los requerimientos y el código.

Lo ideal es que sea **simple** y **entendible**.

Objetivo: crear un plano del sistema.
Determina las mayores características de un sistema.

Tiene un gran **impacto en testing** y **mantenimiento**.

##  Niveles en el proceso
Diseño arquitectónico:
+ Identidica las comonentes neccesarias del sistema, comportamiento y relaciones
Diseño de alto nivel:
* Vista de los módulos del sistema
* Funciones o OO.

Diseño detallado diseño lógico:
Muy cercano al código

## Criterios para Evaluar
<!-- SE EVALÚA -->
1. **Corrección** 
	+ ¿El diseño implementa todos los requerimientos?
	+ ¿Es factible el diseño dada las restricciones?

2. **Eficiencia**
	* Apropiado *uso de los recursos* del sistema.

3. **Simplicidad**
	* Difícil de hacer, fácil de entender.
	* Facilita el testing :D
	* Facilita la modificación del código :D
	* Es difícil cuantificar la "simplicidad". Agarrarse de conceptos como modificabilidad, y facilidad en testing.

## Principios de diseño
"ayudas " o "guías" para crear diseños
**Principios fundamentales**.
1. Partes y jerarquía
2. Abstracción
3. Modularidad

### Particionar y definir jerarquía.
+ Cada parte debe poder *solucionarse* separadamente
+ <!--Completar-->
+ La jerarquía => algo de abstracción pero no necesariamente se cumple abstracción => jerarquía.

### Abstracción
+ **Ocultar** detalles de lo que pasa en niveles más bajos.
+ No hace falta preocuparse por eso.
+ Describe el comportamiento externo.
+ Permite que el diseñador *controle la complejidad*.
1. Abstracción funcional
	+ pre y post condición.
2. Abstracción de datos
	+ una entidad del mundo que provee servicios al entrono
	+ Orientación a objetos?
	+ Ada, C++, Modula, Java

### Modularidad
+ Un sistema se dice modular si consiste de componentes discretas. 
+ Se pueden implementar separadamente.
+ Mínimo impacto
+ Prove la abstracción en el software
+ Mejora claridad de diseño
+ Reduce costos de testing

### Estrategias top-down y bottom-up
Top-down_ el refinamiento de más general a más especifico. Hasta que pueda ser implementado directamente.
Desventajas: se puede asumir que un módulo se pueda hacer pero al final no sea posible.

Bottom up: se usa cuando hay mucho re-uso.

# Diseño orientado a funciones
Un módulo es una **parte lógicamente** separable de un programa.
Es una unidad **discreta** e **identificable**

Criterios para seleccionar módulos que soporten abstracciones bien definidas:
<!-- SE EVALÚA SIEMPRE -->
+ Acoplamiento: 
+ Definición
### Acoplamiento
<!-- Se toma definición y objetivo-->
<!-- Completar -->
queremos que la dependencia sea mínima
Más conexiones => más dependencia.
Objetivo: módulos deben estar tan **débilmente acoplados**
No puede reducirse durante la implementación.
El acoplamiento es un concepto *inter-modular*

Factores:
* Tipo de conexiones entre módulos
* complejidad de interfaces. ¿Estoy pasando solo los parámetro necesarios?
* tipo de flujo de información entre módulos. si se pasan flags que determinan el un caso de la función, es probable que se pueda dividir en dos funciones.

Complejidad y **oscuridad** de las interfaces: no se puede ver el propósito de pasar un parámetro.

* Minimizar la cantidad de interfaces por módulo 
* minimizar la complejidad de cada interfaz

El acoplamiento disminuye si:
+ Solo las  entradas definidas en un módulo son utilizadas por otros
+ la info se pasa exclusivamente a través de parámetros

el acoplamiento depende del **tipo del flujo de información**
control: <!-- Completar-->
datos: <!-- Completar-->
Bajo acoplamiento: las interfaces solo contienen comunicación de datos.
Alto acoplamiento: Las interfaces contienen comunicación de información híbrida 

### Cohesión
Es *intra-modular*. Tiene que ver con la relación de las componentes del mismo módulo.
 Cuán fiertemente vinculados están los elementos de un módulo
#### Tipos de cohesión
<!-- COMPLETAR-->
más débil
1. **Casual**
2. **Lógica**
3. **Temporal**
4. **Procedural**
5. **Comunicacional**
6. **Secuencial**
7. **Funcional**
más fuerte

#### Determinar la cohesión de un módulo.
<!-- COMPLETAR, no se toma -->

## Diagramas de estructura
Presenta una notación gráfica para la estructura de un programa
Representa módulos y sus interconexiones
La invocación de A a B se representa con una flecha.

Se puede realizar una correlación entre código y diagramas de estructura.

### Tipos de módulos
![tipos_de_módulos](...)

No es intención de los diagramas de estructura mostrar la lógica del programa.

La implementación NO debe cambiar la estructura.


