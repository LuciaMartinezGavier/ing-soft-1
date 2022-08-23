# Arquitectura del software
Ya se empieza a detallar el *cómo* se va a resolver el problema
Es la primera de las tres etapas de **diseño** y la de más alto nivel:
1. Arquitectura
2. Diseño Alto Nivel
3. Diseño Bajo Nivel

Da una vision de las partes del sistema y de las relaciones entre ellos.
La arquitectura permite que los cambios sean simples de hacer en sistemas grandes y complejos.

El objetivo de la arquitectura es identificar subsistemas y la forma que interactúan entre ellos.

***
Definición:
<!--COMPLETAR-->
***

No son importantes los detalles de como se aseguran las propiedades externas.
En general se tienen varias estructuras (aspectos ortogonales).

A este nivel se hacen las elecciones de tecnología, productos a utilizar, servidores, ...
Es la etapa más temprana donde algunas propiedades como confiabilidad y desempeño pueden evaluarse.

## ¿Por qué es importante?
Facilita la **Comprensión y comunicación**: Define un marco de **comprensión común** entre los distintos interesados.

Reuso:
Una de las principales técnicas para incrementar la productividad.
Se elige una arquitectura tal que las **componentes existentes encajen**

**Construcción y evolución**: sservirá para **guiar** el desarrollo y **asignar equipos de trabajo**.
Ayuda a dimensionar cuán caro puede costar un cambio.

Propiedades de **confiabilidad y diseño**.

Se requerirá descripción precisa.
No hay una única arquitectura de un sistema. 

## Vistas
Una vista consiste de elementos y relaciones entre ellos y describe una estructura. Destacan un aspecto.

1. Módulo
2. Componentes y conectores: análisis de desempeño
3. Asignación de recursos: 

### Vista de módulos
Un sistema es una colección de **unidades de código**

### Componentes y conectores
Los elementos son **entidades de ejecución**. 
Componentes son elementos computacionales o de almacenamiento de datos
conectores son mecanismos de interacción entre las componentes


Una vista C&C define las componentes y ?? <!--completar-->

#### Componentes
Cada componente tiene tipos. Ser consistente con la notación
* Cliente 
* Servidor
* Base de datos
* Aplicaciones

#### Conectores
Conectores son el medio en el cual la interacción entre componentes toma lugares.
Los conectores no necesariamente son binarios.

Tienen nombre y tipo.

A nivel arquitectura se omiten muchos detalles.

#### Estilos arquitectónicos para la vista de C&C
Define una familia de arquitecturas que satisfacen las restricciones de ese estilo.
Distintos estilos pueden combinarse.

En general se usan diferentes combinaciones de estilos o se usan estilos nuevos.

##### Pipe and Filter
Adecuado para sistemas que fundamentalmente realizan *transformaciones de datos*.
Tipo de componente: filter: es **independiente** y **asíncrona**. 
Tipo de conector: pipe. Unidireccional y no tiene bifurcaciones. Cada tubo solo conecta 2 componentes.

**Restricciones**
<!--Completar-->

##### Estilo de Datos Compartidos
<!-- SE EVALÚA -->
Repositorio de datos: provee **almacenamiento** permanente y confiable.
Los componentes no actúan directamente entre ellas.

**Estilo pizarra**  
Avisa cuando hay algún cambio.

**Estilo repositorio**  
Es pasivo. 

##### Estilo cliente-servidor
Componentes: clientes y servidores
Los clientes solo se comunican con el servidor, no con otros clientes.

##### Otros estilos
**Publicar-suscribir**
**Estilo peer-to-peer**
Componente: Peer.
Parecido al modelo de computación orientada a objetos
**Estilo de procesos que se comunican**
Procesos que se comunican a través de mensajes.

## Documentación 