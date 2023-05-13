"#<var>N</var>-tice" in English means "#<var>N</var>-tuplet".

"Do you already know that you can return a value from a function using the `return` statement?"

The translated text is: 

``` python
def double(x):
    return x * 2
``` 

This is a Python function that takes in a parameter `x` and returns its double.

But how to write a function that returns two values? For example, I want to write a function that calculates the quotient and remainder after division.

"Two values can be returned as a list."

```
The code defines a function called "podil_a_zbytek" which takes two arguments, "a" and "b". The function calculates the integer division of "a" by "b" and assigns the result to the variable "podil". It also calculates the remainder of the division and assigns the result to the variable "zbytek".

"return [share, remainder]"

The Czech text "print(podil_a_zbytek(5, 2))" translates to "print(quotient_and_remainder(5, 2))" in English.

"But it's better to return a *pair* of numbers - two numbers separated by a comma."

```
The code defines a function in Python called "podil_a_zbytek" that takes two parameters "a" and "b". Inside the function, it calculates the integer division of "a" and "b" using the "//" operator and assigns the result to a variable called "podil". It also calculates the remainder of the division using the "%" operator and assigns the result to a variable called "zbytek".

"return" means "remainder" and "zbytek" means "remainder", so the translation of the Czech text to English is: "return remainder, remainder".

The Czech text "print(podil_a_zbytek(5, 2))" translates to "print(quotient_and_remainder(5, 2))" in English.

This is called a pair - and similarly, a trio, quartet, quintet, sextet, simply an <var>n</var>-tuple (English *tuple*) of values is formed.
It works similarly to a list, but it cannot be changed - for example, additional elements cannot be added to it using `append`.
When I have a trio, it always remains as a trio.

"When you have an <var>n</var>-tuple, you can *unpack* it by assigning it to several variables."

quotient, remainder = divide(5, 2)

This is not a Czech text, it is a code snippet in the Python programming language. 

The first line "print(podil)" means "print quotient" in English.

The second line "print(zbytek)" means "print remainder" in English.

"N-tuples have many uses, for example:"

* A point in space has 3 coordinates - a triple of numbers!
* A playing card has a color and a value - a pair of numbers and strings, for example `(2, 'spades')`.

Sometimes it is necessary to add an <var>n</var>-tuple to a list, for example, to save information about a whole pack of playing cards. In similar cases, it is necessary to enclose each <var>n</var>-tuple in parentheses to make it clear where it begins and ends. Here is a list of pairs:

The translation of the Czech text is: 

```python
hand = [(2, 'spades'), (10, 'clubs'), (8, 'diamonds')]
``` 

This appears to be a list of cards in a hand, with each card represented as a tuple containing the card value and its suit. The cards in this hand are the 2 of spades, the 10 of clubs, and the 8 of diamonds.

"When you have such a list, you can go through it in a `for` loop using unpacking."

```
for value, color in hand:
    print('I am playing', value, 'and they are', color)
```

Note: I assumed that `ruka` was meant to be `hand` in English.

"Zip" is the same word in both Czech and English and refers to a type of fastener that is used to join two pieces of fabric or other materials together.

The function `zip` returns an <var>N</var>-tuple or a sequence of <var>n</var>-tuples, which allows you to iterate through multiple lists simultaneously, where the elements correspond to each other.

Items = ['grass', 'sun', 'carrot', 'river']
Colors = ['green', 'yellow', 'orange', 'blue']
Places = ['on the ground', 'up high', 'on the plate', 'behind the wall']

The English translation of the given Czech text is:

"for item, color, place in zip(items, colors, places):
    print(color, item, 'is', place)"

"In this cycle, you will first receive a trio of the first elements from all three lists, then a trio of all second elements, then third, and so on."

"Shrnutí" in Czech means "summary" in English.

"What did you learn this time?"

* Using a *<var>n</var>-tuple*, several values can be combined into one.
* *<var>N</var>-tuples* can be unpacked into several variables.
* The `zip` function returns a sequence of *<var>n</var>-tuples*, in which the elements come from several lists.