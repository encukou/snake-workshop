> [warning]
> This is a machine-generated translation.
> If you're not at the in-person workshop, try the [DjangoGirls tutorial](https://tutorial.djangogirls.org/en/) for an intro to Python!

# Type conversion

Let's try something new: find out the length of a number the same way you found out the length of your name.
Enter `len(304023)` and press <kbd>Enter</kbd>:

```pycon
>>> len(304023)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: object of type 'int' has no len()
```

You have encountered an error!
 It says that objects of type 'int' (short for 'integer', a whole number) do not have a length.
 What can you do now? Maybe you can try writing the number as a string? Strings have length, right?

```pycon
>>> len("304023")
6
```

But it can also be done without quotation marks.
There is also a function that *converts* a number to a string.
It's called `str`.


```pycon
>>> str(304023)
"304023"
>>> len(str(304023))
6
```

When entering a number directly, it will probably be more pleasant to use quotation marks.
However, the `str` function will become more useful when you want to leave the calculation of the number to Python.

```pycon
>>> str(304023 * 12345 * 83845)
'314684030130075'
>>> len(str(304023 * 12345 * 83845))
15
```

Similarly to `str` converting to strings, the `int` function converts things to integers.

```pycon
>>> int("304023")
304023
```

The number can always be converted to text, but the opposite is not always possible.
What happens when you try to convert a string without digits - for example, `'hello'`?

{% filter solution() %}
An error will occur!

``` pycon
>>> int('hello')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: 'hello'
```

The sentence contains useful information.
The most important thing is the `ValueError`, which indicates an error in the value.
{% endfilter %}
