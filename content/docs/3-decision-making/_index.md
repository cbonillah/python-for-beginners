---
weight: 3
title: "Decision making"
draft: true
---

# Decision making

Until now, we've written programs that tell Python what to do step by step. Let's take a look at this number division program, you can save it at `<Programming>/3-decisions/division.py`:

A two number division program:
```python
print("I can help you divide two numbers (dividend ÷ divisor)")
dividend = input("Please write the dividend number:\n")
divisor = input("Please write the divisor number:\n")
result = int(dividend) / int(divisor)
print("The result of your division is:\n", result)
print("All done!")
```
If we try to run this program using `0` as a divisor, our program will break.

We can fix this by letting Python make decisions about how to run the code given what is going on in the program execution.

## What `if`

We can tell our programs to execute certain sections of code using `conditional statements`. Let's take a look on how to fix our division problem.

An approach to solving division by 0 issues:
```python
print("I can help you divide two numbers (dividend ÷ divisor)")
dividend = input("Please write the dividend number:\n")
divisor = input("Please write the divisor number:\n")
if int(divisor) == 0:
    print("You can't divide by 0")
else:
    result = int(dividend) / int(divisor)
    print("The result of your division is:", result)
print("All done!")
```
{{< hint info >}}
**Tip**  

Note that when we ask the program if the divisor is `0` we do it using a `==` (`equal to`) operator instead of a `=` operator.
{{< /hint >}}

Python (and other programming languages) use the `if` and `else` statements to determine which sections of code will run. If it's not clear at first glance, telling the user that they can't divide by zero will only run if the `divisor` is actually zero. Or else, the program will execute as intended.

This happens because the section of code that will run only if the divisor is not zero in the `else` statement is `idented` (or slightly offset by spaces) using four spaces. This helps Python identify which section of the code (or `scope`) will be executed within a `conditional statement`.

After everything is done, the program will then print `"All done!"`, because this line of code is not idented, so it belongs to the program's main section of code (or `scope`).

## On how to compare

You've probably guessed it by now, but Python can help you use other kind of `comparison operators`. Here is a list:

* The `greater than` operator `>` e.g. `8 > 3` is `True`.
* The `less than` operator `<` e.g. `1 > 3` is `True`.
* The `equal to` operator `==` e.g. `2 == 2` is `True`.
* The `not equal to` operator `!=` e.g. `0 != 2` is `True`.
* The `greater than or equal to` operator `==` e.g. `0 >= 0` is `True`.
* The `less than or equal to` operator `==` e.g. `-1 <= 2` is `True`.

{{< hint warning >}}
**Important**  

These operators can compare other `types` too. `"b" > "a"` is a valid operation, for example.  
Fire up your `REPL` and try out using compare operators for different types.
{{< /hint >}}
