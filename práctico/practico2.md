# Práctico 2: Análisis y Especificación de Requerimientos

1- _¿Qué especifican los requisitos de funcionalidad? ¿Qué otras componentes conforman la especificación de los requisitos del software? Dé al menos dos ejemplos de características que especifiquen cada una de ellas._

Los requisitos de funcionalidad especifican todas las funciones que el sistema debe proveer; qué salidas debe producir para cada entrada y las relaciones entre ellas; y las entradas válidas y las verificaciones de validez de la entrada y salida.

La especificación de los requisitos del software también es conformada por los requerimientos de desempeño, restricciones de diseño, requerimientos de interfaces externas.

**Ejemplos:**
Requerimientos sobre funcionalidad

- El sistema debe proveer _x_ función.
- Cuando el sistema reciba _x_ entrada, debe producir _y_ salida.

Requerimientos sobre desempeño

- El sistema debe proveer una respuesta en menos de _x ms_.
- Se deben aceptar _x_ usuarios simultáneamente.

Restricciones de diseño

- Se debe seguir _x_ estándar para _y_ operación.
- Debe ser compatible con _x_ sistema.

Requerimientos de interfaces externas

- La interfaz debe tener _x_ feature de accesibilidad.
- Debe usarse _x_ fuente de tamaño _y_, para que sea legible.

  2- _¿Cuál es el objetivo de realizar el análisis de requisitos?_

Entender al cliente. Descubrir qué se pretende del producto para producir el software. Tener las pautas para generar el SRS correctamente.

3- _¿Cuál es el objetivo de realizar la especificación de los requisitos?_

Tener una especificación concisa establece el contrato entre el cliente y el proveedor respecto a lo que el software va a hacer, es necesario para comprender las necesidades. También funciona como documento legal en caso de que luego de entregado haya malos entendidos, y provee una referencia para la validación del producto final. Y finalmente es necesaria para minimizar cambios y errores en los requerimientos.

4- _¿Qué características debe tener una especificación de requisitos? Enumérelas y describa las dos que considera más importantes. Justifique su elección. Elija tres de las características restantes y explique qué problemas ocurrirían si una especificación no las poseyera._

1. Correcta
2. Completa
3. No ambigua
4. Consistente
5. Verificable
6. Rastreable
7. Modificable
8. Ordenada en aspectos de importancia y estabilidad

**Dos más importantes**:

- **No ambigua**: Cada requerimiento tiene exactamente un significado. Que no haya cosas subjetivas: "rápido" "lindo" . Si la especificación es ambigua va a llevar a la mayor cantidad de errores porque al tener requerimientos que se pueden interpretar de diversas maneras es posible que el cliente y el desarrollador piensen de formas diferentes y se arrastren errores de requerimientos.
- **Completa**: Todas las características deseadas por el cliente están descritas.  
  `cliente -> determina -> SRS`. Si no es **completa** puede haber necesidades del cliente que no estén satisfechas por un error de especificación. Lo cual llevará a tener que rehacer o corregir porciones del software lo cual es caro. Y es posible que tanto cliente como desarrollador terminen pasando una mala experiencia.

- Si no es **modificable**: será mucho más costoso si el cliente desea hacer alguna modificación, lo cual es muy probable que suceda. Pueden ocurrir errores si la especificación de requerimientos no está organizada y ordenada.
- **Rastreable**: Es importante para asegurarse que todas las necesidades y los deseos del cliente fueron satisfechos. También podría ocurrir que un cliente desee ver donde está _x_ funcionalidad en el código (a punto de ir a juicio) y necesitamos poder mostrarlo.
- **Consistente**: si la especificación se contradice es imposible hacer el proceso de diseño correctamente.

5- _¿Cuáles son los tipos de errores más comunes en el desarrollo de una especificación de requisitos? Descríbalos brevemente._

