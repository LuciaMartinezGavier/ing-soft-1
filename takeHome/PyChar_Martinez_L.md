# PyRobots
## Alcance
PyRobots es un juego web donde compiten robots. Los jugadores pueden programar el comportamiento de sus propios robots, crear, unirse y ejecutar partidas, ver sus estadísticas y ejecutar simulaciones.

Para jugar es necesario tener una cuenta en la plataforma y haberla verificado a través del email provisto. Un usuario puede crear, editar y eliminar sus robots.

Una **simulación** permite ver competir en un juego a los robots propios (o los dos bot que provee por default el sistema), para verificar su correcto funcionamiento. 

También, se puede competir contra robots de otros usuarios, a través de una **partida** que consta de muchos juegos donde cada robot comienza en una posición aleatoria y el resultado de la partida se calcula a través de los resultados de cada juego individual. 

Un usuario puede crear una partida, otros usuarios pueden unirse con un robot, y solo el creador puede iniciarla. Al final de la partida, el sistema muestra las estadísticas relacionadas a la partida y estas se reflejan en las estadísticas de cada robot participante.

### Datos y restricciones
#### Usuario

| Dato       | obligatorio | Restricciones                                                                                       |     |
| ---------- | ----------- | --------------------------------------------------------------------------------------------------- | --- |
| Email      | Sí          | Ser único. Tener formato de mail                                                                    |     |
| Nombre     | Sí          | Ser único.                                                                                          |     |
| Contraseña | Sí          | Tener al menos 8 caracteres, al menos una mayúscula, al menos una minúscula y exactamente un guión. |     |
| Avatar     | No          | Ser una imagen.                                                                                     |     |

#### Simulación

| Dato               | Obligatorio | Restricciones                                                                                                          |     |
| ------------------ | ----------- | ---------------------------------------------------------------------------------------------------------------------- | --- |
| Cantidad de rondas | Sí          | Ser un número entero entre 1 y 10 000.                                                                                 |     |
| Robots             | Sí          | No ser más de 4 robots, ni menos de 2. Ser robots anteriormente subidos por el usuario o los provistos por el sistema. |     |

#### Partida

| Dato                         | Obligatorio | Restricciones                           |
| ---------------------------- | ----------- | --------------------------------------- |
| Nombre                       | Sí          | Ser único.                              |
| Cantidad de juegos           | Sí          | Ser un número  entero entre 1 y 10 000. |
| Cantidad de rondas por juego | Sí          | Ser un número entero entre 1 y 200.     |
| Cantidad de jugadores        | Sí          | Ser 2, 3 o 4.                           |

#### Robot 

| Dato   | Obligatorio | Restricciones                                                                                                                                                                 |
| ------ | ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nombre | Sí          | Ser único                                                                                                                                                                     |
| Avatar | No          | Ser una imagen.                                                                                                                                                               |
| Código | Sí          | Implementar al menos los métodos `initialize()` y  `response()`. No implementar métodos internos. No tener errores de sintaxis. Cumplir con restricciones de seguridad extra. |

#### Estadísticas asociadas a una partida o simulación.
Por cada jugador se muestra:  
+ **Ranking**.
+ **Nombre** del robot que usó.
+ Porcentaje de **juegos sobrevividos**.

El ranking se determina por:  
+ Cantidad de juegos sobrevividos hasta el final.
+ Cantidad de vida promedio al final del juego.
+ Cantidad de rondas promedio que sobrevivió.
+ Si todavía hay un empate entonces tienen el mismo número de ranking.

#### Estadísticas asociadas a un robot
Un jugador puede ver las estadísticas de su robot. En ellas, se encuentra la siguiente información:
+ Cantidad total de **partidas jugadas**.
+ Cantidad de **partidas ganadas** 
+ Cantidad de **partidas empatadas** (se considera un empate cuando dos o más robots tienen ranking 1).
+ Porcentaje de **partidas perdidas** (un robot pierde cuando no tiene ranking 1).

#### Estadísticas generales
+  Por cada robot en el sistema se ve la cantidad de partidas jugadas y el porcentaje de ganadas y perdidas.

 # Casos de uso
A continuación se especifican 6 casos de uso. Los conjuntos y validaciones de datos se pueden ver detalladas en la sección de Alcance: Datos y Restricciones.
 
## 1 Registrarse
+ **Caso de uso:** Registrarse
* **Actor principal:** Usuario no registrado.
* **Pre-condición:** El usuario no está logueado.
+ **Escenario exitoso:** 
	1. El usuario ingresa sus datos.
	2. El sistema informa que se registró una nueva cuenta, y envía un mail de verificación.
	3. El usuario, recibe el mail y verifica su cuenta.
	4. El sistema muestra una confirmación de que se ha verificado correctamente la cuenta.
+ **Escenarios excepcionales:**
	+ El usuario no ingresa algún dato obligatorio: 
		+ El sistema le informa qué campo debe completar.
	+ El usuario ingresa un dato con un formato incorrecto: 
		+ El sistema le informa qué campo debe corregir.
	+ El usuario ingresa un mail que ya fue registrado: 
		+ Se le informa que ya tiene un usuario en la plataforma con ese mail.
	+   El usuario ingresa un nombre de usuario que ya fue registrado: 
		+ Se le informa que ese nombre de usuario ya está tomado.

