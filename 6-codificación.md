# Codificación
Objetivo:
Implementar el diseño de la *mejor manera posible*.
La codificación afecta al testing y al mantenimiento.

El objetivo es reducir los costos de testing y mantenimiento. 
El código debe ser *fácil de leer y comprender* (no necesariamente fácil de escribir).

## Principios y pautas para la programación
**Objetivo**: que el código...
+ Sea simple
+ Sea fácil de leer
+ Tenga la menor cantidad de errores

### Errores comunes de codificación
"memory leaks", dereferencias de punteros a NULL
**Errores de sincronización**: deadelocks, condiciones de carrera, sincronización inconsistente
Error by one ej: <= por <
Indice de arreglo fuera de límites
Buffer overflow
Tipos de datos creados por el usuario (tener cuidado, describir bien las cotas) no es un error per sé

### Programación estructurada
Uso indiscriminados de los "goto"

Un programa tiene una *estructura estática* la cual es el orden de las sentencias en el código (lineal).
Un programa tiene una *estructura dinámica* el orden en el cual las sentencias se ejecutan.

El objetivo sería que sean lo más similares posibles.

Los constructores de la programación estructurada son de **una única entrada y una única salida**
Ser consciente de las suposiciones que uno hace sobre las llamadas a las funciones.

### Ocultamiento de la información
En general **solo ciertas operaciones** se realizan sobre la información, los datos solo se manipulan de pocas maneras.
Reduce el acoplamiento.

### Prácticas
+ Constructores de control
+ Gotos
+ Ocultamiento de la información
+ Tipos definidos por el usuario
+ Tamaños de los módulos
+ Interfaz del módulo
+ Robustez
+ Efectos secundarios: Evitarlos, documentar
+ Bloque "catch" vacío
+ "if" o "while" vacíos
+ Usar default en switch case
+ Valores de retorno en lecturas
+ "return" en "finally": NO
+ Fuentes de datos confiables
+ Dar importancia a las excepciones

### Estándares de codificación
La legibilidad del código aumenta si todos siguen ciertas convenciones de codificación.

Cierta dependencia de lenguaje/empresa/...

**Java**
+ Nombres de paquetes en minúscula
+ Tipos: Mayúscula
+ Variables: min
+ Constantes: TODO MAY
+ Métodos: verbos minúscula
+ Variables, métodos booleanos: 
+ Inicializar variables cuando se declaran
+ Inicial las varibales de los loops justo antes de estos
+ Evistar sentencias ejecutables en condicioanels

## Proceso de codificación
Comienza ni bien está disponivle la especificacipin del diseño de los módulos.
Usialemte los módulos se asignan a programadores individuales.

### Proceso de codificación incremental
**Proceso básico**
1. Escribir código del módulo
2. Realizar test de unidad
3. Si error: arreglar bugs y repetir tests.
<!-- Esto está MUY incompleto. Falta la parte de incremental: Describir el gráfico-->

Especificación del módulo
Escribir una implementación que implementa una funcionalidad
Escribir los test de esa funcionalidad
Correr el test
Si hay error → corregir → volver a correr
si no existe
Chequear que todas las especificación esté cubierta.
Si es así, listo
Si no: implementar otra funcionalidad.

### Desarrollo dirigido por test TDD
TDD: *Test Driven Develoment*

Especificación del módulo
↓
1. Escribir los test de alguna parte de la funcionalidad como la especificación
2. Escribir el código que pasa el test
3. Correr el código con los test
4. Si hay errores→arreglar. Si no hay:
5. El código necesita mejoras? si es así: refactorización (goto 3)
6. Todas las especificaciones están cubiertas? si es así listo sino, goto 1

Es completamente testeado :D
Lo que no se nos ocurrió testear, puede no estar en el código en sí.

El código necestitará factorización

### Programación de a pares
El código se escribe de a 2.
Una tipea otra señala errores.

Hay una revisión continua de código
Mejor diseño de algoritmos /estructuras de datos/lógica/..
Es más fácil que se escapen las condiciones particulares.
La efectividad no está demostrada.

### Control de código fuente y construcción 
("built")
Git

## Refactorización
El código se modifica con el fin de aumentar su funcionalidad.
Con el tiempo, aún si el diseño inicial era bueno, los cambios en el código deterioran el diseño.
Al complicarse el diseño, comienza a hacerse más complicado modificar el código y más susceptible a errores.

La **refactorización** es una técnica para mejorar el diseño del diseño existente
El objetivo NO es corregir bugs. Se debe hacer sobre código que funciona bien.
No debería cambiar la funcionalidad del código.

Debe hacerse en pasos pequeños. Para poder saber dónde se cometen errores.

cambio pequeño →test→corrección →test→ sale  todo bien → cambio pequeño.

**cosas feas**
1. Código duplicado
2. Métodos largos
3. Clases grandes
4. Lista larga de parámetros
5. Sentencia "switch"
6. Generalidad especulativa
7. Demasiada comunicación entre objetos
8. Encadenamiento de mensajes

### Refactorizaciones más comunes
**Mejoras de métodos:**
+ Extracción de métodos
**Mejoras de clases**
+ Desplazamiento de métodos
+ Desplazamiento de clases
+ Extracción de clases
+ Reemplazar valores de datos por objetos
**Mejoras de jerarquías**
+ Reemplazar condicionales con polimorfismos
+ Subir métodos/atributos: respecto a la herencia

## Verificación
+ **Inspección de código:** revisión. Luego de que el código esté compilado. Es caro. También se usan listas de control.
+ **Test de unidad:** El programador testea lo que acaba de programar. Da como resultado: pass/fail/inconclusive
+ **Análisis estático:** falso negativo: un test pasó pero había un bug. falso positivo: dice que hay error pero no.

### Métodos formales
no son escalables. F

***
El buen código es invisible.
***
