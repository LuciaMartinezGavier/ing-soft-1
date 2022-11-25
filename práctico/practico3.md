# Práctico 3: Arquitectura

1. _¿Existen razones por las cuales pueda ser necesario diseñar la arquitectura de un sistema antes de alcanzar la etapa de especificación?_
   No, porque la arquitectura comienza a resolver el problema. Y sin la
   especificación no se sabe cuál es el problema en cuestión.

2. _Al realizar el diseño arquitectónico de un sistema, ¿puede concebirse un sistema que corresponda a más de un estilo arquitectónico?_
   Si, en general se combinan diseños.

3. _¿Cuál es la diferencia entre una arquitectura y un diseño de alto nivel?_
   La arquitectura es de más alto nivel, que se enfoca en las componentes
   principales. A diferencia del diseño de alto nivel no considera nada de la
   estructura interna.

4. _Como resultado del diseño de un sistema, se produjo un diagrama de clases. ¿Se necesita algo más que esto?_
   Si, el diagrama de clases se correspondería con la vista de módulos. Pero
   para el diseño arquitectónico se deben plantear muchos tipos de vistas, entre
   ellos una vista de asignación de recursos, y vistas de componentes y conectores.

5. _La arquitectura de un sistema, ¿corresponde al comportamiento de un sistema en tiempo de ejecución o a su organización estática?_
   La arquitectura de un sistema identifica subsistemas y la forma que interactúan
   entre ellos. Pero no en tiempo de ejecución. Se pueden ver las conexiones entre
   los diferentes componentes pero no cómo estas cambian a lo largo de la ejecución.

6. _¿Qué es un estilo arquitectónico? Según “Software Architecture: Perspectives on an Emerging Discipline”(Shaw & Garlan 1996), los estilos arquitectónico pueden clasificarse en componentes independientes, flujo de datos, centrados en datos, de máquina virtual y de llamada/retorno. ¿A cuáles de estas categorías corresponden los estilos arquitectónicos descriptos en “An Integrated Approach to Software Engineering”?_

Un estilo arquitectónico es un conjunto de restricciones que definen una familia
de arquitecturas que las satisfacen.

- Pipe and filter: flujo de datos
- Estilo de datos compartidos: centrados en datos
- Estilo cliente servidor: llamada/retorno
- Publicar-suscribir: de máquina virtual
- Estilo peer to peer: componentes independientes

<!--??? -->

7. _¿Qué es el middleware? Un sistema cuyas componentes se comunican a través de middleware, ¿a qué estilo arquitectónico puede corresponder?_
    El **middleware** es el software que brinda servicios y funciones comunes
   a las aplicaciones. Cliente-Servidor, donde el middleware contiene lar
   reglas del servicio.

8. _¿Qué son las arquitecturas de software orientadas a servicios?_
   Son un estilo de arquitectura que se enfoca en servicios discretos en vez de
   en el diseño monolítico. Se provee servicios a otros componentes por
   componentes de aplicación a través de un protocolo de comunicación.
   Por ejemplo el estilo peer-to-peer y el estilo cliente-servidor.
