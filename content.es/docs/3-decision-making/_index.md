---
weight: 3
title: "Tomando decisiones"
---

# Tomando decisiones

La última vez, vimos cómo Python ejecuta el código que escribimos, cómo recuerda valores y qué tipo de valores puede recordar.

Veamos el siguiente programa para división de números, puedes guardarlo en `<Programacion>/3-decisiones/division.py`:

Un programa que divide dos números:

```python
print("Te puedo ayudar a dividir dos números (dividendo ÷ divisor)")
dividendo = input("¿Cuál es el dividendo?:\n")
divisor = input("¿Cuál es el divisor?:\n")
resultado = int(dividendo) / int(divisor)
print("El resultado de tu división es:\n", resultado)
print("Finalizado")
```

Si intentamos ejecutar este progrma utilizando `0` como divisor, nuestro programa se romperá. Incluso las computadoras no pueden dividir por cero.

Hasta ahora, hemos escrito programas que le dicen a Python que hacer paso a paso, como una lista de tareas. Esto no nos permite reaccionar y responder de forma diferente en situaciones como una división por cero.

## Qué pasaría **si**

Podemos pedir a Python que ejecute ciertas secciones de código condicionalmente con `sentencias condicionales`. Veamos como arreglar nuestro problema de división.

Un acercamiento para resolver el problema:

```python
print("Te puedo ayudar a dividir dos números (dividendo ÷ divisor)")
dividendo = input("¿Cuál es el dividendo?:\n")
divisor = input("¿Cuál es el divisor?:\n")
if int(divisor) == 0:
    print("No puedes dividir por cero")
else:
    resultado = int(dividendo) / int(divisor)
    print("El resultado de tu división es:\n", resultado)
print("Finalizado")
```

{{< hint info >}}
**Tip**

Cuando pedimos al programa si el divisor es cero, lo hacemos utilizando el operador `==` (`igual a`), en lugar de el operador de asignación `=`.
{{< /hint >}}

Python (y otros lenguajes de programación) utilizan las sentencias `if` (Si) y `else`(Si no) para determinar qué secciones de código se ejecutan de acuerdo a una condición. Podríamos interpretar el código arriba de la siguiente forma:

- **Si** el dividor es cero, indica al usuario que no puede realizar la división.
- **Si no**, realiza la división y presenta el resultado.

Python utiliza cuatro espacios en blanco como `identación` o sangría (alinear líneas de código ligeramente a la derecha) para identificar qué codigo pertenece a las sentencias `if` o `else`. Esto le ayuda a a Python a identificar el `alcance` de las sentencias `if` y `else`.

Una vez todo ha finalizado, el programa imprimirá en pantalla `"Finalizado"`. Esto ocurre porque esta línea de código no esta _identada_, por lo que no pertenece al `alcance` de la sentencia `else`.

## Cómo comparar

Probablemente lo has adivinado, pero Python te permite utilizar otros `operadores de comparación`. Acá hay una lista:

- El operador `mayor que`, `>` ej. `8 > 3` es `True` (verdadero).
- El operador `menor que`, `<` ej. `1 > 3` es `True` (verdadero).
- El operador `igual a`, `==` ej. `2 == 2` es `True` (verdadero).
- El operador `no igual a` o `diferente a`, `!=` ej. `0 != 2` es `True` (verdadero).
- El operador `mayor o igual que`, `==` ej. `0 >= 0` es `True` (verdadero).
- El operador `menor o igual que`, `==` ej. `-1 <= 2` es `True` (verdadero).

{{< hint warning >}}
**Importante**

Estos operadores pueden comparar otros `tipos`, aparte de enteros. `"b" > "a"`, por ejemplo, es una operación válida.  
Utiliza el `REPL` para jugar un poco y entender qué operadores puedes utilizar para diferentes tipos.
{{< /hint >}}

## Piedra, papel o tijera

Vamos a escribir un programa para saber si un año en específico es, fue, o será bisiesto. Antes de hacerlo, escribiremos un guión como si estuvieramos describiendo el juego a alguien más (en lenguaje natural).

> 1. Preguntar al usuario por el año en cuestión.
> 2. Dividir el año sobre 4, si la división es exacta (no tiene residuo), sabremos que es un año bisiesto.

Ahora podemos escribir nuestro programa, lo guardaremos en `<Programacion>/3-decisiones/bisiesto.py`.

```python
año = input("Por favor, indica el año para saber si es bisiesto: ")
residuo = int(año) % 4

if residuo == 0:
    print("El año es bisiesto")
else:
    print("El año no es bisiesto")
```

{{< hint info >}}
**Tip**

