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
	+ Es más general que el diseño de alto nivel.
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
<!--Tipos de acoplamiento: SE EVALÚA-->
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
<!--Se evalúa teóricamente, no los usamos mucho en la práctica -->
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
+ La *factorización* es el proceso de *descomponer* un módulo de manera que el grueso de la computación se realice en módulos subordinados.

### Pasos principales
<!-- Se evalúa. Nombre, descripción. No prácticamente. -->
<!-- LEER EN EL JALOTE-->
1. [Reformular el problema como un DFD](#reformular-el-problema-como-un-DFD)
2. [Identificar las entradas y salidas más abstractas](#identificar-las-entradas-y-salidas-abstractas)
3. [Realizar el primer nivel de factorización](#factorizar1)
4. [Factorizar los módulos de entrada, de salida, y transformadores](#factorizar2)
5. [Mejorar la estructura (heurísticas, análisis de transacciones)](#mejorar-la-estructura)

#### Reformular el problema como un DFD
Se toma el *flujo de datos* de todo el sistema propuesto. Y se plantea un DFD, que proveerá una visión de alto nivel del sistema.

Si bien *se ignoran aspectos procedurales* y la *notación es la misma*, el *propósito* del DFD es *diferente* al del de análisis de requerimientos. (No nos interesa entender el problema, sino empezar a desarrollar la solución).

#### Identificar las entradas y salidas abstractas
**MAI** (*Most Abstract Input*)
+ La *MAI* consiste en la *entrada* y todas las *transformaciones* que se le aplican a la misma para que esté en un *formato adecuado*.
+ Elementos de datos en el DFD que están más distantes de la entrada real, pero que aún puede considerarse como entrada.
+ Podrían tener poca semejanza con la entrada real.

**MAO** (*Most Abstract Output*)
+ Es dual a la *MAI*.
+ Elementos de datos en el DFD que están más distantes de la salida real, pero que aún puede considerarse como salida.

Determinar las *MAI* o las *MAO* es subjetivo, es decir, representan un juicio de valor.

Las **transformaciones centrales** entre la *MAI* y la *MAO* es donde el sistema realmente "hace algo". Y estos se concentran en la transformación sin importar el formato/validación/etc de las entradas y salidas.

Entonces, el primer diseño básico consiste en:

| MAI     | → | Sistema intermedio | → | MAO    |
| ------- | - | -------------------| - | ------ |
| entrada | → | transformaciones   | → | salida |

#### Factorizar1
**Realizar el primer nivel de factorización**

Hay que subdividir en:
1. *Modulo principal*: Módulo coordinador
2. *Módulos subordinados*
	1. De entrada: responsables de entregar las entradas lógicas
	2. Transformadores: consumen las entradas lógicas y obtienen las salidas lógicas
	3. De salida: Consumen las salidas lógicas
	+ Cada uno de los tres tipos de módulos pueden diseñarse separadamente y son independientes.

#### Factorizar2
**Factorizar los módulos de entrada**
+ El transformador que produce el dato de MAI se trata ahora como un transformador central.
+ Se repite el proceso del primer nivel de factorización considerando al módulo de entrada como si fuera el módulo principal.
+ Usualmente no debería haber módulos de salida.

**Factorizar los módulos de salida**
+ Módulos subordinados: transformador y módulos de salida.
+ Usualmente no debería haber módulos de entrada.

**Factorizar los transformadores centrales**
+ Utilizar un proceso de refinamiento top-down.
+ El objetivo es determinar los subtransformadores que compuestos conforman el transformador.
+ Graficar DFD.
+ Repetir hasta alcanzar los módulos atómicos.

#### Mejorar la estructura
**Mejorar la estructura (heurísticas, análisis de transacciones)**
<!-- No está en el libro -->
Esta etapa consiste en hacer las *modificaciones finales*. 
Dada una serie de heurísticas se determina si la estructura está bien hecha. Y si no lo es, modificar.

El objetivo es tener el menor grado de acoplamiento y tener mucha cohesión en los módulos.

**Heurísticas** "Rules of thumb"
1. *Tamaño del módulo*: Indicador de la complejidad del módulo. Examinar los módulos con muy pocas líneas o con más de 100 líneas.
2. *Cantidad de flechas de salida y entrada*: La primera no debería exceder las 5 o 6 flechas; la segunda debería maximizarse.
3. *Alcance del efecto de módulo*: Los módulos afectados por una decisión en este módulo (pueden ser más profundo que solo los inmediatos). 
4. *Alcance del control de un módulo*: A dónde van las flechas. Todos los subordinados.

Lo ideal es que `efecto == control`. Mientras menos se propaguen los problemas, mejor. Una decisión debe tener efecto solamente en los módulos subordinados.

## Verificación
**Objetivo:** Asegurar que el diseño implemente los requerimientos (corrección). <!-- y completitud?--> Hacer análisis de desempeño, eficiencia, etc.

Si se usan lenguajes formales para representar el diseño => existen *herramientas* que asisten para el análisis... Se usan también *listas de control*.

La calidad del diseño se completa con una buena modularidad (*bajo acoplamiento y alta cohesión*).

## Métricas
**Objetivo:** proveer una evaluación cuantitativa del diseño (así el producto final puede mejorarse).

Se aplican dentro de UN MISMO proyecto y siempre se debe ser consistente.
1. **Tamaño estimado:** `cantidad de módulos + tamaño estimado de c/u`
2. **Complejidad de módulos:** cuáles son los que van a tomar más tiempo testear.
3. **Métricas de red:** enfocado en la estructura del diagrama.
	1. Se considera un buen diagrama aquel en el cual cada módulo tiene sólo un módulo invocador (reduce acoplamiento). 🌳
	2. Impureza del grafo = `nodos_del_grafo - aristas_del_grafo - 1` si impureza = 0 tenemos un árbol. <!--Y todo es felicidad. -->
4. **Métricas de estabilidad:** Trata de capturar el *impacto de los cambios* en el diseño. La estabilidad es la cantidad de suposiciones por otros módulos sobre uno específico.
5. **Métricas de flujo de información:** Computar la complejidad inter-módulo que se estima con inflow y outflow (el flujo de info que entra o sale del módulo).
	1. `DC = tamaño * (inflow * outflow)²` <!-- El ( )² representa la importancia de la interconexión respecto a la complejidad interna --> 
	2. Propenso a error si `DC > complejidad_media + desviación_estándar`
	3. Complejo si `complejidad_media < DC < complejidad_media + desviación_estándar.`

# 🦆 Diseño orientado a objetos

## Análisis OO y Diseño OO
Análisis OO: Primer paso (previo a la SRS).
Existe métodos que combinan análisis y diseño (ADOO)
Análisis: entender el sistema. Muy global.
Diseño: Maquetear una solución.

## Conceptos de la Orientación a Objetos
### Clases y objetos
**Encapsulamiento** de datos e información u provee interfaces para accederlos y modificarlos.
**Estado persistente** tracking del estado.

Clase: define estructura y servicios. Tiene interfaz, cuerpo y variables. Las operaciones pueden ser públicas, privadas y protegidas.

### Relaciones entre objetos
**Asociación** solicitar un servicio
**Agregación** uno es parte de otro
**Composición** uno no existe sin la presencia del otro.

![Relaciones_entre_objetos](relaciones_entre_objetos.png)

### Herencia y polimorfismo
Único en OO
**herencia**: <!-- COMPLETAR --> Forma una jerarquía entre clases.
Herencia múltiple: puede generar conflictos. El polimorfismo es incluso más complejo. Mejor no usarlas a menos que sea muy necesario.
+ Herencia estricta: No se redefinen  métodos. Solo se agregan características para especializarla.
+ Herencia no estricta: Mala costumbre.
<!--Duda: Interfaz es herencia estricta? -->
`herencia => polimorfismo`
**polimorfismo**: una hija Y de X es tanto de tipo X como de tipo Y.
<!--Nota: optimización temprana es la raíz de todos los males -->

## Conceptos de diseño
### Acoplamiento
<!-- SIEMPRE SE EVALÚA-->
**Tipos de acoplamiento**
+ *Interacción:* no se puede eliminar del todo. es mejor si Se comunican a través de la menor cantidad de parámetros pasando menos info y nada de control
+ *Componentes:* Muy feo. Mejor Si las variables de la clase C en A son, o bien atributos o parámetros. 
+ *Herencia:* Dos clases están acopladas si una es subclase de otra. Lo malo es si se modifican la signatura de un método. O si cambia la pre y post condición (especificación).

### Cohesión
<!-- SIEMPRE SE EVALÚA-->
**Tipos de cohesión**
+ *Método:* Porqué los elementos están juntos en el mismo método. Se debería poder escribir una oración simple de lo que hace un *método?*
+ *De clase:* Porqué distintos atributos y métodos están en la misma clase?
+ *De Herencia:* Porqué distintas clases están juntas en la misma jerarquía? Cohesión por reuso no esta tan bueno, si esta piola si es especificación-generalización.

### Principio abierto-cerrado
*"Las entidades de software deben ser abiertas para extenderlas y cerradas para modificarlas."*
Habla de herencia. Evitar la herencia no estricta.
Si se cumple el principio de Sustitución de Liskov se cumple el principio abierto-cerrado.

**Principio de sustitución de Liskov**
<!-- SIEMPRE SE EVALÚA. COMPLETAR -->
Un programa que utiliza un objeto O con clase C debería permanecer inalterado si O se reemplaza por cualquier objeto de una subclase de C. En general `Liskov => abierto-cerrado`

## Arquitectura del software
Si se puede elegir entre fácil o entendible. Siempre elegir entendible. Ahorra tiempo después.

## Metodología de diseño
<!-- No se evalúa prácticamente. Estudiar teóricamente -->
1. **Producir el diagrama de clases**
	+ Básicamente el diagrama obtenido en el análisis.
2. **Producir el modelo dinámico y usarlo**
	+ Describe la interacción entre objetos. ¿Cuándo pasan las cosas?
3. **Producir el modelo funcional y usarlo para definir operaciones de las clases** 
	+ Define la transformación de los datos.
4. **Identificar las clases internas y sus operaciones**
5. **Optimizar y empaquetar**

<!-- COMPLETAR para qué se usa c/uno + frase explicativa -->

## Métricas
Sirven para repensar el diseño o prestar más atención en testing.
<!-- COMPLETAR: para qué sirven los números que se obtienen al final -->

### Métodos pesados por clases (WMC)
La complejidad de la clase depende de la **cantidad de métodos en la misma y su complejidad**
`M1, ..., Mn` son métodos de `C`
Sea C(Mi) la complejidad
Luego WMC = Sumatoria de C(Mi)

### Profundidad del árbol de herencia (DIT)
mayor DIT => mayor probabilidad de errores

### Acoplamiento entre clases (CBC)
Cantidad de clases a las cuales esta clase está acoplada.

### Respuesta para una clase (RFC)
RFC captura el grado de conexión de los métodos de una clase con otras clases.

### Cantidad de hijos (NOC)
Cantidad de subclases inmediatas de C.
`> NOC => >reuso`
***
Práctico: el último que entra al primer par