# Interactive mode of Python

If you want to start playing with Python, open the command line and activate the virtual environment.
Check that at the beginning of the command line, you see `(venv)`.

If that's the case, there's nothing left but to run Python.
To do that, use the command `python`.

``` console
$ python
Python 3.6.6 (...)
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

The command will display several pieces of information.
From the first line, you can make sure that you are using Python 3.
(If you see a number like `2.7.11`, something is wrong - ask your coach for advice.)

With three 'greater-than' signs `>>>`, Python will then ask for instructions.
It's like a command line, but instead of commands like `cd` and `mkdir`, you will write Python commands here.

As the first instruction, we will use Python as a calculator.
In three beaks, write for example `2 + 3` and press <kbd>Enter</kbd>.

``` pycon
>>> 2 + 3
5
```

Did you see the correct answer?
If yes, congratulations! You've done your first Python command.

Will you also try subtraction?
And what about multiplication?
On a calculator, you would enter `4 × 5`, which is hard to write on the keyboard.
Therefore, Python uses the `*` symbol.

``` pycon
>>> 4 * 5
20
```

Symbols such as `+` and `*` are called *operators* in professional terminology.

The operator for division is `/`.

When dividing, an incomplete number can be created, for example two and a half. Python uses a decimal *point*, so it will show `2.5`.

``` pycon
>>> 5 / 2
2.5
```

For reasons we won't go into now, when dividing, a decimal point appears even if the number is a whole number:
``` pycon
>>> 4 / 2
2.0
```

Sometimes it is useful to use division with remainder.
The result will remain as a whole number. For this, Python has operators `//` (quotient) and `%` (remainder):

``` pycon
>>> 5 // 2
2
>>> 5 % 2
1
```

## Errors

Sometimes it happens that you input something incorrectly - something that Python won't understand.
For example, if you accidentally use a non-existent operator `%%`, you will receive an *error message* as a response.

```pycon
>>> 5 %% 2
  File "<stdin>", line 1
    5 %% 2
       ^
SyntaxError: invalid syntax
```

It happens quite often - to beginners as well as professional programmers.
You don't have to be afraid of error messages.
Even if something is wrong, you just need to enter the corrected command on the next line.

In the error message, Python tells you that something was not understood or something else is wrong.
It tries to indicate as clearly as possible *what* and *where* the problem is (but it's just a silly machine, so sometimes it doesn't get it right).
In the error message, notice the arrow symbol `^` at the top, which shows where Python noticed the error.

Orientation in error messages is one of the basic skills of programmers.
Next time you receive an error, try to think about what Python is trying to tell you.

## Summary

What have you learned so far?

*   **Interactive mode of Python** allows you to enter commands (code)
    for Python and displays the results/answers.
*   **Numbers** are used for mathematics and working with text.
*   **Operators** such as `+` and `*` combine values and createw a result.
