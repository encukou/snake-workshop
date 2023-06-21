> [warning]
> This is a machine-generated translation.
> If you're not at the in-person workshop, try the [DjangoGirls tutorial](https://tutorial.djangogirls.org/en/) for an intro to Python!

# Variables

An important concept in programming are *variables*.
A variable is nothing but a *naming* of something that we will want to use later.
Programmers use variables to store data so that their code is more readable and they don't have to remember specific values.

Let's say you want to name a string with your name as `name`. It would be written like this:

```pycon
>>> name = 'Ola'
```

The variable `name` will now have the value  `'Ola'`.

As you may have noticed, this command did not return anything - Python did not output any result.
How do you then find out if the variable really exists?

Enter the variable name alone (i.e. `name`, without quotation marks) and press <kbd>Enter</kbd>: 

```pycon
>>> jmeno
'Ola'
```

Try to set a different variable - for example, your favorite color.

``` pycon
>>> color = 'blue'
>>> color
'blue'
``` 

You can assign a value to a variable anytime again and thus change what is hidden under the given name:

```pycon
>>> name
'Ola'
>>> name = "Soňa"
>>> name
'Soňa'
```

You can also pass it to a function or use it in an expression.
Python will substitute the current value for the variable name.

```pycon
>>> len(name)
4
>>> name * 4
'SoňaSoňaSoňaSoňa'
```

Great, isn't it?
The variable can contain anything, for example numbers. Try this:

```pycon
>>> width = 4
>>> length = 6
>>> width * length
24
```

But what if you use the wrong name? Can you guess what will happen?

{% filter solution %}
```pycon
>>> city = "Tokyo"
>>> ccity
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'ccity' is not defined
```
{% endfilter %}

Error!

Python has various types of errors.
This one is called `NameError`.
Python will return this error if you try to use a variable that has not been set yet.
It is often a typo.
So when you see `NameError`, check if you made a typo when you were setting or using the variable.

## Variable names
Professional programmers name variables in English so that as many colleagues around the world as possible can understand them. 

In any case, it is good not to use diacritics and avoid capital letters:
use `name` instead of <code><strong>N</strong>ame</code>.

Try it out: Which of these names will Python allow you to use as a variable?

* `button5`
* `5button`
* `button` 
* `favorite color`
* `favorite-color`
* `favoriteColor`

{% filter solution %}
* `button5` yes
* `5button` no: names must start with a letter
* `button` yes
* `favorite color` no: that's not one name, but two!
* `favorite-color` also no: Python interprets it as substracting two variables (`favourite` minut `color`)
* `favoriteColor`yes: but it's better to avoid capital letters
{% endfilter %}

In more complex variable names, an underscore is used. For example, `favorite_color` will be considered as one word, the name of one variable, by Python, but a person sees two words.
```
>>> favourite_color = 'blue'
>>> favourite_color.upper()
'BLUE'
```

## Summary

* **Variables** are names for values.
* By using the assignment operator (`=`), you can set a variable to any value.
* Variables are named using **lowercase letters** without diacritics.
* We can use an **underscore** to separate words within a variable name.
