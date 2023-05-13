#Strings

Numbers are very useful for computers (as the word *computer* suggests), but Python can also work with other types of information. For example, with text.

Try it: enter your name in quotation marks, as you can see below:
```pycon 
>>> 'Ola'
'Ola'
```

You have now created your first *string*! A string is a programming term for *text* - a sequence of characters (letters) that can be processed by a computer.

When entering a string, you must always enclose it in quotation marks (apostrophes). Otherwise, Python would not recognize what is text to work with and what are instructions to execute. This is quite important for a computer - similar things can be understood by humans from context, but a computer is a dumb device.

{{ figure( img=static('quote-comic.svg'), alt='(Ilustrační komiks. Člověk říká robotovi: "Řekni Pavlovi, ať mi zavolá!". Robot odpoví: "PAVLOVI AŤ MI ZAVOLÁ!")', ) }}

Strings can be concatenated - "added" - using the `+` operator. Try this:
```pycon
>>> 'Já jsem ' + 'Ola'
'Já jsem Ola'
```
Watch out for the space! When you enter 'I am' + 'Ola', the two words will be joined together.
The computer considers the space as a *character*; it behaves towards it like towards any letter.
If you don't put the space in quotation marks, it won't be part of the string.

Spaces between the string and the operator (`+`) do not matter. All of the following commands do the same thing:
```pycon
>>> 'I am ' + 'Ola'
'I am Ola'
>>> 'I am '+'Ola'
'I am Ola'
>>> 'I am '                +     'Ola'
'I am Ola'
```
But it is customary to write one space around the operator on each side - just like in these materials. The code is then more readable.

Try putting the space itself in quotation marks - add up three strings:
```pycon
>>> 'I am' + ' ' + 'Ola'
'I am Ola'
```

In addition to "concatenation", you can also repeat strings - multiply by a number.
```pycon
>>> 'Ola' * 3
'OlaOlaOla'
```

## Quoting

And what if you want to put an apostrophe inside your string? You can use double quotes around the string.

```pycon
>>> "I'd say they're properly crazy!"
"I'd say they're properly crazy!"
```

Python doesn't care which type of quotation marks you use to enter a string. The important thing is the letters inside. When Python prints a string, it can choose a different type of quotation marks than the ones you used.
```pycon
>>> "Ola"
'Ola'
```

## Functions and methods

You already know how to 'add' strings ('Hello ' + 'Ola!') and 'multiply' them ('la' * 3). For all other things that can be done with text, there are not enough symbols on the keyboard. Therefore, some operations are named verbally - for example, so-called *functions*.

If you want to know the number of letters in your name, call the function 'len'.
Write 'len' (without quotes), then parentheses, and inside those parentheses, your name as a string (in quotes).
This way you will *call* the function 'len' on the string with your name.

``` pycon
>>> len('Ola')
3
```

There is a function called `type` which determines whether something is a number or a string. How would you call it on the number `123` or the string `'abc'`?

{% filter solution %}
```pycon
>>> type(123)
<class 'int'>
>>> type('abc')
<class 'str'>
```
{% endfilter %}

In addition to functions, there are *methods*, which are written a little differently.

If you want to see your name in capital letters, call the `upper` method. Write a string, then a dot, the method name `upper` (without quotes), and empty parentheses.

``` pycon
>>> 'Ola'.upper()
'OLA'
``` 
Strings also have a method called `lower`. Try calling it on your name.
{% filter solution %}
```pycon
>>> 'Ola'.lower()
'ola'
```
{% endfilter %}

What is a method (which you call with a dot, like `'Ola'.upper()`) and what is a function (where you insert information in parentheses like `len('Ola')`), you will have to remember or look up for each new function/method.

## Expression evaluation

You can use calling a function or method as another value.

Let Python calculate the mathematical expression `(1 + 3) / 2`.\
```pycon
>>> 8 / (1 + 3)
2.0
```

Python first adds `1 + 3` and the result is 4. It replaces the sum with 4 in the original equation and gets `8 / 4`. Then it divides and gets `2.0`.


Try to think about how Python will process these expressions:
```pycon
>>> len('Ola') + 1
4
```

```pycon
>>> 'I am ' + 'Ola'.upper()
'I am OLA'
````

```pycon
>>> len('Ola' * 3)
9
```

```pycon
>>> len('Ola'.upper())
3
```
{% filter solution() %} 
`len('Ola') + 1` → `3 + 1` → `4`

`'I am ' + 'Ola'.upper()` → `'I am ' + 'OLA'` → `'I am OLA'`

`len('Ola' * 3)` → `len('OlaOlaOla')` → `9`

`len('Ola'.upper())` →` len('OLA')` → `3` {% endfilter %}

Similar composition is very common in programming. Most of the basic building blocks can be learned by beginners in a few weeks or months - and then throughout their programming career they discover new ways to assemble them into more and more complex structures.

## Summary

OK, enough of the strings. What have you learned so far?"

Strings are used for working with text.
Operators `+` and `*` are used for concatenating and repeating strings.
Functions and methods like `len()` and `upper()` perform some actions on strings.
Expressions can be composed together.

Numbers, strings, operators, and functions are the basics of most programming languages.

Ready for something else? We bet you are!
