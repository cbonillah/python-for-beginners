# Coding for every day life

## Goal

Learn to code to improve processes for (already working?) adult students.

### Philosophy

Every piece of code the student will write, can help them grasp algorithmia processes and write code that will help them do better at their work through process enhancing and automation.

# From zero to hero

These small tutorials are aimed to teach adults on how to think, and write code to help in daily endeavors.

Hopefully every simple program we write, will help you grasp algorithms and write code that can help you enhance or even automate tasks in your daily life.

In this tutorial, we wil set-up a code environment, install a code editor, Python (a programming language) and write a simple hello world program.

## Visual Studio Code

Download and install the [Visual Studio Code](https://code.visualstudio.com/) editor. This will be the main tool we use to write, and run our programs.

Install the Python extension if it's not installed, click on the extensions side bar menu (Or use the keyboard shortcut `Ctrl+Shift+X`), check if the Python (By Microsoft) extension is installed or install it by searching it in the Marketplace and adding it to the code editor.

## Chocolatey

Install [Chocolatey](https://chocolatey.org), a "package manager" for windows environment.

Chocolatey will help you install programming software through an easy to use command line interface. It will also help you (with some assistance) to update or remove programming software with ease.

Press the `Windows` key and search for the `Powershell`, right click on the `Windows Powershell` entry and select `Run as administrator`.

Head over to [the Chocolatey install page](https://chocolatey.org/install) and follow the instructions by running the instructed command on your `Powershell` terminal.

Repeat the instructions above to open yet another `Powershell` terminal with administrative rights. And run:

```powershell
choco install python
```

When everything is done run:

```powershell
python --version
```
To make sure python is installed.

## Hello world!

Create a folder for our programming journey, a recommended folder would be in your Documents folder under the `Programming` folder (the `<Programming>` folder from now on).

Open the folder within VisualStudio Code using the `Open folder` shortcut, or by selecting the option through the `File>Open folder` menu.

Create a new folder for this section either on your file explorer or through VisualStudio Code named `1-hello-world`.

Then, create a new file `hello-world.py`, using the new file button or by pressing `Ctrl+N`.

We will write now our first program that greets everyone through the console interface.

```python
print("Hello world")
```

Hit the play button and watch as your program comes to life and greets everyone.

# Lights, camera, action!

Get familiar with the script concept in programming. Understand how code is "interpreted" and why it is interpreted by Python.

We will introduce simple math operators and the concept of variables and (primitive) types.

## Enter the REPL

We can ask Python to perform actions for us, like adding, substracting, multiplying or dividing  numbers.

Head to the terminal and prompt a `py` command (Which is available because we installed python last time).

Now we can use Python as a calculator, we can ask them to multiply two really big numbers for example.

Try out addition, substraction, division or multiplication using the math operators (`+`, `-`, `*`, `/`).

## Create a new program

Create a new folder within your programming projects folder like so: `<Programming>/2-scripting`.

Open the program within `VS Code` and create a new file `multiplying-numbers.py`.

Python reads our code files as an actor would a move script and does it best to follow it very precisely. Each line prompts python to perform an action.

`print` will tell Python to print something to the console, and `input` will prompt Python to ask an user for input, and then "remember" it, storing it inside a `variable`.

We will write a simple program that will greet the user by their name.

Sample program:

```python
username = input("What's your name?")
print("Hello,", username)
``` 

> `username = input("What's your name?")` will promp Python to ask the user for their name, and then remember that name and store it in a `variable` called `username` using the `=` operator.

`print` can print multiple things if we use `,` as a separator, in this case, we are printing the text `"Hello,"` followed by the user's name we told Python to remember.

## What can Python remmember? (Variable types)

We can tell Python to remember something using the `Assignment operator` `=`. It's called that because we are `assigning` a value to a variable.

In `name = "Jhon"`, we're telling Python to remember `"Jhon"` when we ask for `name`. In other words, we are `assigning` the value `"Jhon"` to the variable `name`.

Python can remember all sorts of stuff. We will see some basic things (`types`), Python can remember.

As we've seen, we can assign `text` to variables. In programming this is called `strings`, Python calls this `str`.

e.g.

```python
name = "John"
print("Hi,", John)
```

We can also assign `numbers` to variables. Python can tell the difference between three `types` of numbers:
* `int` for integer numbers
* `float` for floating point numbers
* `complex` for complex numbers (we won't use this very much)

e.g.
```python
radius = 2
pi = 3.14159
area = radius * pi
print("The area of your circle is", area)
```
> In this case, `radius` would be an `int`, `pi` a `float`.
> Because `area` is the result of a computation that involves a `float`, it is as well, a `float`.

We can also assign `truth values` to variables. To discern if something is `True` or  `False`, we use truth values, or `Booleans`, Python calls these `bool`.

e.g.
```python
codingIsCool = True
print("Is coding cool?", codingIsCool)
```

## Multiply two big numbers, please

We will now write a simple program that asks the user for two (integer) numbers and multiplies them together.

```python
print("I can help you multiply two numbers")
firstNumber = input("Whats the first number?\n")
secondNumber = input("Whats the second number?\n")
result = firstNumber * secondNumber
print("Your multiplication is done, the result is:\n", result)
```

**If** we run the code above, our program will fail. The reason is Python assumes everything you type through the `input` is a text(`str`). We have to tell Python the input is not a text, but a number.

```python
print("I can help you multiply two numbers")
firstNumber = input("Whats the first number?\n")
secondNumber = input("Whats the second number?\n")
result = int(firstNumber) * int(secondNumber)
print("Your multiplication is done, the result is:\n", result)
```

> When we ask python to multiply the inputs, we use `int(firstNumber)`, this asks Python to assume the `variable` within the parenthesis is an integer number(`int`) and not a text.  
> As long as the values **are numbers** Python will multiply them for you.

## Homework

Write a program that asks the user for two sides of a rectangle, and prints out the area for said rectangle.

# Decision making

Until now, we've written programs that tell Python what to do step by step. Let's take a look at this number division program, you can save it at `<Programming>/decisions/division.py`:

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
    print("You can't divide by 0, silly")
else:
    result = int(dividend) / int(divisor)
    print("The result of your division is:", result)
print("All done!")
```
> Note that when we ask the program if the divisor is `0` we do it using a `==` operator instead of a `=` operator.

Python (and other programming languages) use the `if` and `else` statements to determine which sections of code will run. If it's not clear at first glance, telling the user that they can't divide by zero will only run if the `divisor` is actually zero. Or else, the program will execute as intended.

This happens because the section of code that will run only if the divisor is not zero in the `else` statement is `idented` (or slightly offset by spaces) using four spaces. This helps Python identify which section of the code (or `scope`) will be executed within a `conditional statement`.

After everything is done, the program will then print `"All done!"`, because this line of code is not idented, so it belongs to the program's main section of code (or `scope`).

## Everything compares


