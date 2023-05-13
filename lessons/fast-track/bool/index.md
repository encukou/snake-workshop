# Comparing things

Programmers often compare different values. Let's take a look at how to do it.

```pycon
>>> 5 > 2
True
>>> 5 > 8
False
>>> 5 < 8
True
```

When you ask Python if one number is greater than the other, it will answer either `True` or `False`.

It works even with more complex expressions.


``` pycon
>>> 5 > 3 * 2
False
```

"Greater than" and "less than" are symbols known from mathematics. However, if you want to ask if two numbers are equal, you need to use a slightly different notation:

```python
>>> 1 == 1
True
``` 

We use one equals sign `=` for *assignment* of a value to a variable. When you want to check if things are *equal* to each other, always, **always** use two equals signs `==`.

The other comparison options are inequality (≠), greater than or equal to (≤), and less than or equal to (≥). Most people do not have these symbols on their keyboard, so Python uses `!=`, `<=`, and `>=`.

``` python
>>> 5 != 2
True
>>> 3 <= 2
False
>>> 6 >= 12 / 2
True
```

Have you ever heard the expression "comparing apples and pears"? Let's try the Python equivalent:

``` pycon
>>> 1 > 'krajta'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: '>' not supported between instances of 'int' and 'str'
```

Just like you can't compare apples and pears, Python is unable to compare strings (`str`) and numbers (`int`). Instead, it displays a `TypeError` and tells us that these two types cannot be compared.

What happens when you replace `>` with `==` in the previous example?

{% filter solution %}
```pycon
>>> 1 == 'krajta'
False
```

You can't compare apples and pears, but you can confirm that they are two different things.
{% endfilter %}

## Logic

Do you want to try something else? Enter this:

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

In Python, you can combine several comparisons into one!

If you use the 'and' operator, both sides must be true for the whole expression to be true. If you use the 'or' operator, it is enough for only one side of the comparison to be true. The 'not' operator 'inverts' the result of the comparison.

## Presence

Wouldn't it be nice to find out if your number won the lottery? If you have a list, you can use the `in` operator to ask if a given element is in it.

``` 
>>> loterie = [3, 42, 12, 19, 30, 59]
>>> 18 in loterie
False
>>> 42 in loterie
True
``` 

It's not a complete comparison, but you'll get the same kind of result as with `<` or `==`.

## Truth values

You have just learned about a new type of object in Python. We already know types such as string, number, list, or dictionary; we have added to them the *truth value*, or more commonly in English, *boolean*.

The truth values are only two: `True` (true) or `False` (false).

In order for Python to understand that it is this type, it is necessary to pay attention to the capitalization. `true`, `TRUE`, `tRUE` will not work - only `True` is correct.

Like any value, you can also save a *boolean* in a variable.


```python
>>> a = True
>>> a
True
``` 

You can also save the result of the comparison in the same way:
``` pycon
>>> a = 2 > 5
>>> a
False
```


And you can use all of that in logical expressions:
``` pycon
>>> a and True
False
```

## Summary

In this section you have learned:

In Python, you can **compare** using operators `>`, `>=`, `==`, `<=`, `<`, `!=`, and `in`.
* Operators `and` and `or` can **combine** two boolean values.
* Operator `not` can **invert** a boolean value.
* **Boolean** is a type that can have one of two values: `True` (true) or `False` (false).
