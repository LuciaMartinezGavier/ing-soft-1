# PyRobots
## Alcance
PyRobots es un juego web. Donde los jugadores pueden programar el comportamiento de sus propios robots, crear, unirse y ejecutar partidas, ver sus estadísticas y ejecutar simulaciones, para las cuales el sistema provee dos bots default,  para ver sus robots en el campo de batalla.
El programa controla un robot cuya misión es buscar, seguir y destruir otros robots, cada uno ejecutando diferentes programas.
Cada robot dispone de funciones para escanear enemigos, iniciar y detener el motor, disparar cañones, etc.
Luego de cada partida el programa mostrará las estadísticas de la misma. Adicionalmente, se pueden ver las estadísticas de cada bot.

### Datos y restricciones
#### Usuario
| Dato | obligatorio | Restricciones |
| - | - | - | - |
| Email | Sí | Ser único. Tener formato de mail |
| Nombre | Sí | Ser único. | 
| Contraseña | Sí | Tener al menos 8 caracteres, al menos una mayúscula, al menos una minúscula y exactamente un guión. |
|  Avatar | No | Ser una imagen. |

#### Simulación
| Dato | Obligatorio  | Restricciones |
| - | - | - | - | 
| Cantidad de rondas | Sí |  completar |

+ Cantidad de rondas
+ Bots

#### Partida
+ Cantidad de juegos
+ Cantidad de rondas por juego
+ Cantidad de jugadores
+ Nombre

#### Bot 
+ Nombre
+ Avatar
+ Código
#### Estadísticas asociadas a una partida o simulación.
Por cada jugador se muestra:  
+ **Ranking**.
+ **Nombre** del bot que usó.
+ Porcentaje de **juegos sobrevividos**.
+ Promedio de **rondas sobrevividas** (si el bot ganó y el juego terminó antes de completar las `N` rondas entonces se cuentan todas las rondas restantes como sobrevividas).

El ranking se determina por:  
+ Cantidad de juegos sobrevividos hasta el final.
+ Cantidad de vida promedio al final del juego. %%Va a desempatar ganadores %%
+ Cantidad de rondas promedio que sobrevivió. %% Va a desempatar perdedores %%
+ Si todavía hay un empate entonces tienen el mismo número de ranking.

#### Estadísticas asociadas a un bot
Un jugador puede ver las estadísticas de su bot. En ellas, se encuentra la siguiente información:
+ Cantidad total de **partidas jugadas**.
+ Porcentaje de **partidas ganadas** (con número de ranking 1, las partidas donde todos los bots obtuvieron el mismo ranking se considera que todos ganaron).
+ Porcentaje de **partidas perdidas** (con menor número de ranking).
+ Valor medio de **ranking**.

#### Estadísticas generales
+  Por cada bot se ve la cantidad de partidas jugadas y el porcentaje de ganadas y perdidas.
%% el objetivo es poder compararlos %%

## Limitaciones y límites:

### Simulación
+ **Cantidad de rondas:** Un valor entero entre 1 y 10 000.
+ **Cantidad de bots:** Se permiten simulaciones con 2, 3 o 4 bots.

### Partida
+ **Nombre:** Debe ser único.
+ **Cantidad de rondas:** Un valor entero entre 1 y 10 000.
+ **Cantidad de juegos:** Un valor entero entre 1 y 200.
+ **Cantidad de jugadores:** Se permiten partidas de 2, 3 o 4 jugadores.

### Bots
+ **Nombre:** Debe ser único y es obligatorio
+ **Avatar:** Debe ser una imagen \[es un campo opcional\]
+ **Código:**
	+ Debe implementar al menos los métodos `initialize()` y  `response()`.
	+ No debe implementar métodos internos.
	+ No debe tener errores de sintaxis.
	+ Debe cumplir con restricciones de seguridad extra.
