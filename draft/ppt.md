Ahora podemos escribir nuestro programa, lo guardaremos en `<Programacion>/3-decisiones/ppt.py`.

```python
import random

seleccionJugador = input("¿Piedra, papel, o tijera?\n")
seleccionPrograma = random.choice(["piedra", "papel", "tijera"])

print("El programa eligió:", seleccionPrograma)

if seleccionJugador == seleccionPrograma:
    print("¡Empate!")

if seleccionJugador == "piedra" and seleccionPrograma == "tijera":
    print("¡Ganaste!")

if seleccionJugador == "tijera" and seleccionPrograma == "papel":
    print("¡Ganaste!")

if seleccionJugador == "papel" and seleccionPrograma == "piedra":
    print("¡Ganaste!")

if seleccionPrograma == "piedra" and seleccionJugador == "tijera":
    print("Perdiste, ¡qué mal!")

if seleccionPrograma == "tijera" and seleccionJugador == "papel":
    print("Perdiste, ¡qué mal!")

if seleccionPrograma == "papel" and seleccionJugador == "piedra":
    print("Perdiste, ¡qué mal!")
```

Después de haber jugado un poco con el programa, vamos a analizarlo.

Para recordar la selección del jugador, estamos utilizando el comando `input`.

Para que el programa elija, utilizamos una función utilitaria `random.choice` (una función utilitaria que viene de una "libreria" `random`). No vamos a entrar en el detalle, pero diremos que traemos un juego de herramientas que alguien más construyo, haciendo uso de la palabra reservada `import`.

Si volvemos al listado de comparaciones, verás que hacemos las comparaciones una por una, tal y como se describe en nuestro guión. Es importante entender que estamos verificando que la selección del jugador y la del programa sean iguales (con el operador igual a `==`), y eso significa que el jugador debería escribir su selección en minúsculas. Para Python "Piedra" y "piedra", son dos textos distintos.

Por último, verás que para hacer comparar que se cumplan dos condiciones, como por ejemplo en *"2. Si el jugador seleccionó `piedra` **Y** el programa `tijera`, se declara ganador al jugador"*, utilizamos el `operador lógico` `and`.