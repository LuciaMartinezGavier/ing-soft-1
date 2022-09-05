# Práctico 3: Arquitectura
1. *¿Existen razones por las cuales pueda ser necesario diseñar la arquitectura de un sistema antes de alcanzar la etapa de especificación?*
No, porque la arquitectura comienza a resolver el problema. Y sin la especificación no se sabe cuál es el problema en cuestión.

2. *Al realizar el diseño arquitectónico de un sistema, ¿puede concebirse un sistema que corresponda a más de un estilo arquitectónico?*
Si, en general se combinan diseños.

3. *¿Cuál es la diferencia entre una arquitectura y un diseño de alto nivel?*
La arquitectura es de más alto nivel, que se enfoca en las componentes principales. A diferencia del diseño de alto nivel no considera nada de la estructura interna.

4. *Como resultado del diseño de un sistema, se produjo un diagrama de clases. ¿Se necesita algo más que esto?*
Si, el diagrama de clases se correspondería con la vista de módulos. Pero para el diseño arquitectónico se deben plantear muchos tipos de vistas, entre ellos una vista de asignación de recursos, y vistas de componentes y conectores.

5. *La arquitectura de un sistema, ¿corresponde al comportamiento de un sistema en tiempo de ejecución o a su organización estática?*
La arquitectura de un sistema identifica subsistemas y la forma que interactúan entre ellos. Pero no en tiempo de ejecución. Se pueden ver las conexiones entre los diferentes componentes pero no cómo estas cambian a lo largo de la ejecución.
 
6. *¿Qué es un estilo arquitectónico? Según “Software Architecture: Perspectives on an Emerging Discipline”(Shaw & Garlan 1996), los estilos arquitectónico pueden clasificarse en componentes independientes, flujo de datos, centrados en datos, de máquina virtual y de llamada/retorno. ¿A cuáles de estas categorías corresponden los estilos arquitectónicos descriptos en “An Integrated Approach to Software Engineering”?*

Un estilo arquitectónico es un conjunto de restricciones que definen una familia de arquitecturas que las satisfacen.

Pipe and filter:  flujo de datos
Estilo de datos compartidos: centrados en datos
Estilo cliente servidor:  llamada/retorno
Publicar-suscribir :de máquina virtual 
Estilo peer to peer:  componentes independientes
<!--?? No encontré el libro -->

7. *¿Qué es el middleware? Un sistema cuyas componentes se comunican a través de middleware, ¿a qué estilo arquitectónico puede corresponder?*
 El **middleware** es el software que brinda servicios y funciones comunes a las aplicaciones.
Cliente-Servidor, donde el middleware contiene lar reglas del servicio.

8. *¿Qué son las arquitecturas de software orientadas a servicios?*
Son un estilo de arquitectura que se enfoca en servicios discretos en vez de en el diseño monolítico. Se provee servicios a otros componentes por componentes de aplicación a través de un protocolo de comunicación.
Por ejemplo el estilo peer-to-peer y el estilo cliente-servidor.

9- *Considere las siguientes descripciones de sistemas a desarrollar, y proponga un diseño arquitectónico para potenciales soluciones a los mismos. Busque identificar estilos arquitectónicos adecuados para cada caso*
***
Un **compilador** está generalmente dividido en cuatro grandes porciones.
1. La primera de ellas es el **pre-procesador**, 
	+ Transforma el código fuente de entrada original en el código fuente puro.
	+ Es responsabilidad del pre-procesador el expandir las macros, incluir las librerías, etc..
2. La segunda porción de un compilador es la encargada del **proceso de compilación** 
	+ Recibe el código fuente puro, somete el mismo a un análisis lexicográfico, posteriormente a un análisis sintáctico, y a un análisis semántico.
	+ El resultado de este proceso es la construcción de una tabla de símbolos, y de un código intermedio, el cual se optimizaría para la producción de código de salida, generalmente en algún lenguaje ensamblador.
