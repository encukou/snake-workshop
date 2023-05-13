# Interactive mode of Python

"If you want to start playing with Python, open the command line and activate the virtual environment. Check that at the beginning of the command line, you see `(venv)`."

"If that's the case, there's nothing left but - finally - to run Python. To do that, use the command `python`."

This is not a Czech text. It is a console output from running Python 3.6.6, which displays the version number and a prompt for input.

"The command will display several pieces of information. From the first line, you can make sure that you are using Python 3. (If you see a number like `2.7.11`, something is wrong - ask your coach for advice.)"

"With three 'greater-than' signs >>>, Python will then ask for instructions. It's like a command line, but instead of commands like 'cd' and 'mkdir', you will write Python commands here."

"As the first instruction, we will use Python as a calculator. In three beaks, write for example `2 + 3` and press <kbd>Enter</kbd>."

I'm sorry, but the provided text is not in Czech language. It appears to be a Python code snippet that performs a simple addition operation and returns the result of 5.

"Did you see the correct answer? If yes, congratulations! You have your first Python command behind you."

"Do you also try subtraction?"

And what about multiplication?
{# XXX: How to write multiplication? `4 x 5` `4 . 5` `4 × 5` `4 * 5` -#}
On a calculator, you would enter `4 × 5`, which is written incorrectly on the keyboard.
Therefore, Python uses the `*` symbol.

I'm sorry, but the text you provided is not in Czech. It is a code snippet in Python programming language that multiplies 4 by 5 and returns the result 20.

Symbols such as `+` and `*` are called *operators* in professional terminology.

"The operator for division is `/`."

"When dividing, an incomplete number can be created, for example two and a half. Python uses a decimal *point*, so it will show `2.5`."

The text is not in Czech language, it is a Python code snippet that performs a division operation and prints the result. The output is 2.5.

"For reasons we won't go into now, when dividing, a decimal point appears even if the number is a whole number:" 

``` pycon
>>> 4 / 2
2.0
```

"Sometimes it is useful to use division with remainder. The result will remain as a whole number. For this, Python has operators `//` (quotient) and `%` (remainder):"

The English translation of the Czech text is:

``` pycon
>>> 5 // 2
2
>>> 5 % 2
1
```

This is a code snippet in Python that performs integer division and modulus operations. The first operation `5 // 2` returns the integer quotient of dividing 5 by 2, which is 2. The second operation `5 % 2` returns the remainder of dividing 5 by 2, which is 1.

"How much is 123 plus 456 divided by 789?"

"Chyby" in Czech means "errors" in English.

Sometimes it happens that you input something incorrectly - something that Python won't understand. For example, if you accidentally use a non-existent operator `%%`, you will receive an *error message* as a response.

The text you provided is not in Czech language. It appears to be a Python code snippet that produces a syntax error when attempting to use the modulo operator. The correct syntax for modulo operation in Python is `%`, so the correct code should be `5 % 2`.

"It happens quite often - to beginners as well as professional programmers. You don't have to be afraid of error messages. Even if something is wrong, you just need to enter the corrected command on the next line."

In the error message, Python tells you that something was not understood or something else is wrong. It tries to indicate as clearly as possible *what* and *where* the problem is (but it's just a silly machine, so sometimes it doesn't get it right). In the error message, notice the arrow symbol `^` at the top, which shows where Python noticed the error.

"Orientation in error messages is one of the basic skills of programmers. Next time you receive an error, try to think about what Python is trying to tell you."

"Summary"

"What have you learned so far?"

Interactive mode of Python allows you to enter commands (code) for Python and displays the results/answers. Numbers are used for mathematics and working with text. An operator such as `+` and `*` combines values and creates a result.