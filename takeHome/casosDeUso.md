 # Casos de uso
## 1 Registrarse
+ **Caso de uso:** Registrarse
* **Actor principal:** Potencial usuario
+ **Escenario exitoso:** 
	1. El usuario ingresa *email*, *nombre de usuario*, *contraseña*, y opcionalmente *imagen de avatar*.
	2. El sistema verifica la validez de los datos, y envía un mail de verificación.
	3. El usuario, recibe el mail y lo verifica
	4. El sistema registra efectivamente al nuevo usuario y le muestra al usuario una confirmación. 
+ **Escenarios excepcionales:**
	+ El usuario no ingresa algún dato obligatorio o alguno inválido: El sistema le informa de qué campo debe corregir.
	+ El usuario ingresa un mail o un usuario que ya fue registrado: Se le informa que ya tiene un usuario en la plataforma con ese mail o que ese nombre de usuario ya está tomado.

## 2 Cambiar Password
+ **Caso de uso:** Cambiar password
+ **Actor principal:** Usuario
+ **Pre-condición:** El usuario debe estar loggeado
+ **Escenario exitoso:**
	1. El usuario emite una solicitud de cambio de contraseña ingresando su contraseña actual y la nueva contraseña dos veces .
	2. El sistema verifica que la contraseña nueva sea igual en ambos campos. Y verifica que sea válida: al menos 8 caracteres, mayúsculas y minúsculas y un guión. E informa que el cambio de contraseña fue exitoso.
+ **Escenarios excepcionales:**
	+ El usuario ingresa mal su contraseña actual: Se le informa del error y se le permite intentar de nuevo.
	+ El usuario ingresa una contraseña nueva inválida, o la confirmación de la nueva contraseña no es correcta: Se le informa del error y se le permite intentar de nuevo.

## 3 Ejecutar Simulación
+ **Caso de uso:** Iniciar simulación
+ **Actor principal:** Usuario
+ **Pre-condición:** El usuario debe estar loggeado
+ **Escenarios exitosos:**
	1. El usuario inicia una simulación ingresando: la cantidad de rondas y eligiendo los bots que van a pelear.
	2. El sistema verifica la validez de los datos ingresados, genera el tablero, posiciona aleatoriamente los bots en este y la pelea de bots que se muestra en tiempo real hasta completar la cantidad de rondas pautadas.
	3. El usuario puede pausar esta simulación o verla completamente.
	4. Una vez completada, el sistema genera y muestra las estadísticas de los resultados de la simulación.
+ **Escenarios excepcionales:** 
	+ No es válida la cantidad de rondas o la cantidad de bots: Se le informa al usuario del error y se le permite volver a intentar.

## 4 Crear una Partida
+ **Caso de uso:** Crear una partida
+ **Pre-condición:** El usuario debe estar loggeado
+ **Actor principal:** Usuario
+ **Escenario exitoso:**
	1. El usuario ingresa cantidad de juegos, cantidad de rondas por juego, cantidad de jugadores, nombre.
	2. El sistema crea la partida, y queda disponible en la lista de partidas.
+ **Escenarios excepcionales:**
	+ La cantidad de juegos, cantidad de rondas o cantidad de jugadores no es válida: Se le informa al usuario del error y se le permite volver a intentar.

## 5 Ejecutar Partida
+ **Caso de uso:** Iniciar partida
+ **Actor principal:** Usuario Creador de la partida
+ **Pre-condición:** El usuario debe estar loggeado y haber creado una partida previamente.
+ **Escenarios exitosos:** 
	1. El usuario inicia la partida.
	2. El sistema verifica que estén todos los jugadores presentes, computa los resultados de los juegos, y muestra los resultados acumulados con porcentajes de los juegos ganadas de cada bot. El sistema también actualiza las estadísticas de todos los bots que participaron. 
	3. Los usuarios que participaron pueden volver al lobby.
+ **Escenarios excepcionales:**
	+ Si no están todos los jugadores especificados: El sistema no permite iniciar la partida, muestra un mensaje de error y el usuario debe esperar a que se unan todos.
	+ Un bot levanta una excepción en tiempo de ejecución: Pierde ese bot.

## 6 Subir un bot
+ **Caso de uso:** Subir un bot
+ **Actor principal:** Usuario
+ **Pre-condición:** El usuario debe estar loggeado
+ **Escenarios exitosos:**
	+ El usuario ingresa el código en *Python* que puede ser un archivo o se puede ingresar desde el editor de texto que ofrece el juego. El código debe implementar al menos los métodos `initialize()` y `response()`... (agregar más restricciones)
	+ El sistema verifica que el bot sea legal y válido (implemente los métodos necesarios, no tenga métodos internos, ... (completar)); agrega al bot en la lista de bot del usuario e inicializa las estadísticas. Finalmente informa al usuario que se subió el bot correctamente.
+ **Escenarios excepcionales:**
	+ El bot tiene algún aspecto no válido o algún error de sintaxis: No se le permite al usuario agregar ese bot. Se le informa del error.


## Otros casos de uso
1. Loguearse
2. Unirse a la partida
3. Restablecer contraseña
4. Ver estadísticas de mis bots


## Preguntas
+ ¿Cómo se llama el actor que todavía no es usuario? ¿Es el mismo que está por iniciar sesión?
+ ¿Pausar simulación está bien que sea un método de simulación?
+ Subir_robot es un método de robot?
+ Cuando uno crea  la partida debe elegir su robot? O lo hace al iniciarla?