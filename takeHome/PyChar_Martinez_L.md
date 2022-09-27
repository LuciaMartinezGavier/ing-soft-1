# PyRobots
PyRobots es un juego web donde compiten robots. Los jugadores pueden programar el comportamiento de sus propios robots, crear, unirse y ejecutar partidas, ver sus estadísticas y ejecutar simulaciones.

Para jugar es necesario tener una cuenta en la plataforma y haberla verificado a través del email provisto. Un usuario puede crear y editar sus robots.

Una **simulación** permite ver competir en un juego a los robots propios (o los dos bot que provee por default el sistema), para verificar su correcto funcionamiento. 

También, se puede competir contra robots de otros usuarios, a través de una **partida** que consta de muchos juegos donde cada robot comienza en una posición aleatoria y el resultado de la partida se calcula a través de los resultados de cada juego individual. 

Un usuario puede crear una partida, otros usuarios pueden unirse con un robot, y solo el creador puede iniciarla. Al final de la partida, el sistema muestra los bots jugadores, el ranking de la partida y la cantidad de juegos sobrevividos de cada uno.

El ranking de la partida se determina por:  
+ Cantidad de juegos sobrevividos hasta el final.
+ Cantidad de vida promedio al final del juego.
+ Cantidad de rondas promedio que sobrevivió.

Los resultados de las partidas se verán reflejados en las estadísticas de cada robot participante, donde se podrá consultar la cantidad total de partidas jugadas, cantidad de partidas ganadas, empatadas y perdidas. Una partida se considera ganada si se tiene puesto 1 en el ranking; empatada, si el puesto 1 se comparte con otro(s) robot(s); y perdida, si el robot no ganó ni empató.

Los usuarios podrán ver un ranking de todos los robots en el sistema que se calcula por la cantidad de partidas ganadas o empatadas de cada bot. Además pueden consultar el historial de partidas que tiene un registro de todas las partidas finalizadas en la que participó el usuario; así como la lista de partidas creadas y aún no iniciadas y una lista de partidas disponibles para unirse.

### Datos y restricciones
#### Usuario
- **Email**: Debe ser único y tener formato de mail. Es obligatorio.  
- **Nombre**: Debe ser único. Es obligatorio. 
- **Contraseña**: Debe tener al menos 8 caracteres, al menos una mayúscula, al menos una minúscula y exactamente un guión. Es obligatorio.
- **Avatar**: Debe ser una imagen. 

#### Simulación
- **Cantidad de rondas**: Debe ser un número entero entre 1 y 10 000. Es obligatorio.                                                                                 
- **Robots**: No pueden ser más de 4 robots, ni menos de 2. Deben ser robots anteriormente subidos por el usuario o los provistos por el sistema. Es obligatorio.

#### Partida
- **Nombre**: Debe ser único. Es obligatorio.
- **Cantidad de juegos**: Debe ser un número  entero entre 1 y 10 000. Es obligatorio.
- **Cantidad de rondas por juego**: Debe ser un número entero entre 1 y 200. Es obligatorio.
- **Cantidad de jugadores**: Debe ser 2, 3 o 4. Es obligatorio.

#### Robot 
- **Nombre**: Debe ser único. Es obligatorio.
- **Avatar**: Debe ser una imagen.
- **Código**: Debe implementar al menos los métodos `initialize()` y  `response()`, no implementar métodos internos, y debe cumplir con restricciones de seguridad extra. Es obligatorio. 

 # Casos de uso
A continuación se especifican 6 casos de uso. Los conjuntos y validaciones de datos se pueden ver detalladas en la sección de *Alcance: Datos y Restricciones*.
 
## 1 Registrarse
+ **Caso de uso:** Registrarse
+ **Actor principal:** Actor externo.
+ **Pre-condición:** El actor externo no está logueado.
+ **Escenario exitoso:** 
	1. El actor externo solicita registrarse.
	2. El sistema le pide al actor externo que ingrese los datos necesarios para crear la cuenta.
	3. El actor externo ingresa sus datos.
	4. El sistema informa que se registró una nueva cuenta, y envía un mail de verificación.
