# Análisis y especificación de los requisitos del software

Paso #1 de los procesos. 

Identificar y especificar los requisitos (involucra interacción con la gente y no puede automatizarse).

**Análisis**: Entender al cliente. Descubrir qué se pretende del producto. Ida y vuelta entre el analista y el cliente.

Un buen analista debe asesorar y convencer y que el cliente acepte en lo que uno es bueno.

**Requisitos del software**: Tenerlo en concteto para producir el software.

+ Entrada: Las necesidades se encuentran en la cabeza de alguien (ideas abstractas)
+ Salida: Un detalle preciso de lo que será el sistema futuro.** SRS-System Requirements Specification**.

El proceso no es lineal; es itearivo y en paralelo.

![](https://imgur.com/kh7GfZN.png)

## SRS
La SRS es el medio para **reconciliar las diferencias** y **especificar las necesidades** del cliente/usuario de manera que todos entiendan.

Hay abogados y escribanos involucrados. Es un **contrato** o acuerdo entre cliente/usuario y quién suministrará el software. No debe ser ambigua.

**Es concisa y precisa**

+ Necesidades del cliente
+ Consideraciones del usuario
--> cliente y usuario deben comunicarse con el desarrollador

Cliente: No comprende el proceso de desarrollo de software. La SRS ayuda al usuario a comprender sus necesidades. 

Desarrolladorx: No conoce el problema ni su área de aplicación.

La SRS provee una referencia para la **validación** del producto final. (Determina el resultado correcto). Verificación: "el software satisface la SRS".

**Una SRS de alta calidad es esencial para obtener un software de calidad**
Los errores de requerimientos solo se manifiestan en el software final.

**Una buena SRS reduce los costos de desarrollo**
Los cambios de requerimientos pueden costar demasiado (hasta un 40%)
En cada etapa es más caro el precio de encontrar y resolver un error de los requerimientos.


## Proceso de requerimientos

Lso requerimientos deberían ser simples conceptos que son siempre ciertos.

**Actividades básicas**
1. Análisis del problema o requerimientos.
2. Especificación de los requerimientos.
3.  Validacion.

La transición del análisis a la especificación es complicada.
1. La especificación se enfoca en el **comportamiento externo.**
2. Objetivo del análisis: comprender la estructura del problema y su dominio (componentes, entrada, salida).
3. Se recolecta **más  información (o distinta) de la necesaria** para la especificación.

Los métodos de análisis son similares a los de diseño, pero con **objetivos y alcances distintos**.
El análisis trata de entender. El diseño trata de resolver.

## Análisis del problema
1. Entrevistas con el cliente y usuarios
2. Lectura de manuales
3. Estudio del sistema actual
4. Ayudar al cliente/usuario a comprender las nuevas posibilidades

+ Obtener la información necesaria
+ Lluvia de ideas: discutir. Interactiar con el cliente para establecer propiedades
+ Relaciones iterpersonales
+ Habilidades de comunicación
+ Organizar la información
+ Asegurar completitud
+ Asegurar consistencia
+ Evitar diseño interno: evitar tratar de resolver el problema.

 **Particionar el problema**
Comprender los subproblemas y la relación respecto a
+ Funciones
+ Objetos
+ Eventos del sistema

### Enfoque informal
No hay una metodología definida; la informacion se obrinee a través del análisis.

### Modelado de flujo de datos
Ampliamente utilizado
Se enfoca en las ffunciones realizadas en el sistema.
Para el modelado se usan diagramas de flujos de datos (DFD) y descomposición funcional.

**Un DFD es una represetación gráfica del flujo d datos a través del ssistema**

![](https://imgur.com/LKwxEDB.png)

Las burbujas deben tener nombre (verbos); transformadores
Flechitas: (con dirección)  su numbre son sustantivos, son los datos que van de un lado a otro
Rectánfulos: represneranan fuentes o resumuderos.
Nombres con rayita: Los archivos externos
una relación * o + 

No debe decir **cómo** se realiza una transformación.
No hay loops ni razonamiento condicional

### Cómo dibujar
Entradas, salidas, fuentes, sumideros
Trabajar consistentemente
si se complica, cambiar el sentido (de la salida a la entrada)
<!-- TODO: completar lista -->
hacer + de un grafo


**Errores**:
Consistencia no preservada
Flujo de datos irrelevantes
Flujos de datos omitidos
Flujos de datos sin etiquetar
Procesos omitidos
Inclusion de analisis de control : se resuelve el COMO

#### Diccionario de datos
Se puede usar expresiones regulares para identificar los datos.



### Modelado de flujo de datos
1. Dibujar el diagrama del contexto: unico transformador. General
2. Dibujar el DFD del sistema existente: refinar el anterior. Es importante la comunicación con el cliente. 
3. Modelado del sistema propuesto. Dibujar el DFD del sistema propuesto e identificar la frontera hombre-máquina: Pueden usasrse DFD en niveles jerárquicos.

**Ejemplo**

Una dueña de restaurante, quiere automatizar algunas partes del negocio.
Entrevistas y cuestionarios. Recolectamos info en gral

**Partes involucradas**: clientes y usuarios.

**Diagrama de contexto:**

![](https://imgur.com/amyk3yi.png)

No todos los aspectos seran computables

**DFD**
![](https://imgur.com/GADTuWV.png)



**DFD del sistema propuesto**
Se interactúa con el cliente. Pueden agregar nuevos aspectos.

![](https://imgur.com/VCI0KTe.png)

Se genera el sistema propuesto.

<!-- TODO: Actividad: jugar y hacer DFDs --> 

**Diccionario de datos del DFD del sistema**

![](https://imgur.com/burjAR3.png)


## Modelado orientado a objetos
Un objeto **provee servicios** o **realiza operaciones**. Solo se acciede a ellos a través de estos.

![](https://imgur.com/9VxS3NL.png)


| clase |ejemplo |
| --- |---|
| nombre de la clase |Prescription|
| atributos |Refrigration Needs|
|métodos |Warnings|

Herencia
Hay asociaciones: no hay herencia. Una drugstore tiene muchas ventas.  relaciones N a N (dos puntitos).

* Pasos más significativos para el modelado orientado a objetos.
Identificar objetos y clases: los objetos se corresponden con sustantivos
Identidicar estructuras
Identificar atributos: características. No agregar atributos innecesarios
Identificar asociaciones: hacer jerarquía de las clases
Definir servicios: proveen el elemento activo en el modelado OO.


En estos pasos, hay "huecos" por ejemplo clases que todavía no se sabe cuales son los atributos.

## Prototipado 
<!-- TODO: estudiar del libro 3.2.4 -->

Enfoques
Descartable: el prototipo se construye con la idea de desecharlo luego de culminada la fase de requerimientos
Evolucionario: Se construye con la idea de que evolucionará al sistema final.

* El descartable es más adecuado porque igual es probable que se descarte

## Especificación de los requerimientos

La SRS se sssconfoca en el comportamiento **externo** del sistema.

También en la SRS: tratamiento de errores, requerimeiteneos en el desempeño restricciones de diseño, conformidad de estándares, recuperacion, etc
### Características de la SRS
<!-- SE EVALUA SIEMPRE-->
+ **Correcta**: Cualquier cosa que está en la SRS tiene que haber sido querida por el cliente. cliente --> SRS
+ **Completa**: que tenga todos los requerimientos que el cliente quiere. cliente <-- SRS
+ **No ambigua**: que no haya cosas subjetivas: "rápido" "lindo" . Se puede interpretar de una única forma.
+ **Consistente**: Que no se contradiga. Que toda la información esté ordenada permite que sea consistente
+ **Verificable**: Tiene que ver con la No-ambiguedad.
+ **Rastreable**: Que para cualquier elemento en la SRS, se puede mostrar que en el sistema final. Y viceversa. sistema final <-- SRS & SRS <-- sistema final
+ **Modificable**: debe suceder que no haya requerimientos en varios lugares. Para que sea facil de modificar.
+ **Ordenada en aspectos de impotancia y estabilidad** : Saber qué aspectos son más importantes. Criticos, importantes, deseables. Dar bola a las características deseables.


### Componentes de la SRS
Requerimientos **dinamicos**: especifican restricciones sobre la ejecución
* Tiempo de respuesta
* Tiempo esperado de terminación de una operación dada
* Tasa de transferencia o rendimiento
* Cantidad de operaciones realizadas por unidad de tiempo
* En general se especifican los rangos aceptables de los distintos parámetros


Requerimientos **estáticos** :  no imponen restricción en la ejecucion
* Cantidad de terminales admitidas
* Cantidad de usuarios admitidos simultaneamente
* Cantidad de archivos a procesar y sus tamaños

Restricciones de diseño: estandares

Requerimientos de interfaces externas

### Lenguajes de especificación

Realidad: lenguaje natural. No usar conjugación de verbos. La gran ventaja es que el cliente entiende.

Los lenguajes formales deben ser fáciles y precisos. Vemos en ingeniería II, se usan para sistemas muy críticos.

Lo ideal es mezclar ambos enfoques


### Alcance
<!--No se suele tomar, importante para el TH -->

Qué cosas entran o no en el proyecto
Objetivos, entregables y requerimientos. Tiempos de entrega
Cuales son la prioridades para que hacer promero
Criterio de aceptacion (¿que usauario lo aceptara?)
<!-- Creo que me falta una FIXME -->


## Estructura de un documento de requerimientos
<!--TODO: Completar -->