Recuerda que la entrada de un usuario se considera un texto, y debemos indicarle a Python que es en realidad un número utilizando `int()`.
{{< /hint >}}

¿Fácil, verdad?

Resulta que no es tán fácil, si le preguntamos a nuestro programa, por ejemplo si los años `1900` y `2100` son bisiestos, nos indicará que lo son. Sin embargo, si consultas un calendario en línea, te darás cuenta que ninguno de los dos es un año bisiesto.

Esto es porque hay [más reglas para saber si un año es bisiesto o no](https://es.wikipedia.org/wiki/A%C3%B1o_bisiesto#Algoritmo_computacional). La entrada de Wikipedia indica que un año es bisiesto si:

- Es divisible por `4`
- **No** es divisible por `100`
  - Salvo si es divisible por `400`

Así, el año `1900`, a pesar de ser divisible por `4`, no es bisiesto porque es divisible por `100`. Y el año `2000` es un año bisiesto, porque a pesar de ser divisible por `100`, también es divisible por `400`.

Modifiquemos nuestro programa para ajustarlo con las reglas que acabamos de leer:

```python
año = input("Por favor, indica el año para saber si es bisiesto: ")
divisiblePorCuatro = int(año) % 4 == 0
divisiblePorCien = int(año) % 100 == 0
divisiblePorCuatroscientos = int(año) % 400 == 0

if divisiblePorCuatro and not divisiblePorCien or divisiblePorCuatroscientos:
    print("El año es bisiesto")
else:
    print("El año no es bisiesto")
```

Si probamos este programa, obtendremos resultados correctos `1900`, `2100`, y `2003` no son bisiestos; y `1904`, `2000` y `2008` si lo son. Notarás que la condición dentro del `if` ahora usa nuevas palabras reservadas. Estos operadores, `and`, `not` y `or` se llaman `operadores lógicos`.

### Operadores lógicos

Los operadores lógicos nos ayudan a combinar condiciones y evaluarlas dando como resultado un único valor. Si has leído algo de lógica proposicional, estos conceptos serán familiares.

Python hace uso de tres operadores lógicos:

- El operador `Y` (`and`), resultará en un valor verdadero solo si las dos condiciones que une son verdaderas.  
  ej.

```python
A = 2
B = 5
if A > 0 and B > 0:
    print("Tanto A como B, son positivos")
```

Será verdadero **solo si** tanto `A` como `B` son positivos. Si alguno de los dos llega a ser negativo, la condición no se cumplirá.

- El operador `Ó` (`or`), resultará en un valor verdadero si por lo menos alguna de las dos condiciones que une son verdaderas.  
  ej.

```python
A = 7
B = -3
if A > 0 and B > 0:
    print("Entre A y B, alguno es positivo")
```

Será verdadero si `A` es negativo **ó** B es positivo.

- Finalmente, el operador `no` (`not`), que negará (o invertirá) un valor de verdad.

ej.

```python
A = 8
if not A < 0:
    print("A no es negativo")
```

### Agrupando condiciones

En el programa escrito arriba, la condición que usamos para saber si un año es bisiesto, puede prestarse para confusiones.

```python
if divisiblePorCuatro and not divisiblePorCien or divisiblePorCuatroscientos:
```

¿Qué se evalúa primero? El orden en el que interpretamos los operadores importa y nos puede llevar a resultados inesperados. Al igual que cuando escribimos operaciones matemáticas, podemos hacer uso de paréntesis para agrupar estas operaciones lógicas.

```python
año = input("Por favor, indica el año para saber si es bisiesto: ")
divisiblePorCuatro = int(año) % 4 == 0
divisiblePorCien = int(año) % 100 == 0
divisiblePorCuatroscientos = int(año) % 400 == 0

if divisiblePorCuatro and (not divisiblePorCien or divisiblePorCuatroscientos):
    print("El año es bisiesto")
else:
    print("El año no es bisiesto")
```

De está forma es más claro que el `and`, se aplicará después de resolver el `or` que envuelve el paréntesis, y que el `not` únicamente está negando el valor de verdad de `divisiblePorCien`.

## Más programas

Si quieres seguir practicando por tu cuenta, acá hay un listado de programas que puedes escribir por tu cuenta para practicar:

- Escribe un programa que indique si un numero `A` es multiplo de otro número `B` (Ambos especificados por el usuario).
- Escribe un programa que determine si una letra ingresada por un usuario es una vocal o una consonante.
- Escribe un programa que dado un més ingresado por un usuario, indique el número de dias que tiene.
- Escribe un programa que dados tres números `A`, `B` y `C`, ingresados por un usuario, indique cual mayor entre los tres.
