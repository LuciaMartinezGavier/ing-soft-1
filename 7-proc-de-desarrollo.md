# Procesos de desarrollo

## Modelos de proceso de desarrollo
### Modelos comunes
%%Siempre se toman%%
#### Cascada
Secuencia lineal.  
Primero una fase termina y luego empieza la siguiente.
1. Análisis y especificación de requerimientos
2. Diseño (de alto nivel y detallado)
4. Codificación
5. Testing
6. Instalación
%% Pegar gráfico%%

**¿Cuándo sirve?**  
- Para proyectos donde los requerimientos son bien comprendidos y las decisiones sobre la tecnología son tempranas.
- Para tipos de proyectos en los cuales los desarrolladores están muy familiarizados con el problema a atacar y el proceso a seguir.

#### Prototipado
El prototipado aborda las limitaciones del modelo de cascada en la especificación de requerimientos.

%%gráfico. El test en requerimientos es muy mínimo%%

**Desarrollo del prototipo**  
Versión para comprender requerimientos. El prototipo debe descartarse.
El cliente experimenta el prototipo y provee feedback para la mejora.

**El costo de prototipado debe mantenerse bajo**  
Quick & dirty: La calidad no importa, solo poder desarrollar el prototipo rápidamente.

**Ventajas**  
Mayor estabilidad en los requerimientos
Los requerimientos se congelan más tarde
La experiencia en la construcción del prototipo ayuda al proyecto final.

#### Iterativo
[[SCRUM]]
+ Aborda el problema de "todo o nada" del modelo de cascada.
+ Combina beneficios del prototipado y del cascada
+ desarrolla y entrega el SW incrementalmente.
+ Cada incremento es completo en sí mismo.
+ Puede verse como una "secuencia de cascadas".

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

#### Timeboxing
Planear tiempos fijos. Para hacer cada tarea

Primero fija la duración de las iteraciones y luego determina la especificación
Divide la iteración en partes iguales y usa pipelining para ejecutar iteraciones en paralelo.

Lo ideal es que todo el tiempo, todos los recursos que tengo estén siendo usados.

Hay equipos dedicado a cada etapa
En este modelo hay un alto compromiso con los tiempos de entrega.

La ejecución del proyecto de trabajo <!--completar-->
Sirve para distintos proyectos distintos.

**Desventajas**
Necesita muchas personas en cada equipo.
