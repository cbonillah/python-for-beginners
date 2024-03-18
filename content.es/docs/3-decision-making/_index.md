---
weight: 3
title: "Tomando decisiones"
draft: true
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

* **Si** el dividor es cero, indica al usuario que no puede realizar la división.
* **Si no**, realiza la división y presenta el resultado.

Python utiliza cuatro espacios en blanco como `identación` o sangría (alinear líneas de código ligeramente a la derecha) para identificar qué codigo pertenece a las sentencias `if` o `else`. Esto le ayuda a a Python a identificar el `alcance` de las sentencias `if` y `else`.

Una vez todo ha finalizado, el programa imprimirá en pantalla `"Finalizado"`. Esto ocurre porque esta línea de código no esta *identada*, por lo que no pertenece al `alcance` de la sentencia `else`.

## Cómo comparar

Probablemente lo has adivinado, pero Python te permite utilizar otros `operadores de comparación`. Acá hay una lista:

- El operador `mayor que`, `>` ej. `8 > 3` es `True` (verdadero).
- El operador `menor que`, `<` ej. `1 > 3` es `True` (verdadero).
- El operador `igual a`, `==` ej. `2 == 2` es `True` (verdadero).
- El operador `no igual a` o `diferente a`, `!=` ej. `0 != 2` es `True` (verdadero).
- El operador `mayor o igual que`, `==` ej. `0 >= 0` es `True` (verdadero).
- El operador `menor o igual que`, `==` ej. `-1 <= 2` es `True` (verdadero).

{{< hint warning >}}
**Important**

Estos operadores pueden comparar otros `tipos`, aparte de enteros. `"b" > "a"`, por ejemplo, es una operación válida.  
Utiliza el `REPL` para jugar un poco y entender qué operadores puedes utilizar para diferentes tipos.
{{< /hint >}}


## Piedra, papel o tijera

Vamos a hacer un 