| Error              | Frecuencia | Descripción                                                                                               |
| ------------------ | ---------- | --------------------------------------------------------------------------------------------------------- |
| Omisión            | 30%        | No se describen todos las funcionalidades que el cliente necesitaba.                                      |
| Inconsistencia     | 10-30 %    | Hay especificaciones que se contradicen.                                                                  |
| Hechos incorrectos | 10-30 %    | Hay puntos en la SRS que no se corresponden con una necesidad o deseo del cliente.                        |
| Ambigüedad         | 5-20 %     | Hay requerimientos que pueden tener más de una interpretación, y cliente y desarrollador no coincidieron. |

6- _¿Es posible contar con un sistema que pueda verificar automáticamente la consistencia de un documento SRS?_
Si, si se utilizan lenguajes formales.
_¿Y que pueda verificar automáticamente su completitud? Justifique su respuesta._
No, porque eso depende de lo que el cliente dice y de lo que el proveedor interpreta.

7- _¿Es útil contar con métricas en la etapa de análisis de requisitos? Describa brevemente las métricas de tamaño y calidad discutidas en “An Integrated Approach to Software Engineering”(Jalote)._

Si, para poder estimar costos y tiempos, y planear el proyecto se necesita medir el esfuerzo que demandará.

**Punto función**: define el tamaño en términos de la funcionalidad.
Se determinan diferentes _tipos de funciones_ , la cantidad de cada tipo y para cada una un nivel de complejidad entre _compleja_, _promedio_ o _simple_. Se calcula el UFP (punto función no ajustado). Luego, de acuerdo a diferentes características de determina la _complejidad del entorno_ y con esa información se calcula el CAF (factor de ajuste de complejidad). Y finalmente el punto función es CAF \* UFP.

**Métricas de calidad para evaluar la calidad de la SRS**.
_Métricas de calidad directa_: Evalúan la calidad del documento estimando el valor de los atributos de calidad de la SRS.

_Métricas de calidad indirecta_: Evalúan la efectividad de las métricas de control de calidad usadas en el proceso en la fase de requerimientos. El proceso debe estar bajo control estadístico.

8- _Considere los siguientes problemas, y realice análisis orientado a objetos para cada uno de ellos. Describa además los requisitos funcionales asociados a estos problemas mediante casos de uso_

Se desea desarrollar un sistema informático para **controlar los préstamos** de la biblioteca de una institución.

Los estudiantes y otros usuarios de la biblioteca son los que:

- toman los libros de las estanterías,
- los leen,
- los sacan en préstamo,
- los devuelven y
- consultan el catálogo de ejemplares disponibles.

Cada **libro** tiene un _código de barras_ que lo identifica. Adicionalmente dispone de un _dispositivo electrónico antirrobo_ situado debajo del código de barras, siendo el sistema el encargado de activarlo y desactivarlo.

<!--Caso de uso: obtener un préstamo -->

Cuando un usuario desea obtener en préstamo un libro:

1. se sitúa con él delante del sistema de préstamo. Primeramente pasa por el lector su tarjeta de socio.
2. A continuación se produce la lectura del código de barras de los libros que desee obtener en préstamo. Si el socio no tiene préstamos vencidos el sistema desbloquea el código antirrobo del libro. En una misma operación se pueden obtener varios libros en préstamo. El proceso termina pulsando un botón de finalización.
   <!-- Caso de uso: devolver un libro -->
   El procedimiento de devolución de libros funciona de un modo análogo.

<!-- Caso de uso: ser admitido en la biblioteca como socio -->

Para ser admitido en la biblioteca como socio, un usuario tiene que ser dado de alta por el personal de la biblioteca.

1. A partir de los datos del usuario
2. el sistema genera una tarjeta de socio.

El personal de la biblioteca se encarga de las labores de mantenimiento de libros y de socios, y de las consultas relativas al estado de los **socios** y los **libros**.

Los socios pueden:

