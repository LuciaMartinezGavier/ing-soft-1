# ✏️ Diseño del software
+ Se realiza luego de que los requerimientos estén definidos y antes de la implementación.
+ Es el lenguaje intermedio entre los requerimientos y el código.
+ Se comienzan a hacer representaciones más concretas.
+ El resultado es un plano del sistema que **satisfaga los requerimientos** y que se utilizará para la implementación.
+ Determina las mayores características de un sistema.
+ Tiene un gran **impacto en testing** y **mantenimiento**.

Lo ideal es que sea **simple** y **entendible**.

## 👾 Niveles en el proceso
1. Diseño arquitectónico:
+ Identifica las componentes necesarias del sistema, su comportamiento y relaciones.
2. **Diseño de alto nivel**:
	* Es la vista de los módulos del sistema.
	* Cuáles son los módulos del sistema, qué deben hacer, y cómo se organizan/interconectan
	* Opciones:
		* [Orientado a funciones](#diseño-orientado-a-funciones)
		* [Orientado a objetos](#diseño-orientado-a-objetos)
3. Diseño detallado o diseño lógico:
	+ Establece *cómo* se implementan las componentes de manera que satisfagan sus especificaciones.
	+ Muy cercano al código: incluye detalles del procesamiento lógico (por ejemplo algoritmo) y de estructuras de datos.

## 🦉 Criterios para Evaluar el Diseño
<!-- SE EVALÚA -->
Los criterios son usualmente subjetivos y no cuantificables. :(  
Principales criterios para evaluar:  
1. **Corrección** 👍🏼
	+ ¿El diseño implementa todos los *requerimientos*?
	+ ¿Es *factible* el diseño dada las restricciones?

2. **Eficiencia** 🏃🏼‍♀️
	* Apropiado *uso de los recursos* del sistema (principalemte CPU y memoria).

3. **Simplicidad**  🧘🏼‍♀
	<!-- Las cosas simples son difíciles de hacer, fáciles de entender. -->
	+ Facilita la *comprensión* del sistema.
	* Facilita el testing, modificación de código, mantenimiento, descubrimiento y corrección de bugs. 🦄🌈

Eficiencia y simplicidad no son independientes => el diseñador debe encontrar un balance.

## 🐦 Principios de diseño
No hay una serie de pasos que permitan derivar el diseño a partir de los requerimientos. Pero existen "ayudas" que son **principios fundamentales** que guían el proceso de diseño:

### 🪆 Particionar y definir jerarquía.
Consiste en dividir el problema en pequeñas partes, simplificando el diseño y facilitando el mantenimiento. Cada parte debe poder *solucionarse*  y *modificarse* independientemente. Aunque no son totalmente independientes: deben *comunicarse* para solucionar el problema mayor. 

La comunicación agrega complejidad: A medida que la cantidad de componentes aumenta, el *costo del particionado* + la *complejidad de la comunicación* también aumenta. Hay que detener el particionado cuando el costo supera al beneficio.

El particionado del problema determina una *jerarquía* de componentes en el diseño. Usualmente la jerarquía se forma a partir de la relación "es parte de".

Relación con la abstracción: `Jerarquía => Abstracción` pero no necesariamente se cumple `Abstracción => Jerarquía`.

%%ACÁ%%

### 🎨 Abstracción
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

### 📦 Modularidad
+ Un sistema se dice modular si consiste de componentes discretas. 
+ Se pueden implementar separadamente.
+ Mínimo impacto
+ Prove la abstracción en el software
+ Mejora claridad de diseño
+ Reduce costos de testing

### ⤵️ Estrategias top-down y bottom-up⤴️ 
Top-down_ el refinamiento de más general a más especifico. Hasta que pueda ser implementado directamente.
Desventajas: se puede asumir que un módulo se pueda hacer pero al final no sea posible.

Bottom up: se usa cuando hay mucho re-uso.

# 🐜 Diseño orientado a funciones
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


# Diseño orientado a objetos