+ **Escenarios excepcionales:**
	+ El actor externo no ingresa algún dato obligatorio: El sistema le informa qué campo debe completar.
	+ El actor externo ingresa un dato con un formato incorrecto: El sistema le informa qué campo debe corregir.
	+ El actor externo ingresa un mail que ya fue registrado: Se le informa que ya tiene un usuario en la plataforma con ese mail.
	+   El actor externo ingresa un nombre de usuario que ya fue registrado: Se le informa que ese nombre de usuario ya está tomado.

## 2 Cambiar Contraseña
+ **Caso de uso:** Cambiar password
+ **Actor principal:** Usuario
+ **Pre-condición:** El usuario debe estar logueado.
+ **Escenario exitoso:**
	1. El usuario emite una solicitud de cambio de contraseña. 
	2. El sistema le pide el usuario ingresar su contraseña actual y la nueva contraseña junto con una confirmación de la misma.
	3. El usuario ingresa llena los campos requeridos.
	4. El sistema informa que el cambio de contraseña fue exitoso. Finalmente, envía un mail al usuario notificando dicho cambio.
+ **Escenarios excepcionales:**
	+ El usuario ingresa mal su contraseña actual: Se le informa del error y se le permite intentar de nuevo.
	+ El usuario ingresa una contraseña nueva que no cumple las restricciones: Se le informa del error y se le permite intentar de nuevo.
	+ La confirmación de la nueva contraseña no es igual a la contraseña nueva: Se informa al usuario del error y se le permite intentar de nuevo.

## 3 Ejecutar Simulación
+ **Caso de uso:** Ejecutar simulación
+ **Actor principal:** Usuario
+ **Pre-condición:** El usuario debe estar logueado y su cuenta debe haber sido verificada.
+ **Escenario exitoso:**
	1. El usuario solicita iniciar una simulación.
	2. El sistema le pide al usuario que ingrese los datos de una simulación.
	3.  El usuario ingresa los datos pedidos.
	4. El sistema reproduce la batalla de robots que se muestra en tiempo real hasta completar la cantidad de rondas pautadas. Una vez completada, el sistema muestra los resultados de la simulación.
+ **Escenarios excepcionales:**
	+ No es válida la cantidad de rondas o se seleccionaron más robots que los permitidos: Se le informa al usuario del error y se le permite volver a intentar.

## 4 Crear una Partida
+ **Caso de uso:** Crear una partida.
+ **Actor principal:** Usuario
+ **Pre-condición:** El usuario debe estar logueado y su cuenta debe haber sido verificada.
+ **Escenario exitoso:**
	1. El usuario solicita crear una partida.
	2. El sistema le pide al usuario ingresar los datos de la partida y elegir su robot.
	3. El usuario ingresa los datos solicitados y especifica cuál de sus robots quiere usar.
	4. El sistema agrega la partida a la lista de partidas disponibles. Y muestra una confirmación de que se creó con éxito.
+ **Escenarios excepcionales:**
	+ No se completan o especifican todos los datos de la partida: El sistema informa al usuario los campos faltantes y le permite volver a intentar.
	+ Alguno de los datos no es válido: Se le informa al usuario del error y se le permite volver a intentar.

## 5 Ejecutar Partida
+ **Caso de uso:** Ejecutar partida
+ **Actor principal:** Usuario
+ **Pre-condición:** El usuario debe estar logueado. El usuario creó una partida que actualmente se encuentra llena.
+ **Escenario exitoso:** 
	1. El usuario solicita ejecutar una partida.
	2. El sistema computa los resultados de los juegos, y muestra las estadísticas de dicha partida.

## 6 Subir un robot
+ **Caso de uso:** Subir un robot.
+ **Actor principal:** Usuario.
+ **Pre-condición:** El usuario debe estar logueado y su cuenta debe haber sido verificada.
+ **Escenario exitoso:**
	1. El usuario solicita subir un robot.
	2. El sistema le pide al usuario completar la información asociada a un robot.
	3. El usuario ingresa los datos solicitados.
	4. El sistema informa al usuario que se subió el robot correctamente.
+ **Escenarios excepcionales:**
	+ El robot subido tiene algún campo no válido: Se le informa al usuario del error y se le permite corregirlo.
	+ El usuario no completó todos los datos obligatorios: El sistema informa del campo faltante y le pide al usuario que lo ingrese.