3. La tercera porción de un compilador
	+ se encarga de recibir un código fuente de entrada escrito en ensamblador, y produce otro código de salida, llamado código binario no enlazado.
4. Este código binario no enlazado es la entrada de la última de las porciones de un compilador,
	+ encargada de realizar el enlazado del código de fuente de entrada (código maquina relocalizable) con las librerías que necesita
	+ provee al código de las rutinas necesarias para poder ejecutarse y cargarse a la hora de llamarlo para su ejecución, modificar las direcciones relocalizables y ubicar los datos en las posiciones apropiadas de la memoria.
	+ Esta última fase es la que produce como salida el código binario enlazado.

Estilo Pipe&Filter.
***
Se desea desarrollar un **sistema de gestión de tránsito de un aeropuerto**.
Los registros de los pasajeros que vayan a tomar un tránsito serían introducidos por el personal perteneciente al departamento de embarque, que introduciría los datos personales del pasajero (nombre y apellido) y el número de vuelo.
El sistema proporcionaría al operario la lista de asientos libres de ese vuelo y el operario asignará uno al pasajero.
El sistema generaría entonces la tarjeta de embarque con los datos del pasajero (el número de pasajero, el número de asiento, el número de vuelo, el origen y el destino del vuelo y la compañía aérea) que le sería entrega al pasajero.
Si hubiera algún pasajero con asiento asignado que se diera de baja, el personal de embarque debería actualizar los datos del vuelo borrando los datos del pasajero y dejando el asiento libre para que pueda ser ocupado por otro pasajero.

Cualquier operario del departamento de embarque podría producir en cualquier momento un listado con los datos de los pasajeros (nombre, apellido y número de asiento) de un determinado vuelo, introduciendo en el sistema únicamente el número de vuelo.
Dicho informe sólo podría ser utilizado por los propios operarios del departamento de embarque o por los del departamento de seguridad.
El sistema también gestionará el equipaje de los pasajeros que vayan a tomar algún avión. Una vez que se ha gestionado la tarjeta de embarque, el operario seleccionaría la funcionalidad de gestión de equipaje si el pasajero en cuestión tiene equipaje.
El operario introduciría el número de vuelo, el número de pasajero y el peso del equipaje.
El sistema producirá una tarjeta con dichos datos que se colocará en el equipaje, para que los operarios del departamento de equipaje sepan a qué avión destinar cada maleta. El sistema actualizaría también los datos del pasajero indicando que lleva equipaje.
Si algún pasajero con asiento asignado que se diera de baja tuviera maletas, el personal de embarque debería llamar telefónicamente al departamento de equipajes para indicar que la maleta con el número de vuelo y de pasajero correspondiente al pasajero indicado no se cargue en el avión.

Estilo de datos compartido estilo repositorio

***
Se trata de diseñar un sistema que se utilizaría para **controlar una máquina recicladora** de botellas, frascos y cajas. 

Esta máquina puede ser utilizada por diferentes clientes, y cada cliente puede retornar los tres tipos de artículos (botella, frasco y caja) en la misma ocasión.

Dado que hay diferentes tipos de artículos, el sistema debe comprobar, para cada artículo, de que tipo es el devuelto. También se almacenaría cuantos artículos ha devuelto cada cliente.
Cuando un cliente solicite un recibo, el sistema imprimiría la cantidad que ha depositado, el valor de esos artículos y el total que se le abonaría al cliente.

El sistema también sería usado por un operador. Este querría saber cuantos artículos de cada tipo se han retornado durante el día; esta información se solicitaría y se imprimiría al final de cada día.
El operador también podría modificar información dentro de la máquina, como por ejemplo los valores de los depósitos de los diferentes artículos. Si surge algún problema, como el desborde del recipiente de algún artículo o bien se termina el papel de impresión, el operador sería avisado mediante una alarma.

***
