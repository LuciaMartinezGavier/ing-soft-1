# Procesos de desarrollo

## Modelos de proceso de desarrollo
### Modelos comunes
1. [Cascada](#cascada)
2. [Prototipado](#prototipado)
3. [Iterativo](#iterativo)
4. [Timeboxing](#timeboxing)

%%Siempre se toman%%
## Cascada
Secuencia lineal.  
Primero una fase termina y luego empieza la siguiente.
Todas las fases terminan en una etapa de validación.

1. Análisis y especificación de requerimientos
2. Diseño (de alto nivel y detallado)
4. Codificación
5. Testing
6. Instalación
%% Pegar gráfico%%

**¿Cuándo sirve?**  
- Para proyectos donde los requerimientos son bien comprendidos y las decisiones sobre la tecnología son tempranas (electrodomésticos por ejemplo).
- Para tipos de proyectos en los cuales los desarrolladores están muy familiarizados con el problema a atacar y el proceso a seguir.

### Ventaja
+ Conceptualmente simple. **Generalmente**, intuitivo y lógico.
+ Fácil de administrar.

También existe el modelo de **cascada con feedback**.
<!--Agregar summary-->

## Prototipado
El prototipado aborda las limitaciones del modelo de cascada en la especificación de requerimientos.

%%gráfico. El test en requerimientos es muy mínimo%%

### Desarrollo del prototipo
Versión para comprender requerimientos. El prototipo debe descartarse.
El cliente experimenta el prototipo y provee feedback para la mejora.

**El costo de prototipado debe mantenerse bajo**  
Quick & dirty: La calidad no importa, solo poder desarrollar el prototipo rápidamente.

### Ventajas
Mayor estabilidad en los requerimientos
Los requerimientos se congelan más tarde
La experiencia en la construcción del prototipo ayuda al proyecto final.

## Iterativo
[[SCRUM]]
+ Aborda el problema de "todo o nada" del modelo de cascada.
+ Combina beneficios del prototipado y del cascada
+ desarrolla y entrega el SW incrementalmente.
+ Cada incremento es completo en sí mismo.
+ Puede verse como una "secuencia de cascadas".
+ Usa listas de control

Muy efectivo en desarrollo de productos
Desarrollo "a gusto del comprador"
+ Las empresas requieren respuestas rápidas.
+ No se puede arriesgar el "todo o nada"

##### Beneficios
Buen feedback. 
Pagos y entregas incrementales.

##### Inconvenientes
Se necesitará refactorización.

##### Aplicación
+ Cuando el **tiempo de respuesta** es importante.
+ Cuando no se puede tomar el riesgo de proyectos largos.
+ Cuando no se conocen todos los **requerimientos**.

##### Primer paso
implementación simple para un subconjunto del problema completo.
<!--Completar-->
##### ?
##### Nuevos enfoques
+ Extreme programming
	+ No perder tiempo en etapas iniciales
	+ Simplicidad y claridad de código
	+ Se esperan todo el tiempo cambios de requerimientos
+ Test driven development
+ Desarrollo ágil
	+ Esfuerzo colaborativo
	+ Auto-organización
	+ **Equipo multi-disciplinar**
+ Proceso unificado
	+ Proceso dirigido por casos de uso
	+ Iterativo e incremental
	+ Enfocado en los riesgos


##### Modelo en espiral
1. Identificar objetivos
%%2. completar%%

## Timeboxing
Planear tiempos fijos. Para hacer cada tarea.

Primero fija la duración de las iteraciones y luego determina la especificación
Divide la iteración en partes iguales y usa pipelining para ejecutar iteraciones en paralelo.

Lo ideal es que todo el tiempo, todos los recursos que tengo estén siendo usados.

Hay equipos dedicado a cada etapa
En este modelo hay un alto compromiso con los tiempos de entrega.

La ejecución del proyecto de trabajo <!--completar-->
Sirve para distintos proyectos distintos.

**Desventajas**
Necesita muchas personas en cada equipo. Por ende, puede ser caro.

# Procesos de desarrollo
El proceso es diferente al producto.

Un proceso adecuado ayuda a lograr los objetivos del software.

## Ownership of code
Cuanto menos una porción de código tenía menos claro quién es el dueño, más probable es que ese código tenga errores.

## Intercontinental partners
Cuanto más inclusivo, mejor andan las cosas :)
Mirada más amplia.

## Procesos y modelos de proceso
Un **proyecto exitoso** es el que satisface las expectativas en costo, tiempo, y calidad.

Un **modelo de proceso** especifica un proceso general, usualmente con fases en las que el proceso debe dividirse, conjuntamente com otras restricciones.

### Dos procesos fundamentales
+ **Desarrollo:** Se enfoca en las actividades para el desarrollo y para garantizar la calidad necesaria para la ingeniería sel software.
+ **Administración**

%%Gráfico%%

## Especificación del proceso
El proceso generalmente es un conjunto de fases.

### Enfoque ETVX
Entry-Task-Verification-Exit.

+ **Entrada**
+ **Tarea**
+ **Verificación**
+ **Criterio de salida**

## Características deseadas
+ Proveer alta C&P.
+ El costo de eliminar un defecto se incrementa a medida que perdura en el proceso de desarrollo.
+ Los procesos deben conseguir repetir el buen desempeño cuando se utilizan en distintos proyectos: 
	+ Para planear.
	+ Un proceso predecible se dice que está bajo un control estadístico. (Define un rango entre el tiempo estimado y el precio).
+ El SW cambia por muchas razones
	+ Cambios de requerimientos: Ya no se ve como algo negativo
	+ Cambios de operación.

### ¿Por qué utilizar fases?
+ Dividir y conquistar
+ Cada fase ..
%%COMPLETAR%%

### Otros procesos
1. Proceso para la administración del proyecto
2. Proceso de inspección
3. Proceso de administración de configuración

### Proceso para la administración del proyecto
se debe
+ Asignar recursos
+ Administrar recursos
+ Observar el progreso
+ Tomar acciones correctivas...

#### Fases
**Planeamiento:**  
Antes de comenzar el  proyecto
+ Tareas clave:
	+ Estimación de costos y tiempo
	+ ...
+ Seguiminiento y control
+ Análisis y terminación

### Proceso de inspección
Objetivo principal: detectar los defenctos en los productos de trabajo.
Inicialmente utilizado para el código, actualmente usado para todo?

%% Agregar gráfico
Importante: no solo decir revision grupal? (el del medio del gráfico) en el parcial
%%
#### T
+ **Moderador**
	+ Casi el único que está en todas las etapas
+ **Autor** 
	+ El dueño de lo uqe se está revisando
+ **Revisor**
	+ (un grupo)
	+ Son quienres revisan
+ **Lector**
	+ Lee Linea a línea para guiar el proceso
+ **Escriba**
	+ Toma nota de todo.


El foco es encontrar problemas, no resolverlos.

#### Planeamiento
Seleccionar el equipo de revisión

#### Preparación y repaso previo

planilla de registro de la revisión individual

Hay gente (que trabaja en general en otro lado) que usa su tiempo en eso, por lo tanto es importante saber quién fue revisor.

### Reunión de revisión grupal
Propósito: definir la lista final de defectos.

La reunión:
+ El lector lee línea a línea el producto de trabajo (o cualquier otra pequeña unidad)
+ ...
+ Se considera un defecto o no?

Al final de la reunión
+ El escriba presenta la lista de defectos / observaciones

EL moderador está a cargo de la reunión y juega un rol central:
Lo que se está revisando es el producto de trabajo y no el autor de éste.
Reuniones amigables y ordenadas.

| Prod de trabajo                  | Enfoque de la inspección                                                                            | Participantes                                          |
| -------------------------------- | --------------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| Especificación de requerimientos | Cumple con las necesidades del cliente. Es implementable. Omisiones, inconsistencias, ambigüedades. | Cliente, analista, diseñador, desarrollador            |
| Diseño de alto nivel             | El diseño implementa los requerimientos El diseño es implementable. Omisiones, calidad del diseño.  | Autor de SRS, diseñador a nivel detalle, desarrollador |
|   ...                               |                                                                                                     |                                                        |
| Casos de tests                   | Conjunto de casos de test verifica los requerimineots en la SRS. Los casos de test ?                |                                                        |

### Proceso de administración de configuración

### Proceso de administración de procesos.
Para mejorar el proceso, una organización debe comprender el proceso actual
+ Requiere que el proceso está bien documentado,
+ Que sea apropiadamente ejecutado en los proyectos,
+ Recolecta datos de los proyectos para comprender el desempeño del proceso en los proyectos.

Existen marcos que sugioeren formas de proceder en la mejora del proceso.
Ej : CMM

#### CMM *Capability Mature Model*
Tiene 5 niveles para el proceso de software.

| Nivel                 | Descrtipción                                                                      |
| --------------------- | --------------------------------------------------------------------------------- |
| Nivel 1               | Ah hoc                                                                            |
| Nivel 2: Repetible    | Admin de requerimientos del SW. Admin de configuración del SW. Planeamiento de ?? |
| Nivel 3: Definido     | Organización en definición del proceso                                            |
| Nivel 4: Administrado | Admin. de la calidad de SW. Admin cuantitativa del proceso                        |
| Nivel 5: Optimizado   | Admin. de cambio de proceso. Administración de cambio de Tecnología...            |


