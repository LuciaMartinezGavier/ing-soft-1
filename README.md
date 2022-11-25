Desarrollo de _cualquier_ software y en el _proceso_ que conlleva.
Como desarrollar software de solidez industrial.  
Hacer código **entendible** es tan importante como hacer código ejecutable.

## Profes

- Laura Brandán: [laurabrandan@unc.edu.ar](laurabrandan@unc.edu.ar)
- Santiago Ávalos
- Matías Lee
- Diego Lis
- Gonzalo Peralta
- Leandro Ramos

## Bibliografía

Pankaj Jalote "An Integrated Approach to Software Engineering" 3ra ed.,
Springer, 2005

## Plan de estudios

- Objetivo: Planear, ejecutar y administrar un software de tamaño pequeño.

### [Introducción](./1-intro)

- [x] El dominio del problema
- [x] El desafío de la Ingeniería del Software
- [x] El enfoque de la Ingeniería del Software

### [El proceso de desarrollo](https://docs.google.com/document/d/1FKqr_vCBeBYl5YNJjerJeG-dvZYWu2OzV1ZR3bNoaPU/edit?usp=sharing) y [Procesos de Software](https://docs.google.com/document/d/1F__JTCXRi-zQhhv1wH0ElIUSiPICChARimMiT9mkH8I/edit?usp=sharing)

- [x] Procesos, Modelo de procesos. Componentes. Enfoque ETVX.
- [x] Características deseadas del proceso del software: Predecible y repetible. Tolerante a cambios, Testeable y Mantenible.
- [x] Proceso de desarrollo del software, etapas fundamentales.
- [x] Modelos de procesos de desarrollo: Cascada, Prototipado, Iterativo.
- [x] Otros procesos del software: Administración del proyecto, Proceso de inspección, Administración de configuración, Administración de cambios, Administración del proceso (CMM).

### [Análisis y especificación de los requerimientos del software](./2-analysis-espec)

- [x] Requerimientos del software, Necesidad de la especificación de requerimientos, Proceso de requerimientos.
- [x] Análisis del problema: Enfoque informal, Modelo de flujo de datos (DFD), Modelo orientado a objetos (UML), Prototipado.
- [x] Especificación de los requerimientos del software: Características, Componentes, Lenguajes de especificación, Estructura de un documento.
- [x] Especificación funcional con Casos de Uso: Conceptos, Estructura, Abstracción.
- [x] Validación
- [x] Métricas: Tamaño, Calidad

### [Arquitectura del software](./3-arquitectura)

- [x] Rol de la arquitectura del software
- [x] Vistas: Módulos, Componentes y conectores, Asignación de recursos
- [x] Vista de Componentes y Conectores (C&C). Estilos arquitectónicos para C&C: Tubos y Filtros, Datos compartidos, Cliente-Servidor, Estratificados,
- [x] Documentación del diseño arquitectónico.
- [x] Arquitectura en comparación con el diseño. Preservación de la integridad de una arquitectura.
- [x] Evaluación de las arquitecturas (método de análisis ATAM)

### [Planeamiento del proyecto de software](https://docs.google.com/document/d/1H0WMEa_fnbRhy4eeCIM28uRcLvBYIY7inetuubHycAM/edit?usp=sharing)

- [x] Planeamiento del proceso
- [x] Estimación del esfuerzo: Incertidumbres, Construcción de los modelos (estimaciones top-down y bottom-up), el modelo COCOMO.
- [x] Planificación y recursos humanos: Planificación global y detallada, estructura del equipo de trabajo
- [x] Plan del control de calidad: Introducción y eliminación de errores, enfoques, plan
- [x] Administración del Riesgo: Conceptos, Evaluación, Control
- [x] Planeamiento del Seguimiento del proyecto: Mediciones, seguimiento observacional, registro del seguimiento.

### [Diseño de alto nivel](./4-diseño-alto-nivel)

#### Diseño orientado a funciones

- [x] Niveles en el proceso de diseño
- [x] Principios del diseño: Particionado y jerarquía, Abstracción, Modularidad. Estrategias top-down y bottom-up
- [x] Acoplamiento y cohesión
- [x] Notación y especificación del diseño
- [x] Metodología de diseño estructurado: Cuatro pasos elementales, heurísticas de diseño, análisis de transacción.
- [x] Verificación
- [x] Métricas: de red, de estabilidad y de flujo de información

#### Diseño orientado a objetos

- [x] Conceptos de orientación a objetos: Clases, Objetos, Relación entre objetos, herencia, polimorfismo.
- [x] Conceptos de diseño: Acoplamiento, cohesión, principio abierto-cerrado, c UML
- [x] Una metodología de diseño: Modelado dinámico, modelado funcional, definición de clases y operaciones, Optimización.
- [x] Métricas

### [Diseño detallado](./5-diseño-detallado)

- [x] Lenguaje de diseño de procesos (PDL). Diseño lógico (del algoritmo). Modelo de estado de clases (Autómatas de estado nito). Refinamiento en abstracciones de datos e invariantes de representación.
- [x] Verificación: Recorrido del diseño, Revisión crítica (bajo proceso de inspección), verificación de consistencia y uso de técnicas formales
- [x] Métricas. Complejidad Ciclomática, Vínculos de datos, Métricas de cohesión

### [Codificación](6-codificación)

- [x] Principios y pautas para la programación: Errores comunes, Programación estructurada, ocultamiento de la información, prácticas de programación, estándares de codificación
- [x] Proceso de codificación: Incremental, Dirigido por test, Programación de a pares, Control del código fuente y construcción (build).
- [x] Refactorización: Conceptos básicos, Malos olores, refactorizaciones comunes,
- [x] Verificación: Inspección del código, test de unidad, Análisis estático, métodos formales

### [Testing](https://docs.google.com/document/d/1F__JTCXRi-zQhhv1wH0ElIUSiPICChARimMiT9mkH8I/edit?usp=sharing)

- [x] Conceptos fundamentales: Defecto y desperfecto (fault & failure), oráculos, casos de test y criterios de selección, psicología del test.
- [x] Testing de caja negra: Particionado por clases de equivalencia, Análisis de valores limites, gramfo de causa-efecto, testing de a pares, casos especiales, testing basado en estados (Máquinas de esteado finitas)
- [x] Testing de caja blanca: Criterios basados en el flujo de control, criterios basados en flujo de datos,
- [x] Testing por mutacion, generación de casos de test y herramientas de soporte.
- [x] El proceso de testing: Nivles, Plan, Especificación de los casos de test, ejecución de los casos de test, Análisis, Registro de defecros y seguimmiento
- [x] Análisis y prevención de los defectos.
- [x] Métricas. Estimación de la ¿ con habilidad

\*\* Se toma SIEMPRE testing

### **Aspectos profesionales y sociales**

- [ ] Computación y sociedad
- [ ] Propiedad intelectual, licencia de software y contratos informáticos
- [ ] Aspectos legales
- [ ] Responsabilidad y ética profesional.
