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

## Limitaciones y límites:
### Usuario
+ **email:** debe ser único
+ **nombre de usuario:** debe ser único
+ **contraseña:** Debe tener al menos 8 caracteres, al menos una mayúscula, al menos una minúscula y exactamente un guión.
+ **avatar:** imagen `.png` o `.jpg`

### Simulación
+ **Cantidad de rondas:** Un valor entero entre 1 y 10 000.
+ **Cantidad de bots:** Se permiten simulaciones con 2, 3 o 4 bots.

### Partida
+ **Cantidad de rondas:** Un valor entero entre 1 y 10 000.
+ **Cantidad de juegos:** Un valor entero entre 1 y 200.
+ **Cantidad de jugadores:** Se permiten partidas de 2, 3 o 4 jugadores.
+ **Nombre:** Debe ser único.

### Bots
+ **Código:**
	+ No debe tener errores de sintaxis.
	+ Debe implementar al menos los métodos `initialize()` y  `response()`.
	+ No debe implementar métodos internos.


# Preguntas
+ ¿Qué tipos de archivo debe soportar el sistema para el avatar? ¿Debe haber limitaciones respecto al tamaño máximo? ¿Y que relación de aspecto debe tener, 1:1?