- realizar búsquedas sobre el catálogo disponible (por autor, título, palabras clave, etc.).
- Existe un tratamiento uniforme con respecto a la política de préstamos: cada libro que no se devuelva en el plazo estipulado originaría una _sanción_ al socio correspondiente.

<!-- Caso de estudio excepcional. socio intenta salir del edificio con un libro bloqueado-->

- En la puerta de salida de la biblioteca existe un _dispositivo de seguridad_; éste se activa bloqueando las puertas en el momento en el que un socio intenta salir del edificio con un libro que tenga el código antirrobo activado.
- Pulsando un botón de emergencia las puertas se desbloquean.

Existen **diferentes tipos de usuarios** con diferentes plazos de devolución de libros. Los **docentes o personal** de la institución pueden retirar libros por un mes, mientras que los **estudiantes** solo pueden hacerlo por una semana.

En caso que un libro en el cual un cliente está interesado esté prestado, el cliente puede **reservarlo**, en cuyo caso se rechazarán los pedidos de renovación de préstamos que los usuarios de la biblioteca pueden realizar, para extender el plazo de préstamo una vez que éste ha vencido.

La reserva del libro correspondiente se mantiene por 12 horas a partir del momento de devolución. Luego de este tiempo, todos los usuarios de la biblioteca pueden acceder al libro.

Algunos libros son exclusivamente de consulta en la biblioteca, y por lo tanto los usuarios no pueden retirarlos de la biblioteca.

**Casos de uso**

<!--Caso de uso: obtener un préstamo -->

Caso de uso: `Un usuario obtiene un préstamo`
Actor primario: `usuario`
(pre-condición: `el usuario debe ser socio`)
Escenario exitoso principal:
`paso1: El usuario pasa por el lector su tarjeta de socio`
`paso2: El sistema verifica que el socio no tiene préstamos vencidos, desbloquea el código antirrobo.`
`paso3: el usuario pulsa un botón de finalización y sale por la puerta`

