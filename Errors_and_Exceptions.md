![DIT Logo!](/img/Logo.png "DIT")
# **Python Exam: Errors and Exceptions**

# 1. Introduction

All errors that occur during the execution of a Python program are represented by an **exception**.

## a. What is an exception?

An exception is an object that contains information about the context of the error. When an exception occurs and is not handled, it produces an interrupt in the program and displays a message and the stacktrace on the standard output. The call stack shows the list of functions and methods that were being called at the time of the exception.

In this article, you will see what an exception is and how it differs from a syntax error. After that, you will learn about raising exceptions and making assertions.

## b. Exceptions versus Syntax Errors

Exceptions are errors that occur during the execution of a program. They are usually caused by incorrect input or code that does not conform to the syntax of the language. Examples of exceptions include: ZeroDivisionError, ValueError, TypeError, NameError, etc.
>print( 0 / 0 )

![The execption!](/img/2023-03-0312.53.47.png "Expetioncs")

Syntax errors occur when the code does not conform to the syntax of the language. These errors can be caused by typos, incorrect indentation, missing parentheses, etc. Examples of syntax errors include: SyntaxError, IndentationError, TabError, etc.

>print( 0 / 0 ))

![The Errors!](/img/2023-03-0313.06.27.png "Errors")

# 2. Raising an Exception

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

# 3. Handling Exceptions

## a. The try Statement

The try statement is used to try to execute a block of code. If an exception occurs, the try clause is executed, and the except clauses are not executed.

If an exception occurs, the code that follows the except statement will be executed, allowing the program to respond to the exception.

![Handling execption!](/img/try_except.png "TryExeption")

This example demonstrates how a program can be written to handle certain exceptions; it will ask the user for input until a valid integer is entered, but will allow the user to interrupt the program (using Control-C or whatever the operating system supports). If the user chooses to interrupt the program, it will be signalled by raising a KeyboardInterrupt exception.

>number = input("write a number : ")
>
> try:
>
>       number = int(number)
>
> except ValueError:
>
>       print("Sorry the entered value is not a number.")

A try statement can include multiple except clauses, each of which specifies a handler for different exceptions. However, only one handler will be executed if an exception occurs. Furthermore, the handlers will only handle exceptions that occur in the same try clause, not in other handlers of the same try statement. Additionally, an except clause can name multiple exceptions as a parenthesized tuple, e.g. (Exception1, Exception2).

>except (RuntimeError, TypeError, NameError):
>
>       pass

## b. The else Clause

The else clause is executed if no exception occurs in the try clause. If an exception occurs in the try clause, the else clause is not executed.

![Handling execption!](/img/try_except_else.webp "TryExeptionelse")

## c. The finally Clause

The finally clause is executed if no exception occurs in the try clause. If an exception occurs in the try clause, the finally clause is not executed.

![Handling execption!](/img/try_except_else_finally.png "TryExeption")

> try:
>
>       linux_interaction()
>
> except AssertionError as error:
>
>       print(error)
>
> else:
>
>       try:
>
>           with open('file.log') as file:
>
>            read_data = file.read()
>
>       except FileNotFoundError as fnf_error:
>
>              print(fnf_error)
>
>finally:
>
>       print('Cleaning up, irrespective of any exceptions.')

# What we learned

After seeing the difference between syntax errors and exceptions, you learned about various ways to raise, catch, and handle exceptions in Python. In this article, you saw the following options:

* raise allows you to throw an exception at any time.
* assert enables you to verify if a certain condition is met and throw an exception if it isn’t.
* In the try clause, all statements are executed until an exception is encountered.
* except is used to catch and handle the exception(s) that are encountered in the try clause.
* else lets you code sections that should run only when no exceptions are encountered in the try clause.
* finally enables you to execute sections of code that should always run, with or without any previously encountered exceptions.

# Bibliography

* https://realpython.com/python-exceptions/
* https://www.tutorialspoint.com/python/python_exceptions.htm
* https://gayerie.dev/docs/python/python3/exception.html
* https://www.programiz.com/python-programming/exception-handling
* https://docs.python.org/3/tutorial/errors.html