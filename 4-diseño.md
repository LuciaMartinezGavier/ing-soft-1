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
1. **Diseño de alto nivel**:
	* Es la vista de los módulos del sistema.
	* Cuáles son los módulos del sistema, qué deben hacer, y cómo se organizan/interconectan
	* Opciones:
		* [Orientado a funciones](#diseño-orientado-a-funciones)
		* [Orientado a objetos](#diseño-orientado-a-objetos)
2. Diseño detallado o diseño lógico:
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

### 🪆 Partición y jerarquía.
Consiste en dividir el problema en pequeñas partes, simplificando el diseño y facilitando el mantenimiento. Cada parte debe poder *solucionarse*  y *modificarse* independientemente. Aunque no son totalmente independientes: deben **comunicarse** para solucionar el problema mayor.

La comunicación agrega complejidad: A medida que la cantidad de componentes aumenta, el *costo del particionado* + la *complejidad de la comunicación* también aumenta. Hay que detener el particionado cuando el costo supera al beneficio.

El particionado del problema determina una *jerarquía* de componentes en el diseño. Usualmente la jerarquía se forma a partir de la relación "es parte de".

La abstracción es esencial en el particionado del problema, pues `Jerarquía => Abstracción` aunque no necesariamente se cumple `Abstracción => Jerarquía`.

### 🎨 Abstracción
La abstracción de una componente describe el *comportamiento externo* sin dar detalles internos de cómo se produce dicho comportamiento. Es decir, trata de *ocultar* detalles de lo que pasa en niveles más bajos.

Abstracción durante el proceso de diseño:
+ Para decidir como interactúan las componentes sólo el comportamiento externo es relevante. 
+ Permite concentrarse en una componente a la vez.
+ Permite considerar una componente sin preocuparse por las otras.
+ Permite que el diseñador controle la complejidad.
+ Permite una transición gradual de lo más abstracto a lo más concreto.
+ Necesaria para solucionar las partes separadamente.

**Mecanismos comunes de abstracción**  
1. *Abstracción funcional*
	+ Especifica el comportamiento funcional de un módulo.
	+ Los módulos se tratan como funciones de entrada/salida.
	+ Puede especificarse usando pre y post condiciones.
3. *Abstracción de datos*
	+ Una entidad del mundo que provee servicios al entrono.
	+ Los datos se tratan como objetos junto a sus operaciones (orientación a objetos). Y las operaciones definidas para un objetos solo pueden realizarse sobre este objeto.
	+ Lenguajes que soportan abstracción de datos: Ada, C++, Modula, Java

### 📦 Modularidad
Un sistema se dice modular si consiste de *componentes discretas*  que se pueden *implementar separadamente*; donde un cambio a una de ellas tenga *mínimo impacto* sobre las otras.

+ Prove la abstracción en el software.
+ Es el soporte de la estructura jerárquica de los programas.
+ Mejora claridad de diseño y facilita la implementación.
+ Reduce costos de testing, debugging y mantenimiento.

Necesita *criterios de descomposición*: resulta de la conjunción de la *abstracción* y el *particionado*.

### ⤵️ Estrategias top-down y bottom-up⤴️ 
Enfoques para diseñar la jerarquía de componentes.

**Top-down:**
+ El *refinamiento* de más general a más especifico. Hasta que pueda ser implementado directamente.
+ Ventaja: En cada paso existe una clara imagen del diseño.
+ Desventaja: se puede asumir que un módulo se pueda hacer pero al final no sea posible: *factibilidad desconocida* hasta el final.

**Bottom-up**:
+ Comienza por las componentes de más bajo nivel en la jerarquía.
+ Se usa cuando hay mucho re-uso.

# 🐜 Diseño orientado a funciones

## Módulos
Un módulo es una **parte lógicamente** separable de un programa.
Es una unidad **discreta** e **identificable**.

Criterios para seleccionar módulos que soporten abstracciones bien definidas: acoplamiento y cohesión.

<!-- SE EVALÚA SIEMPRE -->
### Acoplamiento
#### Definición
El acoplamiento es un concepto *inter-modular*, que determina la forma y nivel de *dependencia* entre módulos.

**Dos módulos son independientes si cada uno puede funcionar completamente sin la presencia del otro**.

El nivel de acoplamiento se define a nivel de diseño arquitectónico y de alto nivel. Y no puede reducirse durante la implementación.

#### Ventajas de la independencia
Los módulos se pueden implementar, modificar y testear separadamente.

No es necesario comprender todos los módulos para comprender uno en particular: Cuanto más conexiones hay entre dos módulos, más dependientes son uno del otro, es decir, se requiere más conocimiento de un módulo para comprender el otro.

#### Objetivo
Los módulos deben estar tan *débilmente acoplados* como sea posible.

En un sistema *no existe la independencia entre todos los módulos* pues deben cooperar entre sí. Pero queremos que la dependencia sea mínima.

#### Factores que influyen en el acoplamiento
1. **Tipo de conexiones entre módulos**: La *complejidad* y *oscuridad* de las interfaces. Ejemplo: ¿Utilizo solo las interfaces especificadas o también uso datos compartidos?
2. **Complejidad de las interfaces**: ¿Estoy pasando solo los parámetros necesarios? De todas maneras, cierto nivel de complejidad en las interfaces es necesario para soportar la comunicación requerida con el módulo.
3. **Tipo de flujo de información entre módulos**: ¿Estoy pasando parámetros de control (flags)? si se pasan flags que determinan el un caso de la función, es probable que se pueda dividir en dos funciones. Transferencia de información de control permite que las acciones de los módulos dependan de la información; y hace que los módulos sean más difíciles de comprender. 

**El acoplamiento disminuye si**: 
+ Solo las  entradas definidas en un módulo son utilizadas por los otros.
+ La información se pasa exclusivamente a través de parámetros.
+ Sólo se pasa la información estrictamente necesaria.
+ Las interfaces solo contienen comunicación de datos.

**El acoplamiento se incrementa si**:  
+ Se utilizan interfaces indirectas y oscuras.
+ Se usan directamente operaciones y atributos internos al módulo
+ Se utilizan variables compartidas.
+ Se pasan parámetros que contienen más información de la necesaria y hay que parsear (depende del formato).
+ Las interfaces contienen comunicación de información híbrida (datos+control).

### Cohesión
#### Definición
Es *intra-modular*. Tiene que ver con la relación de las componentes del mismo módulo. Y determina cuán fuertemente *vinculados* están los elementos de un módulo.

Consiste en minimizar las relaciones entre los elementos de los distintos módulos y maximizando las relaciones entre los elementos del mismo módulo.

#### Objetivo
Alta cohesión. Usualmente, a mayor cohesión de los módulos, menor acoplamiento.

#### Tipos de cohesión
<!--más débil-->
1. **Casual**: La relación entre los elementos del módulo no tiene significado.
2. **Lógica**: Existe alguna relación lógica entre los elementos del módulo; los elementos realizan funciones dentro de la misma clase lógica.
3. **Temporal**: Los elementos están relacionados en el tiempo y se ejecutan juntos. Ejemplo: inicialización, clean-up, finalización.
4. **Procedural**: Contiene elementos que pertenecen a una misma unidad procedural. Ejemplo: un ciclo o secuencia de decisiones.
5. **Comunicacional**: Tiene elementos que están relacionados por una referencia al mismo datos. Ejemplo: pedir los datos de una cuenta personal y devolver todos los datos del registro.
6. **Secuencial**: Los elementos están juntos porque la salida de uno corresponde a la entrada del otro. Es relativamente buena cohesión y relativamente fácil de mantener, pero difícil de reusar.
7. **Funcional**: Todos los elementos del módulo están relacionados para llevar a cabo una sola función. Ejemplo: Calcular el seno de un ángulo.
<!-- más fuerte -->

#### Determinar la cohesión de un módulo.
<!-- No se toma -->
Describir el propósito del módulo con una *oración*.
Realizar el siguiente test:
+ Si la **oración es compuesta**, tiene **comas** o más de un verbo => el módulo está probablemente realizando más de una función. Probablemente tenga cohesión *secuencial* o *comunicacional*.
+ Si la oración contiene **palabras relacionadas al tiempo** (ejemplo: primero, luego, cuando, después) => probablemente el módulo tenga cohesión *secuencial* o *temporal*. 
+ Si el predicado **no contiene un único objeto específico** a continuación del verbo (como es el caso de “editar los datos”) => probablemente tenga cohesión *lógica*.
+ Palabras como **inicializar/limpiar/...** implican cohesión *temporal*.

Los módulos funcionalmente cohesivos siempre pueden describirse con una **oración simple**.


## Notación y especificación del diseño
Nos interesan el **diseño del sistema** (el producto de la fase) y  el **proceso** que lleva a cabo el diseño.

### Diagramas de estructura
Presenta una notación gráfica para la *estructura de un programa*.
Representa módulos y sus interconexiones. Se puede realizar una correlación entre código y diagramas de estructura.

La invocación de A a B se representa con una flecha; cada flecha se etiqueta con los ítems que se pasan.

**Tipos de módulos**:  
![](https://imgur.com/iqWOFcl.png)

**Iteración y decisión**
![](https://imgur.com/wepHQQy.png)

No es intención de los diagramas de estructura mostrar la lógica del programa. Solo se indican las más importantes.

## Metodología del diseño estructurado
La estructura se decide durante el diseño y la implementación NO debe cambiar la estructura. La metodología de diseño estructurado (SDM: *Structured Design Method*) apunta a controlar la estructura y proveer pautas para auxiliar al diseñador en el proceso de diseño. SDM es una metodología orientada a funciones.

### Pautas
+ Los módulos *subordinados* son los que realizan la mayoría de la computación. El procesamiento real se realiza en los módulos *atómicos* del nivel más bajo.
+ El módulo *principal* se encarga de la coordinación.
+ La *factorización* es el proceso de descomponer un módulo de manera que el grueso de la computación se realice en módulos subordinados.

### Pasos principales
1. [Reformular el problema como un DFD](#reformular-el-problema-como-un-DFD)
2. [Identificar las entradas y salidas más abstractas](#identificar-las-entradas-y-salidas-abstractas)
3. [Realizar el primer nivel de factorización](#factorizar1)
4. [Factorizar los módulos de entrada, de salida, y transformadores](#factorizar2)
5. [Mejorar la estructura (heurísticas, análisis de transacciones)](#mejorar-la-estructura)

#### Reformular el problema como un DFD
#### Identificar las entradas y salidas abstractas
#### Factorizar1
#### Factorizar2
#### Mejorar la estructura

## Verificación

## Métricas

# Diseño orientado a objetos