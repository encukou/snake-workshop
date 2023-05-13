# Type conversion

"Come try something new: find out the length of a number the same way you found out the length of your name. Enter `len(304023)` and press <kbd>Enter</kbd>:"

The text is an error message from a Python interpreter. Here is the translation:

```
>>> len(304023)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: object of type 'int' has no len()
```

The error message indicates that you cannot use the `len()` function on an integer (`int`) object.

"You have encountered an error! It says that objects of type 'int' (short for 'integer', a whole number) do not have a length. What can you do now? Maybe you can try writing the number as a string? Strings have length, right?"

This is not Czech, it is Python code. It calculates the length of the string "304023", which is 6.

"But it can also be done without quotation marks. There is also a function that *converts* a number to a string. It's called `str`."

The translation of the Czech text is:

```pycon
>>> str(304023)
"304023"
>>> len(str(304023))
6
```

This is a code snippet written in Python. It converts the integer number 304023 to a string using the `str()` function and then calculates the length of the resulting string using the `len()` function. The output of the code is the string "304023" and the integer value 6, which represents the length of the string.

"When entering a number directly, it will probably be more pleasant to use quotation marks. However, the `str` function will become more useful when you want to leave the calculation of the number to Python."

The code calculates the product of three numbers, 304023, 12345, and 83845, which equals 314684030130075. The length of the resulting number is 15 digits.

"Similarly to `str` converting to strings, the `int` function converts things to integers."

The Czech text is the same as the Python code, which converts the string "304023" to an integer. The English translation would be: 

```pycon
>>> int("304023")
304023
```

"The number can always be converted to text, but the opposite is not always possible. What happens when you try to convert a string without digits - for example, `'hello'`?"

An error will occur!

This is not a Czech text, but rather a Python error message. It means that the string 'ahoj' cannot be converted to an integer because it is not a valid number.

The sentence contains useful information, although English and advanced knowledge of computer science are required to understand it fully. 

In a more literal translation, the sentence reads: "Value error: incorrect notation of a whole number in decimal system: 'hello'". 

However, the most important thing is the `ValueError`, which indicates an error in the value.