## 2 Cambiar Password
+ **Caso de uso:** Cambiar password
+ **Actor principal:** Usuario
+ **Pre-condición:** El usuario debe estar logueado.
+ **Escenario exitoso:**
	1. El usuario emite una solicitud de cambio de contraseña. Para ello ingresa su contraseña actual y la nueva contraseña junto con una confirmación de la misma.
	2. El sistema informa que el cambio de contraseña fue exitoso. Finalmente, envía un mail al usuario notificando dicho cambio.
+ **Escenarios excepcionales:**
	+ El usuario ingresa mal su contraseña actual:
		+ Se le informa del error y se le permite intentar de nuevo.
	+ El usuario ingresa una contraseña nueva que no cumple las restricciones:
		+ Se le informa del error y se le permite intentar de nuevo.
	+ La confirmación de la nueva contraseña no es igual a la contraseña nueva:
		+ Se informa al usuario del error y se le permite intentar de nuevo.

## 3 Ejecutar Simulación
+ **Caso de uso:** Ejecutar simulación
+ **Actor principal:** Usuario
+ **Pre-condición:** El usuario debe estar logueado y su cuenta debe haber sido verificada.
+ **Escenarios exitosos:**
	1. El usuario solicita iniciar una simulación.
	2. El sistema le pide al usuario que ingrese los datos de una simulación.
	3.  El usuario ingresa los datos pedidos.
	4. El sistema reproduce la batalla de robots que se muestra en tiempo real hasta completar la cantidad de rondas pautadas. Una vez completada, el sistema muestra los resultados de la simulación.
+ **Escenarios excepcionales:**
	+ No es válida la cantidad de rondas o se seleccionaron más robots que los permitidos: 
		+ Se le informa al usuario del error y se le permite volver a intentar.

## 4 Crear una Partida
+ **Caso de uso:** Crear una partida.
+ **Actor principal:** Usuario
+ **Pre-condición:** El usuario debe estar logueado y su cuenta debe haber sido verificada.
+ **Escenario exitoso:**
	1. El usuario solicita crear una partida.
	2. El sistema le pide al usuario ingresar los datos de la partida y elegir su robot.
	3. El usuario ingresa los datos solicitados y especifica cuál de sus robots quiere usar.
	5. El sistema agrega la partida a la lista de partidas disponibles. Y muestra una confirmación de que se creó con éxito.
+ **Escenarios excepcionales:**
	+ No se completan o especifican todos los datos de la partida:
		+ El sistema informa al usuario los campos faltantes y le permite volver a intentar.
	+ Alguno de los datos no es válido:
		+ Se le informa al usuario del error y se le permite volver a intentar.

## 5 Ejecutar Partida
+ **Caso de uso:** Ejecutar partida
+ **Actor principal:** Usuario
+ **Pre-condición:** El usuario debe estar logueado. El usuario creó una partida que actualmente se encuentra llena.
+ **Escenarios exitosos:** 
	1. El usuario solicita ejecutar la partida.
	2. El sistema computa los resultados de los juegos, y muestra las estadísticas de la partida.

## 6 Subir un robot
+ **Caso de uso:** Subir un robot.
+ **Actor principal:** Usuario.
+ **Pre-condición:** El usuario debe estar logueado y su cuenta debe haber sido verificada.
+ **Escenarios exitosos:**
	+ El usuario solicita subir un robot.
	+ El sistema le pide al usuario completar la información asociada a un robot.
	+ El usuario ingresa los datos solicitados.
	+ El sistema informa al usuario que se subió el robot correctamente.
+ **Escenarios excepcionales:**
	+ El robot subido tiene algún campo no válido:
		+ Se le informa al usuario del error y se le permite corregirlo.
	+ El usuario no completó todos los datos obligatorios:
		+ El sistema informa del campo faltante y le pide al usuario que lo ingrese.

# Diagrama de clases 
![diagrama_clases](Clases_PyRobots.png)


# DFD
Cuando no se especifiquen todos los datos y solo se exprese "datos de..." o "estadísticas de..."  se pueden consultar los detalles en la sección de datos y restricciones.
![DFD](DFD_PyRobots.png)


%%
Alcance
#fixme : hay que agregar en el alcance qué es una simulación, partida, juego, ronda, etc? si
#fixme sacar datos irrelevantes en el alcance


DFD
#fixme: la simulación devuelve una película
#fixme  en el dfd que pasa cuando para realizar una acción el usuario debe proveer solo la solicitud? eso se modela? no se pone el pedido.
#fixme  para sacar datos de una base de datos hay que pasarle los datos necesarios para generar ese pedido?  si no es obvia si
#fixme  validacion para todos los datos que deben ser unicos: no

Caso de uso 
#fixme sacar "el sistema hace.." solo dejar "el sistema informa.."

Todo
#fixme  el usuario que crea una partida se une con su robot en ese momento, o se tiene que unir aparte? al crear
#fixme  estadísticas de robot para actualizar, es realmente necesario? si
#fixme rever tema de estadisticas. No guardar estadísticas pero que sea calculable.
#fixme rever tema de simulacion: el ususrio debe ver **cada** ronda 
#fixme hacer rankings de todo el sistema
#fixme arreglar la consistencia respecto a las estadísticas.

%%
