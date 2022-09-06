# Take Home
Análisis, especificación de requerimientos y diseño.
+ Hay que aprobar.
+ Es personal.
+ No tiene nota.
+ Tiene defensa.
+ 2 semanas.
+ Todo se responde y corrige durante estas semanas.
+ Fecha límite 27/09 antes de las 23:59 [Mail de Laura B²](laura.brandan@unc.edu.ar)
+ nombre del archivo: `PyChar_Martinez_L.pdf` 
+ Profesionalmente apto.

Se deberá entregar:
+ Alcance del sistema: 2 párrafos 
+ DFD: va a haber una clase sobre esto
+ Diagrama de clases
+ Casos de uso
	1. Registrarse
		1. Mail 
		2. nombre de usuario, único.
		3. contraseña 8 caracteres mayúsculas, minúscula y guiones
		4. (avatar)
		+ Este no se puede usar hasta que no se verifica el mail.
	2. Cambiar password
	3. Iniciar simulación
		1. Un jugador, varios robots
		2.  máximo de bots 4
	4. Crear una partida
		1. Si un robot está mal programado, se muere en la partida.
		2. No se cancela automáticamente.
		3. Limite total de rondas max 10000
		4. Cantidad de jugadores: mínimo (2) y máximo (4)
		5. ver las partidas disponibles, se puede elegir una en particular.
		6. (por ahora, no se puede invitar).
		7. El usuario que crea la partida la puede iniciar
		8. cantidad de simulaciones no tiene máximo
	5. Iniciar partida
	6. Subir un bot
		1. Acá se tiene que verificar que sea legal

**Py-Robots**  
Juego para programadores.

biiblioteca de bots
se pueden subir tosos los bots que quieran (no hay máximo de bots)
los bots tienen nombre jugadores

(historial de partidas)
un usuario puede ver estadísticas acumuladas por robot

1 archivo por bot

**Simulación**  
+ 1 juego
+ n rondas parametrizable max 10000 
+ tablero: tiempo real (se puede poner pausa, ¿speed up?)
+ single player.
+ max 4 bots
+ se puede repetir bots
+ No genera estadísticas
+ da resultado

**Partida**  
+	Multiplayer
+	n juegos (n configurable, entre 1 y 200) cada uno de 10000 rondas
+	No se ve el tablero: se ven resultados acumulados.
+	Resultado acumulado el porcentaje de partidas ganadas.
+	Genera estadísticas
+ Luego de los n juegos hay un boton para ir al lobby


Orden
Scan → Ataque → Movimiento

Es aleatorio donde empieza el robot
El robot mide 1x1.