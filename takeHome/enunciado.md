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
		2. El bot tiene nombre y avatar

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
+  No es pública
+ No hay caso de uso de crear simulación

**Partida**  
+	Multiplayer
+	n juegos (n configurable, entre 1 y 200) cada uno de 10000 rondas
+	No se ve el tablero: se ven resultados acumulados.
+	Resultado acumulado el porcentaje de partidas ganadas.
+	Genera estadísticas
+ Luego de los n juegos hay un botón para ir al lobby

**Estadísticas**
+ Libertad wii.
+ No poner "etc", "por ejemplo", "tal como", ...
+ El tipo de estadísticas van en el alcance.
+ Tener en cuenta que pueden empatar (datos para desempatar? depende de nosotros).

Orden
Scan → Ataque → Movimiento

Es aleatorio donde empieza el robot
El robot mide 1x1.

***
##### Aclaraciones
1. Crear partida, muchos usuarios, iniciar partida, resultados y etc es **asíncrono**. Se pueden meter en otra partida mientras tanto. Un jugador puede estar en más de una misma partida al mismo tiempo.
2. DFD: el jueves vemos cosas que no deberían ocurrir en un TH. se puede pensar el DFD de casos de uso pero tiene que estar entero TODOS los casos de uso (incluso los que no aparecen entre los 6).
3. Las partidas tienen nombres.
4. Iniciar partida: incluye todo. Seleccionar partida entre todas las que creaste, iniciar, ejecución, resultado.
5. El sistema trae dos bots implementados propios del sistema para las simulaciones. Se puede ver el código

untas generales
1. El diagrama de clases lo tenemos que hacer en español?  si
2. Las restricciones de los datos ingresados deben ir en los casos de uso?  no, en el alcance

# Preguntas Casos de uso
## Registrarse
1. ¿El email debe ser único? si
2. ¿Qué pasa si el usuario no verifica su mail? nada. Es válido para siempre
3. ¿Se debería reservar el nombre de usuario de una persona que se está registrando o si alguien que empezó el mismo proceso se lo puede sacar? ¿Cuánto tiempo lo tendrá reservado? no se resserva
	1. Esto implica: La necesidad de los atributos *está_activa*  y ¿*momento_de_creación*?

## Cambiar password
1. En general se puede cambiar la contraseña solo con el mail o con la contraseña anterior.  no mail. solo cambiar no recuperar
	1. ¿Deberíamos implementar ambas opciones?
	2. ¿Las dos se ponen en el mismo caso de uso o  son dos casos diferentes?
2. Si se manda un mail para el cambio de contraseña, tiene tiempo máximo de cambio o ese mail es válido para siempre.
3. La especificación de cómo debe ser la contraseña la repito en dos lugares, está bien eso?
4. Tengo escenarios excepcionales que no agregan mucha información. Los debería dejar?
5. Se puede cambiar la contraseña a la misma que tenía antes?

## Iniciar simulación
1. Se puede hacer una simulación con un solo bot? no
2. ¿Se puede poner speed up en la simulación? ¿Cámara rápida? ¿Saltar directamente a los resultados?  si (extra) detalle de implementacion
3. ¿Qué pasa si el código falla en algún caso durante la ejecución? Se le debería avisar al usuario de ese error o el bot solo pierde esa ronda en silencio? (como sucedería en una partida) que pierda

## Crear una partida
 1. ¿Las partidas tienen nombre? si, unoico
2. ¿Qué diferencia hay entre hacer n juegos de m  rondas o simplemente hacer m\*n rondas? roda: ejecutar el scrpt

## Iniciar partida
1. ¿El creador de la partida puede iniciarla si no está presenta la cantidad de jugadores? no
2. Qué es el lobby?? Después de una partida pueden volver a hacerla? ¿Los usuarios pueden cambiar de bot? ¿Es parte de "iniciar partida"? no se vuelve ahí
3. chat en el lobby

## Subir robot
1. Se está pidiendo que la clase y el archivo que sube el usuario tengan el mismo nombre o que se guarde de esa manera? no es limitación

# Preguntas diagrama de clases
1. ¿La imagen del avatar está bien que sea un atributo? si
2. ¿Hace falta agregar el atributo ID en la clase usuario?  no

	

alcance 20 lineas
**que** es el sistema
que provee a los usuarios puede haber detalles
características
limitaciones y limites no van en los casos de uso
implicitamente LOS CASOS DE USO

de gral a particular

identificar el usuario, que provee el sistema
nada de implementacion no **como**

partida por tics

## Otros casos de uso
1. Loguearse
2. Unirse a la partida
3. Restablecer contraseña
4. Ver estadísticas de mis bots


## Más preguntas
+ ¿Cómo se llama el actor que todavía no es usuario? ¿Es el mismo que está por iniciar sesión?
+ ¿Pausar simulación está bien que sea un método de simulación?
+ Subir_robot es un método de robot?
+ Cuando uno crea  la partida debe elegir su robot? O lo hace al iniciarla?

## Check list
+ que no haya nada de interfaz de usuario en los casos de uso.
### Clases
+ Ponerle nombre a las relaciones del diagrama de clase
+ No debe haber clases sin relaciones
+ Hay un estado permanente o transitorio que vincula dos clases. No tiene que haber relaciones de "x llama a y"
+ todas las clases deben tener atributos
+ Agregar puntaje del bot (no puede ir en partida ni en juego)
+ No debe haber clases que se relacionan consigo mismas

### DFD
+ Se pueden entregar varios DFD de acuerdo a los diferentes casos de uso. Usuario, Partida, Estadísticas
+ Tipito de palitos es actor externo. (Registrar usuario)
+ En el dfd tiene que estar todos las clases que son permanentes en diagrama de clases clase
+ Los cuadrados son los objetos (cada instancia
+ + Los transformadores NO CREAN DATOS
+ El dfd está mal si:
+ "data de usuario" a secas: hay que especificar en algun lado qué incluye.
+ Hay usuarios que directamente se conectan a la base de datos.
+ Hay nociones de interfaz de usuario
+ Hay noción de tiempo o secuencialidad: no hacer crear→iniciar→ver estadísticas. No tiene que haber secuencias.
+ Hay transformadores que no tienen flechas que salen.


## Preguntas

### Sobre dfd
+ Que se hace con los datos que se deben validar? Se asume que la ida y vuelta está hecha o solo van los datos con el flujo principal?
+ ¿Cómo representamos el mail para validar contraseña y usuario?
+ Qué pasa con los flujos de datos que solo son de lectura. Por ejemplo, ver partidas creadas. Hay que poner un transformador?
+ En el dfd van los datos de control? es decir los pedidos y solicitudes del usuario?
+ Transformadores a los que les entra y les sale el mismo dato???
+ Los datos que van a la base de datos deberían ser como id_user, nuevo_avatar o usuario modificiado


#fixme  estadísticas de robot para actualizar, es realmente necesario?
#fixme  validacion para todos los datos que deben ser unicos