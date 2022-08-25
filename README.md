# 💻️ Ingeniería del Software I 💻️
Desarrollo de *cualquier* software y en el *proceso* que conlleva.
Como desarrollar software de solidez industrial.  
Hacer código **entendible** es tan importante como hacer código ejecutable.

## 👩‍🏫️ Profes
* Laura Brandán: [laurabrandan@unc.edu.ar](laurabrandan@unc.edu.ar)
* Santiago Ávalos
* Matías Lee
* Diego Lis

## 📆 Cronograma
### Parciales presenciales
* 13/09 y 20/10  (fechas tentativas)
* Recuperatorio 24/11

### Regularización y promoción
**Regularidad**
* 2 proyectos aprobados
* 2 parciales aprobados con 4 = **60%**

**Libres**
Se debe hacer el final
Proyecto personal 2 semanas

**Promoción** (falsa)
* Rendir muy bien los parciales.
* Ir a rendir en la 1° fecha y se hace un promedio para la nota final
* Quizás no hay.

### Proyectos
* Proyecto 1: Take home personal
    * Se *debe* hablar con los profes y preguntar.
    * Se entregan a Laura y se defienden personalmente
    * 2 semanas (4 clases + Zulip)
    * Es la primera parte del proyecto

* Proyecto 2: Proyecto de software
    * se elige grupo si tienen el proyecto 1 aprobado.
    * Grupos de 5 a 6 (depende de la cantidad de aprobados)
    * 3 demos obligatorias 3 sprints de 2 semanas con objetivos a completar.
      al final hay que presentar una demo. (Sirve como parcial y **defensa** del 
      laboratorio). Todos los integrantes deben asistir.

## 📚️ Bibliografía
Pankaj Jalote "An Integrated Approach to Software Engineering" 3ra ed.,
Springer, 2005

## 📑️ Plan de estudios
* Objetivo: Planear, ejecutar y administrar un software de tamaño pequeño.

### **Introducción** [[Ingenieria/ing-soft-1/1-intro]]
+ ✅️ El dominio del problema
+ ✅️ El desafío de la Ingeniería del Software
+ ✅️ El enfoque de la Ingeniería del Software

### **El proceso del software**
+ ⬜️ Procesos, Modelo de procesos. Componentes. Enfoque ETVX.
+ ⬜️ Características deseadas del proceso del software: Predecible y repetible. Tolerante a cambios, Testeable y Mantenible.
+ ⬜️ Proceso de desarrollo del software, etapas fundamentales.
+ ⬜️ Modelos de procesos de desarrollo: Cascada, Prototipado, Iterativo.
+ ⬜️ Otros procesos del software: Administración del proyecto, Proceso de inspección, Administración de configuración, Administración de cambios, Administración del proceso (CMM).

### **Análisis y especificación de los requerimientos del software**  [[2-analysis-espec]]
+ ✅️ Requerimientos del software, Necesidad de la especificación de requerimientos, Proceso de requerimientos.
+ ✅️ Análisis del problema: Enfoque informal, Modelo de flujo de datos (DFD), Modelo orientado a objetos (UML), Prototipado.
+ ✅️ Especificación de los requerimientos del software: Características, Componentes, Lenguajes de especificación, Estructura de un documento.
+ ✅️ Especificación funcional con Casos de Uso: Conceptos, Estructura, Abstracción.
+ ✅️ Validación
+ ✅️ Métricas: Tamaño, Calidad

### **Arquitectura del software** [[3-arquitectura]]
+ ✅️ Rol de la arquitectura del software
+ ✅️ Vistas: Módulos, Componentes y conectores, Asignación de recursos
+ ✅️ Vista de Componentes y Conectores (C&C). Estilos arquitectónicos para C&C: Tubos y Filtros, Datos compartidos, Cliente-Servidor, Estratificados,
+ ✅️ Documentación del diseño arquitectónico.
+ ✅️ Arquitectura en comparación con el diseño. Preservación de la integridad de una arquitectura.
+ ✅️ Evaluación de las arquitecturas (método de análisis ATAM)

