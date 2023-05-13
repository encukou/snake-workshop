"Řetězce" means "Strings" in English.

"Numbers are very useful for computers (as the word *computer* suggests), but Python can also work with other types of information. For example, with text."

"Try it: enter your name in quotation marks, as you can see below:"

The given text is not in Czech language, it is a Python code snippet which prints the string 'Ola' in the output.

You have now created your first *string*! A string (in Czech *řetězec*) is a programming term for *text* - a sequence of characters (letters) that can be processed by a computer.

"When entering a string, you must always enclose it in quotation marks (apostrophes). Otherwise, Python would not recognize what is text to work with and what are instructions to execute. This is quite important for a computer - similar things can be understood by humans from context, but a computer is a dumb device."

The Czech text in the comic says: "Tell Paul to give me a call!" and the robot responds: "TELL PAVEL TO GIVE ME A CALL!"

"Strings can be concatenated - "added" - using the `+` operator. Try this:"

"I am Ola."

"Watch out for the space! When you enter 'I am' + 'Ola', the two words will be joined together.
The computer considers the space as a *character*; it behaves towards it like towards any letter.
If you don't put the space in quotation marks, it won't be part of the string."

"Spaces between the string and the operator (`+`) do not matter. All of the following commands do the same thing:"

"I am Ola"

But it is customary to write one space around the operator on each side - just like in these materials. The code is then more readable.

"Try putting the space itself in quotation marks - add up three strings:"

"I am Ola"

In addition to "concatenation", you can also repeat strings - multiply by a number.

The output of the Python code is: "OlaOlaOla".

"Uvozování" in English means "quoting" or "citation".

"And what if you want to put an apostrophe inside your string? You can use double quotes around the string."

"I'd say they're properly crazy!"

"Python doesn't care which type of quotation marks you use to enter a string. The important thing is the letters inside. When Python prints a string, it can choose a different type of quotation marks than the ones you used."

The given text is not in Czech language. It appears to be a Python code snippet that simply assigns the string "Ola" to a variable and then prints it.

## Functions and methods

"You already know how to 'add' strings ('Hello ' + 'Olo!') and 'multiply' them ('la' * 3). For all other things that can be done with text, there are not enough symbols on the keyboard. Therefore, some operations are named verbally - for example, so-called *functions*."

"If you want to know the number of letters in your name, call the function 'len'.
Write 'len' (without quotes), then parentheses, and inside those parentheses, your name as a string (in quotes).
This way you will *call* the function 'len' on the string with your name."

The English translation of the Czech text is: ``` pycon
>>> len('Ola')
3
```

"There is a function called `type` which determines whether something is a number or a string. How would you call it{{a}} on the number `123` or the string `'abc'`?"

The text is not in Czech, it is in Python code. 

The code outputs the data type of the values passed to the `type()` function. 

The first line outputs `<class 'int'>`, indicating that the data type of the value `123` is an integer. 

The second line outputs `<class 'str'>`, indicating that the data type of the value `'abc'` is a string.

"In addition to functions, there are *methods*, which are written a little differently."

"If you want to see your name in capital letters, call the `upper` method. Write a string, then a dot, the method name `upper` (without quotes), and empty parentheses."

The English translation of the Czech text is: ``` pycon
>>> 'Ola'.upper()
'OLA'
``` 

Note: This is actually a block of Python code, which converts the string "Ola" to all uppercase letters using the `upper()` method.

"Strings also have a method called `lower`. Try calling it on your name."

"Ola"

"What is a method (which you call with a dot, like `'Ola'.upper()`) and what is a function (where you insert information in parentheses like `len('Ola')`), you will have to remember or look up for each new function/method."

## Expression evaluation

"You can use calling a function or method as another value."

Let Python calculate the mathematical expression `(1 + 3) / 2`.

The text is already in English and it shows a Python code that calculates the result of 8 divided by the sum of 1 and 3, which is 2.0.

"Python first adds `1 + 3` and the result is 4. It replaces the sum with 4 in the original equation and gets `8 / 4`. Then it divides and gets `2.0`."

The translation of the Czech text is: 

"Eight divided by the sum of one and three equals eight divided by four, which equals two."

"Try to think about how Python will process these expressions:"

The code `len('Ola') + 1` in Czech translates to `len('Ola') + 1` in English. It is not necessary to translate it as it is already in English.

"I am OLA"

The English translation of the given Czech text is: ```pycon
>>> len('Ola' * 3)
9
```

The English translation of the Czech text is: 

```pycon
>>> len('Ola'.upper())
3
```

This is already in English and it is a Python code that converts the string "Ola" to uppercase and then returns the length of the resulting string, which is 3.

I'm sorry, but the text you provided appears to be Python code, not Czech text. Could you please provide the Czech text you would like me to translate?

"I am OLA"

The translation of the given text is not necessary as it is already in English and contains Python code. The code `len('Ola' * 3)` is calculating the length of the string 'OlaOlaOla', which is 9.

`len('Ola'.upper())` → `len('OLA')` → `3`

"Similar composition is very common in programming. Most of the basic building blocks can be learned by beginners in a few weeks or months - and then throughout their programming career they discover new ways to assemble them into more and more complex structures."

Summary

"OK, enough of the chains. What have you learned so far?"

Chains are used for working with text.
Operators `+` and `*` are used for concatenating and repeating strings.
Functions and methods like `len()` and `upper()` perform some actions on strings.
Expressions can be composed together.

"Numbers, strings, operators, and functions are the basics of most programming languages."

"Ready for something else? We bet you are!"