Escenarios excepcionales:
`si el socio tiene préstamos vencidos: se le deniega el préstamo`
`si el usuario sale por la puerta con un libro tiene el código antirrobo activo: se bloquean las puertas en el momento en el que la persona intenta salir del edificio con el libro (Pulsando un botón de emergencia las puertas se desbloquean).
``

<!-- Caso de uso: devolver un libro -->

Caso de uso: `Un usuario devuelve un libro`
Actor primario: `usuario`
(pre-condición: `el usuario debe ser socio y haber tomado un libro`)
Escenario exitoso principal:
`paso1: El usuario pasa por el lector su tarjeta de socio`
`paso2: El sistema, bloquea el código antirrobo.`
`paso3: el usuario pulsa un botón de finalización`

<!-- Caso de uso: ser admitido en la biblioteca como socio -->

Caso de uso: `Un usuario es admitido en la biblioteca como socio`
Actor primario: `usuario`
Escenario exitoso principal:
`paso1: El usuario ingresa sus datos al sistema`
`paso2: El sistema genera una tarjeta de socio`
Escenarios excepcionales:
`si el usuario ya es socio: se le deniega una nueva tarjeta`

Los socios pueden:

- realizar búsquedas sobre el catálogo disponible (por autor, título, palabras clave, etc.).
  <!--Caso de uso: obtener un préstamo -->
  Caso de uso: `Un socio realiza una búsqueda sobre el catálogo`
  Actor primario: `socio`
  Escenario exitoso principal:
  `paso1: El socio introduce autor, título o palabras clave`
  `paso2: El sistema devuelve todas las entradas que coincidan con la búsqueda`

<!-- Duda: se deben incluir casos de uso que forman parte del sistema pero no del software? por ejemplo: persona entra y sale de la biblioteca, para poder hablar del sistema de seguridad. No
Mejor ver si se puede incluir en un caso de uso particular. -->

![](p2-ej8a.png)

Se desea desarrollar un sistema informático para la **gestión de las reservas de las habitaciones de un hotel**.

Cada **reserva** estará a nombre de un **cliente**, que proporcionará un _número de tarjeta de crédito_ para efectuar el pago. El número de tarjeta de crédito es indispensable para poder realizar la reserva. Se podría reservar _habitación_ para cierto _número de días consecutivos_.

Cuando el cliente se presenta para aprovechar la reserva en la fecha de comienzo indicada, el sistema pasa la reserva a la _situación de ocupada_.

Cuando llega la fecha de terminación de la reserva, o si el cliente solicita la terminación anticipada, el sistema pasa la reserva a la _situación de terminada_ y tramita la creación de una **factura**, que se cobrará en general automáticamente de la _tarjeta de crédito_ del cliente. El cliente tiene sin embargo la opción de otras _formas de pago_ al finalizar la reserva (contado, tarjeta de crédito alternativa, etc.).

El cliente puede _cancelar una reserva_ hasta una semana antes de la fecha inicial, en cuyo caso no se le pasaría al cobro factura alguna. En caso de cancelar la reserva con menos de 7 días de anticipación, se le cobrará de su tarjeta de crédito el valor correspondiente a un día de hospedaje.

Caso de uso: `El cliente cancelar una reserva`
Actor primario: `cliente`
Precondición: `el cliente tiene una reserva`
Escenario exitoso principal:
`paso1: el cliente cancela su reserva`
`paso2: El sistema chequea que se cancele hasta una semana antes de la fecha inicial y elimina la reserva`
Escenarios excepcionales:
`Si se cancela con menos de 7 días de anticipación, se cobra de la tarjeta de crédito el valor correspondiente a un día de hospedaje`

Caso de uso: `Un cliente reserva una habitación`
Actor primario: `cliente`
Escenario exitoso principal:
`paso1: El usuario proporciona sus datos, un número de tarjeta de crédito y los días que desea reservar`
`paso2: El sistema verifica que los datos sean válidos y que haya disponibilidad. Y confirma la reserva`
Escenarios excepcionales:
`Si no hay disponibilidad o si la tarjeta de crédito no es válida; se muestra un mensaje que describa el error`

Caso de uso: `El cliente se presenta para aprovechar su reserva`
Actor primario: `cliente`
Escenario exitoso principal:
`paso1: El cliente especifica su reserva`
`paso2: El sistema verifica que el cliente haya reservado y coincidan los días. Y pasa la reserva a la situación de ocupada`
Escenarios excepcionales:
`La reserva del cliente no es correcta: ...`

Caso de uso: `El cliente se termina su estadía`
Actor primario: `cliente`
Pre-condición: `el cliente tiene una reserva a su nombre`
Escenario exitoso principal:
`paso1: El cliente solicita la terminación anticipada o llega la fecha de terminación de la reserva y especifica (o no) una opción de pago`
`paso2: El sistema pasa la reserva a la situación de terminada y genera una factura. Si el cliente no especifica una opcion de pago, el sistema automáticamente cobrará de la tarjeta de crédito.`

![](p2-ej8b.png)

---

El campus de una Universidad cuenta con un conjunto de aulas.
Cada aula tiene ciertos **equipamientos** disponibles, que pueden incluir **elementos** tales como micrófonos, sistema de audio, pizarras, proyector, televisión, conexión a internet, etc..

Por su parte, cada uno de los equipos posee cierta información asociada, como _historial de uso_, _condición actual_, _forma en la que está disponible_ (instalado en un aula e inamovible, o disponible para ser trasladado a distintas aulas);
estos elementos también cuentan con información más específica, tal como _tamaño_ para el caso de las **pizarras** y **televisores**, _inalámbricos_ o no para el caso de los **micrófonos**, etc..

Cada **aula** tiene una lista de **cursos**, planificados para llevarse a cabo en la misma, el _instructor_ de cada uno d como así también permitir a este personal comunicar sobre actualizaciones en el estado de los equipos, estado de las configuraciones solicitadas, etc..
e los cursos, el _equipamiento_ a utilizarse en el curso, y la _persona encargada de configurar los equipos_, en los casos en los que hiciera falta.

Se desea desarrollar un sistema que **permita administrar la asignación de aulas y equipamiento**.

El sistema debería, entre otras cosas,

- permitir a los instructores y otros usuarios consultar los equipamientos disponibles en un aula,
- requerir equipos y personal para su configuración,
- y consultar sobre la disponibilidad de aulas con ciertas características.
- El sistema debería informar al personal encargado de realizar las configuraciones de equipos y tareas asociadas sobre nuevos pedidos,
- como así también permitir a este personal comunicar sobre actualizaciones en el estado de los equipos, estado de las configuraciones solicitadas, etc..

**Casos de uso**
_Caso de uso:_ Un usuario consulta los equipamientos disponibles en un aula
_Actor primario:_ Usuario
_Escenario exitoso principal:_

- El usuario consulta los equipamientos especificando el número de aula.
- El sistema devuelve una lista de los equipos disponibles.
  _Escenarios excepcionales:_
- El aula ingresada no existe: Se le informa al usuario que el número de aula no es correcto.

_Caso de uso:_ Un instructor consulta disponibilidad y requiere equipos.
_Actor primario:_ Instructor
_Escenario exitoso principal:_

- El instructor especifica los equipos que necesita y la fecha en que serán utilizados.
- El sistema muestra las opciones disponibles de aulas que tengan los equipos inamovibles requeridos y opciones de equipos móviles.
- El instructor comienza una solicitud, eligiendo los equipos deseados, y presiona _"solicitar equipos"_
- El sistema pide el código de curso para iniciar la solicitud
- El instructor ingresa el código de curso
- El sistema asigna los equipos al aula. Y retorna al instructor los datos del aula y los equipos disponibles para la fecha indicada.
- El instructor finaliza la solicitud apretando _"aceptar"_ .
- El sistema notifica al encargado, le provee información de los equipos reservados para esa fecha en esa aula y el número de aula.
  _Escenarios excepcionales:_
- El código de curso no existe: Se informa que el código no es correcto.
- Hay algún equipo que no está disponible: El sistema devuelve un mensaje de error y propone solo la reserva de los equipos disponibles.

_Caso de uso:_ El personal de configuración de equipos comunica actualizaciones en el estado de los equipos.
_Actor primario:_ Persona encargada de la configuración de los equipos
_Pre-condición:_ El encargado debe estar loggeado.
_Escenario exitoso principal:_

- El encargado ingresa al sistema el ID del equipo.
- El sistema retorna los datos del equipo y permite modificaciones.
- El encargado actualiza el estado del equipo y presiona _aceptar_.
- El sistema actualiza los datos y comunica si la actualización fue exitosa.

(diagrama de clases en papel)

---

Se desea desarrollar un **buscaminas tradicional.**
El buscaminas es un juego simple de un **jugador**, que consiste en, dada una **grilla** de 8 × 8 casillas cubiertas, 10 de las cuales alojan minas, despejar todas las casillas de la misma que no oculten una mina.
Al ser descubierta una casilla, si la misma aloja una mina entonces se pierde el juego.
En cambio, si la casilla no está ocupada por una mina, se muestra en la misma un número, correspondiente a la cantidad de minas circundantes a la casilla descubierta.

Al descubrir una casilla a la cual le corresponde el número cero, todas sus vecinas se descubren automáticamente.
El juego debe producir configuraciones de la grilla aleatoriamente (con respecto a la ubicación de las minas).
Además, debe llevar cuenta del tiempo que el jugador insume en cada instancia de juego; el objetivo de esto último es mantener un ranking con los mejores cinco tiempos obtenidos. Cuando el desempeño de un jugador le permite acceder al ranking (venciendo a al menos uno de los cinco que lo ocupan en ese momento), se le permite ingresar su nombre.

(diagrama de clases en papel)
