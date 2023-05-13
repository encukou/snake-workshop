"Proměnné" in English means "variables".

"An important concept in programming are *variables*. A variable is nothing but a *naming* of something that we will want to use later. Programmers use variables to store data so that their code is more readable and they don't have to remember specific values."

Let's say you want to name a string with your name as `jmeno`. It would be written like this:

The Czech text ```>>> jmeno = 'Ola'``` translates to English as: ```>>> name = 'Ola'```

The variable `jmeno` will now have the value of `'Ola'`.

As you may have noticed, this command did not return anything - Python did not output any result. How do you then find out if the variable really exists?

"Enter the variable name alone (i.e. `jmeno`, without quotation marks) and press <kbd>Enter</kbd>: "

I'm sorry, but the provided text does not seem to be in Czech language. It appears to be a code snippet in Python programming language, where the variable `jmeno` is assigned the value `'Ola'`.

"Try to set a different variable - for example, your favorite color."

The English translation of the given Czech text would be:

``` python
>>> color = 'blue'
>>> color
'blue'
``` 

Note: The original Czech text simply assigns a string value of 'modrá' to the variable 'barva' and then prints it using the print statement. The translated English text does the same, but uses the English equivalent of the word 'modrá', which is 'blue'.

"Whenever you can assign a variable again and thus change what is hidden under the given name:"

The Czech text translates to:

```
>>> jmeno
'Ola'
>>> jmeno = "Soňa"
>>> jmeno
'Soňa'
```

This is a Python code that assigns the value "Soňa" to the variable "jmeno" and then prints its value.

"You can also pass it as a function or use it in an expression. Python will substitute the current value for the variable name."

The Czech text translates to:

```python
>>> len(jmeno)
4
>>> jmeno * 4
'SoňaSoňaSoňaSoňa'
```

This is already in English and appears to be Python code. The first line calculates the length of a variable named `jmeno`, which is 4. The second line multiplies the value of `jmeno` by 4, resulting in the string 'SoňaSoňaSoňaSoňa'.

"Super, ne?" translates to "Great, isn't it?" in English.

"The variable can contain anything, for example numbers. Try this:"

The code calculates the area of a rectangle with width 4 and length 6, which is 24.

"But what if you use the wrong name? Can you guess what will happen?"

The text is not in Czech language, it is a Python code snippet. Here's the translation of the code:

```
>>> mesto = "Tokyo"
>>> mmesto
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'mmesto' is not defined
```

Translation:

```
>>> city = "Tokyo"
>>> mmesto
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'mmesto' is not defined
``` 

The code creates a variable `mesto` and assigns it the value `"Tokyo"`. The second line tries to access a variable called `mmesto`, which is not defined, causing a `NameError`.

Error!

"Python has various types of errors. This one is called `NameError`. Python will return this error if you try to use a variable that has not been set yet. It is often a typo. So when you see `NameError`, check if you made a typo when you were setting or using the variable."

## Variable names
Professional programmers name variables in English so that as many colleagues around the world can understand them as possible. However, we recommend Czech for beginners - it is clearer which names you can choose for yourself (such as `barva` - color in Czech) and which ones are from Python (such as `upper`). The disadvantage is that you will have to unlearn it over time.

In any case, it is good not to use diacritics and avoid capital letters:
use `jmeno` instead of <code><strong>J</strong>m<strong>é</strong>no</code>.

"Try it out: Which of these names will Python allow you to use as a variable?"

* `tlacitko5` - button5
* `5tlacitko` - 5button
* `tlačítko` - button
* `oblibena barva` - favorite color
* `oblibena-barva` - favorite-color
* `oblibenaBarva` - favoriteColor

I'm sorry, but there is no Czech text provided for me to translate. Please provide the text and I will be happy to assist you.

* `tlacitko5` yes.
* `5tlacitko` no: names must start with a letter.
* `tlačítko` yes, but it's better to avoid diacritics (`č`, `í`).
* `oblibena barva` no: that's not one name, but two!
* `oblibena-barva` also no: Python interprets it as subtracting two variables
  (`oblibena` minus `barva`).
* `oblibenaBarva` yes, but it's better to avoid capital letters.

"In more complex variable names, an underscore is used. For example, `favorite_color` will be considered as one word, the name of one variable, by Python, but a person sees two words."

The code is not a text, but it shows a variable named `oblibena_barva` being assigned the value of 'žlutá' (which means 'yellow' in English). Then, the `upper()` method is called on the variable to convert the string to all uppercase letters, resulting in 'ŽLUTÁ'.

Summary

*Variables* are names for values.
By using the assignment operator (`=`), you can set a variable to any value.
Variables are named using *lowercase letters* without diacritics.
We can use an *underscore* to separate words within a variable name.