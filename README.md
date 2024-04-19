# TP1 de Programación de Video Juegos 2: Sharp Invaders

## Metodología

Integrantes por equipo: 1

Se aprueba con:         6

### Objetivos

- Refrescar lo que aprendieron sobre programación el año pasado
- Que aprendan a modelar problemas básicos usando clases en C#
- Que aprendan a pensar y resolver algoritmos básicos en C#
- Que aprendan a aclararse las dudas de los requerimientos ambiguos

### Comentarios Adicionales

Estos ejercicios son un poco "teóricos" pero el proceso de producción de un juego "real" pasa por los mismos problemas. Ya en el TP2 van a poder mostrar mejor gameplay y gráficos, pero la base lógica va a ser parecida a la que pensaron acá.

Quiero darles la mayor libertad posible para que los resuelvan como quieran. Incluso pueden no usar lo que vimos en clase si saben otra forma. Lo único que les pido es que:

- Estén hechos en C#
- Me justifiquen en el oral por qué les pareció mejor opción que lo que vimos en clase

Tengan en cuenta que en varios de estos ejercicios espero que apliquen los conceptos que vimos en clase como encapsulamiento y polimorfismo. Puede que igual se los de por correctos a los ejercicios donde podrían haberlo usado y no lo hicieron, pero me van a tener que justificar porque no usaron esa solución y se fueron por otro lado.

Todos los ejercicios van a ser ejecutables en consola nada más. No vamos a agregar ningún grafico. Como lo que hicimos en clase.

Pueden asumir cosas que no están aclaradas explícitamente. Si igualmente tienen dudas, pregunten.

Hay algunas cosas que les pido en los ejercicios y que aun no vimos, como pedir input al jugador o el manejo del tiempo. Lo vamos a ver la próxima clase. 

Recuerden que, por lo general, la solución más simple es la mejor.

----

## Entrega

### Código

Todo lo van a resolver en un repositorio de GitHub. Pueden forkear este mismo o crear uno nuevo.

La fecha límite es el Jueves 2 de Mayo de 2024 a las 23:59 hs. Antes de ese horario me tienen que mandar el link del repo por mail a <me@diegofreijo.com>.

Tiene que haber una `tag` que se llame `tp1`. Ese commit es el que voy a corregir.

Si crearon branches por feature o por ejercicio, no los borren. Así puedo ver cómo estuvieron trabajando. Pero para este TP no es necesario que se vuelvan locos con GitFlow. Igual les recomiendo que lo practiquen si pueden porque para los demás TPs va a ser necesario.

### Defensa

Les voy a estar mandando horarios para que cada uno se conecte y tengamos la devolución por Google Meet o Teams. Así no usamos la hora de clase para eso y aburrimos a los que se quedan esperando afuera.

----

## Sharp Invaders

Vamos a programar una versión bien simple de Space Invaders!

Si no lo conoces o no te acordas como se jugaba: https://freeinvaders.org/

Vamos a programar un prototipo del juego que tenga muy pocas funcionalidades. Y en ASCII, nada de gráficos bonitos por ahora.

El juego va a ser una aplicación de consola en C#. Se va a ver de esta manera:

```
############
#   = = =  #
#  = = =   #
#          #
#   |      #
#   ^      #
############
```

Por si mis habilidades de artista ASCII no son muy buenas, paso a explicar cada elemento:

- `#` una pared. Todo el escenario esta encerrado en esas paredes.
- `^` la nave del jugador
- `|` los misiles que dispara la nave del jugador. Se van a mover hacia arriba.
- `=` una nave enemiga. No se va a mover ni va a atacar.

Si no te gusta la elección de caracteres que hice para cada elemento del juego, sentite libre de elegir los que gusten!

## Ejercicios

### 1. Mapa (2 puntos)

Primero queremos ver en pantalla una escena como la que puse arriba. 

Pero no va a alcanzar con mostrar un `string` estático. El mapa va a ser de tamaño dinámico. Es decir, se puede definir el ancho y alto al arrancar la aplicación y el mapa va a dibujarse siempre con ese tamaño hasta que la aplicación se cierre. El ancho y alto puede ser una constante definida en algún lado.

### 2. Enemigos  (3 punto)

Ahora queremos dibujar los enemigos. La cantidad de enemigos a mostrar también va a ser ajustable por una constante definida en algún lado.

Como veras, no están todos en una misma linea. Hay 3 enemigos por fila. Y cada fila esta desfazada una posición, no están los enemigos uno detrás del otro. Por ejemplo, si se configura que hay 8 enemigos, debería mostrarse algo así:

```
############
#   = = =  #
#  = = =   #
#   = =    #
#   |      #
#   ^      #
############
```

### 3. Jugador  (2 puntos)

Ahora vamos a dibujar al jugador. Vamos a querer que pueda moverse para la izquierda y la derecha con las flechas del teclado. Ojo que no podemos permitir que traspase las paredes!

### 4. Misiles  (3 puntos)

Por ultimo, vamos a ponerle acción al juego! 

El jugador va a poder disparar apretando la barra espaciadora. Al hacerlo se va a crear un misil adelante de la nave del jugador. El misil se mueve hacia arriba a la velocidad de un casillero por segundo. Cuando choca contra una pared o un enemigo, se destruye. Si el choque fue contra un enemigo, también va a destruirlo.
