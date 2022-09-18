
# Alcance
%%
alcance 20 lineas
**que** es el sistema
que provee a los usuarios puede haber detalles
características
implicitamente LOS CASOS DE USO
de gral a particular
identificar el usuario, qué provee el sistema
nada de implementacion, no **como**}

El sistema trae dos bots implementados propios del sistema para las simulaciones. Se puede ver el código
%%

%%[](dibujitos.png)%%

PyRobots es un juego para programadores. Donde los jugadores pueden subir el programar sus propios robots, crear y unirse a partidas donde pueden chatear con otros jugadores, ver sus estadísticas y ejecutar simulaciones para ver a sus robots en el campo de batalla.
El programa controla un robot cuya misión es buscar, seguir y destruir otros robots, cada uno ejecutando diferentes programas. 
Cada jugador puede subir tantos bots como desee, y para cada uno deben proveer una implementación 

Cada robot dispone de funciones para scanear enemigos, iniciar y detener el motor, disparar cañones, etc. 


## Limitaciones y límites:
### Usuario
+ **Mail:** debe ser único
+ **Nombre de usuario:** debe ser único
+ **Contraseña:** Debe tener al menos 8 caracteres, al menos una mayúscula, al menos una minúscula y exactamente un guión.
+ **Avatar:** no hay restricciones

### Simulación
+ **Cantidad de rondas:** Un valor entero entre 1 y 10 000.
+ **Cantidad de bots:** Se permiten simulaciones con 2, 3 o 4 bots.

### Partida
+ **Cantidad de rondas:** Un valor entero entre 1 y 10 000.
+ **Cantidad de juegos:** Un valor entero entre 1 y 200.
+ **Cantidad de jugadores:** Se permiten partidas de 2, 3 o 4 jugadores.
+ **Nombre:** Debe ser único.

### Bots
+ **Nombre:** Debe ser único y es obligatorio
+ **Avatar:** una imagen \[opcional\]
+ **Código:**
	+ No debe tener errores de sintaxis.
	+ Debe implementar al menos los métodos `initialize()` y  `response()`.
	+ No debe implementar métodos internos.
	+ Se harán verificaciones de seguridad extra #fixme

