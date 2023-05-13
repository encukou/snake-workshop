"Porovnávání věcí" means "comparing things" in English.

"Programmers often compare different values. Let's take a look at how to do it."

```python
>>> 5 > 2
True
>>> 5 > 8
False
>>> 5 < 8
True
```
The text is already in English and appears to be Python code. It is a series of Boolean expressions that evaluate to either `True` or `False`. The first expression `5 > 2` is `True` because 5 is greater than 2. The second expression `5 > 8` is `False` because 5 is not greater than 8. The third expression `5 < 8` is `True` because 5 is less than 8.

"When you ask Python if one number is greater than the other, it will answer either `True` or `False`."

"It works even with more complex expressions."

The English translation of the Czech text is:

``` pycon
>>> 5 > 3 * 2
False
```

This is a Python code snippet that compares whether 5 is greater than 3 multiplied by 2. The result of this comparison is `False`, which means that 5 is not greater than 3 multiplied by 2.

"Greater than" and "less than" are symbols known from mathematics. However, if you want to ask if two numbers are equal, you need to use a slightly different notation:

The Czech text is actually a code snippet written in Python programming language. It checks if 1 is equal to 1 and returns True. Here is the English translation of the code snippet:

```python
>>> 1 == 1
True
``` 

The code checks if the statement "1 is equal to 1" is true and returns the boolean value True.

"We use one equals sign `=` for *assignment* of a value to a variable. When you want to check if things are *equal* to each other, always, **always** use two equals signs `==`."

"The other comparison options are inequality (≠), greater than or equal to (≤), and less than or equal to (≥). Most people do not have these symbols on their keyboard, so Python uses `!=`, `<=`, and `>=`."

``` python
>>> 5 != 2
True
>>> 3 <= 2
False
>>> 6 >= 12 / 2
True
```

This is a code snippet written in Python. It is testing three different Boolean expressions and printing out their results. The first expression checks if 5 is not equal to 2, which is true. The second expression checks if 3 is less than or equal to 2, which is false. The third expression checks if 6 is greater than or equal to 12 divided by 2, which is true.

Have you ever heard the expression "comparing apples and pears"? Let's try the Python equivalent:

The error message is in English and it says: "TypeError: '>' not supported between instances of 'int' and 'str'". This means that you cannot compare an integer and a string using the '>' operator.

"Just like you can't compare apples and pears, Python is unable to compare strings (`str`) and numbers (`int`). Instead, it displays a `TypeError` and tells us that these two types cannot be compared."

"What happens when you replace `>` with `==` in the previous example?"

The Czech text says: "False".

"You can't compare apples and pears, but you can confirm that they are two different things."

## Logic

"Do you want to try something else? Enter this:"

The given text is not in Czech language, it is a code snippet in Python language. It consists of four boolean expressions using logical operators `and`, `or`, and `not`. The output of each expression is also given. Here is the translation of the code to English:

```
>>> 6 > 2 and 2 < 3
True
>>> 3 > 2 and 2 < 1
False
>>> 3 > 2 or 2 < 1
True
>>> not 3 > 2
False
```

The first expression evaluates whether 6 is greater than 2 and 2 is less than 3, which is True.

The second expression evaluates whether 3 is greater than 2 and 2 is less than 1, which is False.

The third expression evaluates whether 3 is greater than 2 or 2 is less than 1, which is True because at least one of the conditions is True.

The fourth expression evaluates whether the condition "3 is greater than 2" is not True, which is False because the condition is True.

"In Python, you can combine several comparisons into one!"

"If you use the 'and' operator, both sides must be true for the whole expression to be true. If you use the 'or' operator, it is enough for only one side of the comparison to be true. The 'not' operator 'inverts' the result of the comparison."

## Presence

"Wouldn't it be nice to find out if your number won the lottery? If you have a list, you can use the `in` operator to ask if a given element is in it."

``` 
loterie = [3, 42, 12, 19, 30, 59]
18 in loterie
False
42 in loterie
True
``` 

This is a code snippet written in Python programming language. 

The code creates a list of integers called "loterie". The next two lines of code check if the integer 18 is in the list "loterie" (which is False) and if the integer 42 is in the list "loterie" (which is True).

"It's not a complete comparison, but you'll get the same kind of result as with `<` or `==`."

## Truth values

You have just learned about a new type of object in Python. We already know types such as string, number, list, or dictionary; we have added to them the *truth value*, or more commonly in English, *boolean*.

The truth values are only two: `True` (true) or `False` (false).

In order for Python to understand that it is this type, it is necessary to pay attention to the capitalization. `true`, `TRUE`, `tRUE` will not work - only `True` is correct.

Like any value, you can also save a *boolean* in a variable.

Sorry, but the given Czech text appears to be a code snippet written in Python language. It assigns a boolean value of True to the variable 'a' and then prints its value. Here is the English translation of the code:

```python
>>> a = True
>>> a
True
``` 

I hope that helps!

"You can also save the result of the comparison in the same way."

The code is not in Czech language, it is in Python programming language. The code assigns the result of the comparison `2 > 5` to the variable `a` and then prints the value of `a`, which is `False`.

"And you can use all of that in logical expressions."

The Czech text says: "``` pycon >>> a and True False```"

This is not a sentence in Czech, but rather an example of code in Python. The code is checking whether the variable "a" is true and whether the boolean value "True" is also true. The result is "False", which means that either "a" is not true or "True" is not true.

I'd be happy to help! Please provide the Czech text that you would like me to translate.

"Shrnutí" means "Summary" in English.

In this section you have learned:

In Python, you can **compare** using operators `>`, `>=`, `==`, `<=`, `<`, `!=`, and `in`.
* Operators `and` and `or` can **combine** two boolean values.
* Operator `not` can **invert** a boolean value.
* **Boolean** is a type that can have one of two values: `True` (true) or `False` (false).