### **Planeamiento del proyecto de software**
+ ⬜️ Planeamiento del proceso
+ ⬜️ Estimación del esfuerzo: Incertidumbres, Construcción de los modelos (estimaciones top-down y bottom-up), el modelo COCOMO.
+ ⬜️ Planificación y recursos humanos: Planificación global y detallada, estructura del equipo de trabajo
+ ⬜️ Plan del control de calidad: Introducción y eliminación de errores, enfoques, plan
+ ⬜️ Administración del Riesgo: Conceptos, Evaluación, Control
+ ⬜️ Planeamiento del Seguimiento del proyecto: Mediciones, seguimiento observacional, registro del seguimiento.

### **Diseño orientado a funciones** [[4-diseño]]
+  ✅️ Niveles en el proceso de diseño
+ ✅️ Principios del diseño: Particionado y jerarquía, Abstracción, Modularidad. Estrategias top-down y bottom-up
+ ⬜️ Acoplamiento y cohesión
+ ⬜️ Notación y especificación del diseño
+ ⬜️ Metodología de diseño estructurado: Cuatro pasos elementales, heurísticas de diseño, análisis de transacción.
+ ⬜️ Verificación
+ ⬜️ Métricas: de red, de estabilidad y de flujo de información

### **Diseño orientado a objetos**
+ ⬜️ Conceptos de orientación a objetos: Clases, Objetos, Relación entre objetos, herencia, polimorfismo.
+ ⬜️ Conceptos de diseño: Acoplamiento, cohesión, principio abierto-cerrado, c UML
+ ⬜️ Una metodología de diseño: Modelado dinámico, modelado funcional, definición de clases y operaciones, Optimización.
+ ⬜️ Métricas

### **Diseño detallado**
+ ⬜️ Lenguaje de diseño de procesos (PDL). Diseño lógico (del algoritmo). Modelo de estado de clases (Autómatas de estado nito). Refinamiento en abstracciones de datos e invariantes de representación.
+ ⬜️ Verificación: Recorrido del diseño, Revisión crítica (bajo proceso de inspección), verificación de consistencia y uso de técnicas formales
+ ⬜️ Métricas. Complejidad Ciclomática, Vínculos de datos, Métricas de cohesión

### **Codificación**
+ ⬜️ Principios y pautas para la programación: Errores comunes, Programación estructurada, ocultamiento de la información, prácticas de programación, estándares de codificación
+ ⬜️ Proceso de codificación: Incremental, Dirigido por test, Programación de a pares, Control del código fuente y construcción (build).
+ ⬜️ Refactorización: Conceptos básicos, Malos olores, refactorizaciones comunes,
+ ⬜️ Verificación: Inspección del código, test de unidad, Análisis estático, métodos formales
+ ⬜️ Métricas: Tamaño y complejidad.

### **Testing** **
+ ⬜️ Conceptos fundamentales: Defecto y desperfecto  (fault & failure), oráculos, casos de test y criterios de selección, psicología del test.
+ ⬜️ Testing de caja negra: Particionado por clases de equivalencia, Análisis de valores limites, gramfo de causa-efecto, testing de a pares, casos especiales, testing basado en estados (Máquinas de esteado finitas)
+ ⬜️ Testing de caja blanca: Criterios basados en el flujo de control, criterios basados en flujo de datos,
+ ⬜️ Testing por mutacion, genración de casos de test y herramientas de soporte.
+ ⬜️ El proceso de testing: Nivles, Plan, Especificación de los casos de test, ejecución de los casos de test, Análisis, Registro de defecros y seguimmiento
+ ⬜️ Análisis y prevención de los defectos.
+ ⬜️ Métricas. Estimación de la ¿ con habilidad

### **Aspectos profesionales y sociales**
+ ⬜️ Conputación y sociedad
+ ⬜️ Propiedad intelectual, licencia de software y contratos informáticos
+ ⬜️ Aspectos legales
+ ⬜️ Responsabilidad y ética profesional.

** Se toma SIEMPRE testing
Clase de modelado [[2a-modelados]] 