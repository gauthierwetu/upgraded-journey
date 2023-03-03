# Introduction

All errors that occur during the execution of a Python program are represented by an **exception**.

## What is an exception?

An exception is an object that contains information about the context of the error. When an exception occurs and is not handled, it produces an interrupt in the program and displays a message and the stacktrace on the standard output. The call stack shows the list of functions and methods that were being called at the time of the exception.

In this article, you will see what an exception is and how it differs from a syntax error. After that, you will learn about raising exceptions and making assertions.

## Exceptions versus Syntax Errors

Exceptions are errors that occur during the execution of a program. They are usually caused by incorrect input or code that does not conform to the syntax of the language. Examples of exceptions include: ZeroDivisionError, ValueError, TypeError, NameError, etc.
>print( 0 / 0 )

![The execption!](/img/2023-03-0312.53.47.png "Expetioncs")

Syntax errors occur when the code does not conform to the syntax of the language. These errors can be caused by typos, incorrect indentation, missing parentheses, etc. Examples of syntax errors include: SyntaxError, IndentationError, TabError, etc.

>print( 0 / 0 ))

![The Errors!](/img/2023-03-0313.06.27.png "Errors")

# Raising an Exception

If a condition occurs, we can use raise to throw an exception and supplement it with a custom exception.

![Raise the Errors!](/img/raise.webp "Raise")

If you wish to generate an error when a specific condition is met, you can use the 'raise' command to do so, for example:
> x = 27
>
> if x > 19:
> raise Exception('x should not exceed 19. The value of x was: {}'.format(x))

During the execution, the output will be the following:
> Traceback (most recent call last):
  File "/Users/mac/Documents/DIT OFFLINE/exampython/upgraded-journey/samples.py", line 4, in <module>
    raise Exception('x should not exceed 19. The value of x was: {}'.format(x))
Exception: x should not exceed 19. The value of x was: 27

The program stops running and presents our exception on the screen, giving hints about what caused the issue.





une présentation du concept
– théorie
– exemple pratique
– potentielles alternatives
– des cas d’utilisation concrets en rapport avec l’analyse de données
– une conclusion et enfin la liste des ressources consultées