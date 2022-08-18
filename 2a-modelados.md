# Diagrama de clases

## Objeto

```
Objeto = Identidad + Estado + Comportamiento
```

Tienen una identidad que no varía. Su estado si cambia con el tiempo. El comportamiento son las formas en la que dicho estado puede cambiar.


## Clase 
Definen objetos
```
Clase = Tipo + Atributos + Métodos
```

Las clases definen un tipo, conjunto de valores.  La clase determina la estructura de los estados a través de los atributos. Los métodos definon los comportamientos

## ¿Qué describe el diagrama de clases?
### Las relaciones entre objetos.

| Relación      | Explicación              | UML          |
| ---------     | ------------------------ | ------       |
| Asociación*   | A está relacionado con B | A ------ B   |
| Agregación    | A es parte de B          | A ------<> B |
| Composición** | A no puede vivir sin B   | A -----<.> B |
| Herencia***   | A es B                   | A ---> B     |


\* cada objeto de A está relacionado con B. Ej: los alumnos (A) están en cursos (B). Las relaciones son inmutables. Ej:  A llama a B es mutable (solo pasa en un momento)
** composicion es un caso particular de B. Ej: una carrera no puede vivir sin la universidad
*** Pensando en las clases como tipos B es subtipo de A

### Cardinalidades
```
A 1----1 B
A 1----* B
A *----1 B
A *----* B
```
 1: 1 
 \* 0 o mas

## Principios de la OO
1. **Bajo acoplamiento**: si una clase depende mucho de otra => mucho acoplamiento. Si se edita una clase se tiene que modificar la otra. Lo mejor es bajo acoplamiento para que se puedan dividir tareas y que sea más mentenible.\*
2. **Alta cohesión**: Tiene que ver con lo que hay **dentro** de la clase. Que todo lo que está en una clase se refiera a lo mismo. Si hay baja cohesión conviene dividir la clase. Así será más legible y ordenado. \*
3. **Única responsabilidad**: cada clase debe tener una única responsabilidad. Que haya una única razón para que esa clase pueda cambiar.
4. **No repetirse uno mismo**: DRY que no se repita en ningun momento dos porciones de código iguales (semánticamete). Que no se repitan **abstracciones**.

\* hay un trade off entre bajo acoplamiento y alta cohesion. Pero con una buena abstracción se pueden mejorar ambos aspectos.

