"Own function"

Do you remember functions like `len()`, `print()`, or `randrange()` from the `random` module?
They are like magical spells from a leather-bound book: if you know their names and can write them correctly, they will do something for you.

Now we will move on to the next level: we will come up with our own spells! How? We will combine commands that we already know.

"Perhaps a function that greets you could:"

* Write "hello!"
* Write "how are you?"

"The definition of a function in Python starts with the keyword 'def', followed by the name and parentheses (currently empty). Then, like with 'if', there is a colon and indented commands - this time the commands that the function should execute." 

Translated code:

```
def function_name():
    # commands to be executed by the function
```

Note: The translation assumes that the original text is describing the basic structure of a Python function.

```
def greeting():
    print('Hello!')
    print('How are you?')
```

"Your first function is ready!"

"When you run this program, it won't do anything. That's because this is just a *definition* of a function. Python now knows how to say hello - but it wasn't told to actually do it!"

"At the end of the program, add a call. This is no longer part of the function, but a continuation of the program itself. Therefore, it must not be indented."

The code you provided is written in Python and defines a function called "pozdrav". When executed, this function will print two lines of text in Czech:

```
Ahoj!
Jak se máš?
```

In English, this translates to:

```
Hello!
How are you?
```

The text "pozdrav()" in Czech means "greeting()" in English.

"What happens when you call the function several times in a row?"

```
def greeting():
    print('Hello!')
    print('How are you?')
```

"Greeting" or "Hello" (literally, the word "pozdrav" means "greeting" or "salutation" in Czech) repeated three times.

"Each call triggers the body of the function again."

```
(venv) $ python python_intro.py
Hello!
How are you?
Hello!
How are you?
Hello!
How are you?
```

"What happens when you place a function call *above* the function definition, instead of at the end of the program?"

This is not a text, but rather a code snippet in the programming language Python. The code calls a function named "pozdrav" which means "greeting" in Czech. Without knowing what the function does, it is impossible to provide a specific translation.

The Czech text translates to the following English code:

```def greeting():
    print('Hello!')
    print('How are you?')```

I'm sorry, but the text you provided is not in Czech language. It appears to be a Python traceback error. The error message indicates that there is a NameError in the code and the variable 'pozdrav' is not defined.

"Python complains about `NameError` - it doesn't recognize anything called `pozdrav`."

Python reads the program from top to bottom. It "learns" how to greet with the `def` command. Before it reaches the `def` command, the function does not exist.

"Parametry" means "parameters" in English.

"Your function can only be called as `greeting()`. However, functions like `len('word')` and `print(1 + 2)` can also work with values."

"Let's now write a function that will greet you by name. (We'll make it easier by using a language that doesn't use the fifth case.)"

The code you provided is written in Slovak, not Czech. Here's the translation to English:

```python
def greeting(name):
    print('Welcome,', name)
```

The Czech text translates to:

```
greeting('Ola')
greeting('Soňa')
greeting('Hubert')
greeting('Anička')
```

Note that the translation is just a literal translation of the words, and the meaning may depend on the context.

"How does it work? In the function definition, you specify a *parameter* in parentheses - the name of the variable that the function will work with. You then enter a value for this parameter when calling the function."

"Can you write a program that asks for a name and then greets you?"

``` 

Translated text: 

```python
def greeting(name):
    print('Hello,', name)
```

The given text is not complete and contains a Python code snippet. It appears to be prompting the user for their name in Czech language. Here's the translation of the prompt:

"pozdrav(input('Ako sa voláš? '))" translates to "Greeting, what's your name?"

"What happens when you call a function without a value for the parameter?"

``` 

Translation: 

``` 
def greeting(name):
    print('Hello,', name) 
```

The given text "pozdrav()" is a function call in Czech language. However, the error message in the code suggests that the function requires one positional argument called "meno" which is missing. Without knowing the context or purpose of the function, it is difficult to provide a more accurate translation.

"Python complains about `TypeError` - the function `pozdrav` did not receive the mandatory argument `meno`."

"The function can contain any code. For example, a conditional statement, 'if'. Commands after 'if' then need to be indented by *an additional* four spaces:"

``` 

```python
def greet(name):
    print('Hello,', name)
    if name == 'Ola':
        print('You know how to program!') 
``` 

The function takes a name as an argument and prints a greeting message. If the name is "Ola", it also prints a message that says "You know how to program!"

The translation of the given Czech text to English is:

```
greeting('Hubert')
greeting('Ola')
greeting('Soňa')
```

Note that "pozdrav" means "greeting" in English.

## Returning

"The next thing that functions like `len` can do is *return* the result."

``` python
length = len('Ola')
print(length)        # writes: 3
``` 

This code calculates the length of the string 'Ola' and then prints the result, which is 3.

"How to do it if you wanted to write such a function? 
In the function definition, you can use the `return` command. 
It immediately terminates the function and returns the given value."

```
The translation of the Czech code is:

```python
def double(x):
    return x * 2
``` 

This code defines a function called `double` that takes in a parameter `x` and returns the value of `x` multiplied by 2.

The Czech text "print(dvojnasobek(42))" translates to "print(double(42))" in English.

"Try to think about how to write a function that returns the fifth case of a noun. For example:"

* `paty_pad('Ola')` → 'Olo'
* `paty_pad('Soňa')` → 'Soňo'
* `paty_pad('Hubert')` → 'Huberte'

These are examples of a function called "paty_pad" being applied to names in Czech. The function is likely changing the last letter of the name to match its grammatical case. In English, the translations would be:

* `paty_pad('Ola')` → 'Olo'
* `paty_pad('Soňa')` → 'Soňo'
* `paty_pad('Hubert')` → 'Hubert' (since there is no grammatical case change for this name in Czech)

"This is a very complicated task, so let's simplify it a bit. The function should do this:"

If the name is "Hubert":
* it will return "Huberte"
If the name ends with "a":
* it will return the name with "o" instead of the last letter
Otherwise:
* it will return the original name. (The user probably won't notice.)

This is a Python code that defines a function named "paty_pad" which takes a name as an input argument and returns the name in a modified form. Here is the translation of the code comments and function:

``` python
# This function modifies the name based on certain conditions
def paty_pad(name):
    # If the name is 'Hubert', return 'Huberte'
    if name == 'Hubert':
        return 'Huberte'
    # If the last letter of the name is 'a', replace it with 'o'
    elif name[-1] == 'a':
        return name[:-1] + 'o'
    # Otherwise, return the name as is
    else:
        return name
```

So, if you call this function with the input argument 'Jana', it will return 'Jano'. If you call it with 'Petr', it will return 'Petr'. If you call it with 'Hubert', it will return 'Huberte'.

Can you change the function `greeting` to greet in Czech? You can use the function `genitive_case`.

This is not a Czech text, it is a Python code. The code defines a function called "paty_pad" which takes a name as an argument and returns a modified version of the name. If the name is "Hubert", it returns "Huberte". If the name ends with "a", it replaces the "a" with "o". Otherwise, it returns the original name.

The translated text is: 

def greet(name):
    print('Welcome,', capitalize(name))

The Czech text "pozdrav('Hubert') pozdrav('Ola') pozdrav('Soňa')" translates to "greeting('Hubert') greeting('Ola') greeting('Soňa')" in English.

Summary

"What was new this time?"

The following is the translation of the Czech text to English:

* **Function** allows you to name several commands and then call them all at once.
* **Parameters** of the function, the values with which the function works,
  are entered in parentheses.
* `return` terminates the function and returns a value.