 # Casos de uso
A continuación se especifican 6 casos de uso. Los conjuntos y validaciones de datos se pueden ver detalladas en la sección de Alcance.
 
## 1 Registrarse
+ **Caso de uso:** Registrarse
* **Actor principal:** Usuario no registrado.
* **Pre-condición:** El usuario no está logueado.
+ **Escenario exitoso:** 
	1. El usuario ingresa sus datos.
	2. El sistema verifica la validez de los datos, y envía un mail de verificación.
	3. El usuario, recibe el mail y lo verifica.
	4. El sistema registra efectivamente al nuevo usuario y muestra una confirmación.
+ **Escenarios excepcionales:**
	+ El usuario no ingresa algún dato obligatorio: El sistema le informa qué campo debe completar.
	+ El usuario ingresa un dato con un formato incorrecto:  El sistema le informa qué campo debe corregir.
	+ El usuario ingresa un mail que ya fue registrado: Se le informa que ya tiene un usuario en la plataforma con ese mail.
	+   El usuario ingresa un nombre de usuario que ya fue registrado: Se le informa que ese nombre de usuario ya está tomado.

## 2 Cambiar Password
+ **Caso de uso:** Cambiar password
+ **Actor principal:** Usuario
+ **Pre-condición:** El usuario debe estar logueado
+ **Escenario exitoso:**
	1. El usuario emite una solicitud de cambio de contraseña. Para ello ingresa su contraseña actual y la nueva contraseña junto con una confirmación de la misma.
	2. El sistema verifica que la contraseña nueva sea igual a su confirmación. Verifica que el formato sea válido. Informa que el cambio de contraseña fue exitoso. Y envía un mail al usuario notificando el cambio de contraseña.
+ **Escenarios excepcionales:**
	+ El usuario ingresa mal su contraseña actual: Se le informa del error y se le permite intentar de nuevo.
	+ El usuario ingresa una contraseña nueva inválida, o la confirmación de la nueva contraseña no es correcta: Se le informa del error y se le permite intentar de nuevo.

## 3 Ejecutar Simulación
+ **Caso de uso:** Ejecutar simulación
+ **Actor principal:** Usuario
+ **Pre-condición:** El usuario debe estar logueado
+ **Escenarios exitosos:**
	1. El usuario inicia una simulación ingresando los parámetros de la simulación.
	2. El sistema verifica la validez de los datos ingresados, genera el tablero, posiciona aleatoriamente los bots en este y reproduce la pelea de bots que se muestra en tiempo real hasta completar la cantidad de rondas pautadas. Una vez completada, el sistema genera y muestra las estadísticas de los resultados de la simulación.
+ **Escenarios excepcionales:** 
	+ No es válida la cantidad de rondas o la cantidad de bots: Se le informa al usuario del error y se le permite volver a intentar.

## 4 Crear una Partida
+ **Caso de uso:** Crear una partida.
+ **Actor principal:** Usuario
+ **Pre-condición:** El usuario debe estar logueado.
+ **Escenario exitoso:**
	1. El usuario ingresa  los datos de la partida y especifica cuál de sus robots quiere usar.
	2. El sistema crea la partida, queda disponible en la lista de partidas. Y muestra una confirmación de que se creó con éxito.
+ **Escenarios excepcionales:**
	+ No se completan especifican todos los datos de la partida: El sistema informa al usuario los campos faltantes y le permite volver a intentar.
	+ Alguno de los datos no es válido: Se le informa al usuario del error y se le permite volver a intentar.

## 5 Ejecutar Partida
+ **Caso de uso:** Ejecutar partida
+ **Actor principal:** Usuario
+ **Pre-condición:** El usuario debe estar logueado. El usuario creó una partida que actualmente se encuentra llena.
+ **Escenarios exitosos:** 
	1. El usuario solicita ejecutar la partida.
	2. El sistema computa los resultados de los juegos, y muestra las estadísticas de la partida. El sistema también actualiza las estadísticas de todos los bots que participaron. 

## 6 Subir un bot
+ **Caso de uso:** Subir un bot.
+ **Actor principal:** Usuario.
+ **Pre-condición:** El usuario debe estar logueado.
+ **Escenarios exitosos:**
	+ El usuario ingresa la información necesaria.
	+ El sistema verifica que la información esté completa y sea válida; agrega el bot en la lista de bots del usuario e inicializa las estadísticas. Finalmente informa al usuario que se subió el bot correctamente.
+ **Escenarios excepcionales:**
	+ El bot subido tiene algún campo no válido: Se le informa al usuario del error y se le permite corregirlo.
	+ El usuario no completó todos los datos obligatorios: El sistema  le informa el campo faltante y le pide que lo ingrese.


## Todos los casos de uso
### Relacionados al usuario
- Registrar usuario
- Loguear usuario
- Cambiar contraseña
- Recuperar contraseña
- Cambiar avatar

### Relacionado a una simulación
- Ejecutar simulación

### Relacionados a  una partida
- Crear partida
- Ejecutar partida
- Unirse a la partida
- Entrar al lobby (rondas, juegos, jugadores unidos).
- Ver partidas disponibles
- Ver partidas creadas (no terminadas)
- Ver historial de partidas terminadas
- Salir de la partida 

### Relacionados a las estadísticas
+ Ver estadísticas generales de los robots del usuario.
+ Ver estadísticas particulares de un robot.
+ Ver estadísticas de partida.

### Relacionados a los robots
+ Subir robot
+ Eliminar robot
+ Cambiar código de robot
+ Cambiar avatar de robot

