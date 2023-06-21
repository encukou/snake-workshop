> [warning]
> This is a machine-generated translation.
> If you're not at the in-person workshop, try the [DjangoGirls tutorial](https://tutorial.djangogirls.org/en/) for an intro to Python!

# Own function

Do you remember functions like `len()`, `print()`, or `randrange()` from the `random` module?
They are like magical spells from a leather-bound book: if you know their names and can write them correctly, they will do something for you.

Now we will move on to the next level: we will come up with our own spells! How? We will combine commands that we already know.

Perhaps a function that greets you could:

* Write "hello!"
* Write "how are you?"

The definition of a function in Python starts with the keyword 'def', followed by the name and parentheses (currently empty). Then, like with 'if', there is a colon and indented commands - this time the commands that the function should execute.

```
def function_name():
    # commands to be executed by the function
```

Write in your program:
```
def greeting():
    print('Hello!')
    print('How are you?')
```

Your first function is ready!

When you run this program, it won't do anything. That's because this is just a *definition* of a function. Python now knows how to say hello - but it wasn't told to actually do it!

At the end of the program, add a call. This is no longer part of the function, but a continuation of the program itself. Therefore, it must not be indented.

```
def greeting():
    print('Hello!')
    print('How are you?')

greeting()
```

What happens when you call the function several times in a row?

```
def greeting():
    print('Hello!')
    print('How are you?')

greeting()
greeting()
greeting()
```

{% filter solution %}  Each call triggers the body of the function again.

```
(venv) $ python python_intro.py
Hello!
How are you?
Hello!
How are you?
Hello!
How are you?
```
{% endfilter %}

What happens when you place a function call *above* the function definition, instead of at the end of the program?


```
greeting()

def greeting():
    print('Hello!')
    print('How are you?')
```

{% filter solution %}
``` pycon
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'pozdrav' is not defined
```

Python complains about `NameError` - it doesn't recognize anything called `pozdrav`.

Python reads the program from top to bottom. It "learns" how to greet with the `def` command. Before it reaches the `def` command, the function does not exist.
{% endfilter %}

## Parameters

Your function can only be called as `greeting()`. However, functions like `len('word')` and `print(1 + 2)` can also work with values.

Let's now write a function that will greet you by name. 


```python
def greeting(name):
    print('Welcome,', name)

greeting('Ola')
greeting('Soňa')
greeting('Hubert')
greeting('Anička')
```

How does it work? In the function definition, you specify a *parameter* in parentheses - the name of the variable that the function will work with. You then enter a value for this parameter when calling the function.

Can you write a program that asks for a name and then greets you?


{% filter solution %}
```python
def greeting(name):
    print('Hello,', name)

greeting(input('What's your name?'))
```
{% endfilter %}

What happens when you call a function without a value for the parameter?

{% filter solution %}
``` python
def greeting(name):
    print('Welcome,', name)

greeting()
```
``` pycon
Traceback (most recent call last):
  File "<stdin>", line 9, in <module>
TypeError: greeting() missing 1 required positional argument: 'name'
```
Python complains about `TypeError` - the function `pozdrav` did not receive the mandatory argument `name`.
{% endfilter %}

The function can contain any code. For example, a conditional statement, 'if'. Commands after 'if' then need to be indented by *an additional* four spaces:


```python
def greet(name):
    print('Hello,', name)
    if name == 'Ola':
        print('You know how to program!') 

greeting('Hubert')
greeting('Ola')
greeting('Soňa')
```


## Returning

The next thing that functions like `len` can do is *return* the result.

``` python
length = len('Ola')
print(length)        # writes: 3
``` 

How to do it if you wanted to write such a function? 
In the function definition, you can use the `return` command. 
It immediately terminates the function and returns the given value.


```python
def double(x):
    return x * 2

print(double(42))
```

Try to think about how to write a function that returns the fifth case of a noun. For example:

* `paty_pad('Ola')` → 'Olo'
* `paty_pad('Soňa')` → 'Soňo'
* `paty_pad('Hubert')` → 'Huberte'

These are examples of a function called "paty_pad" being applied to names in Czech. The function is changing the last letter of the name to match its grammatical case. 

This is a very complicated task, so let's simplify it a bit. The function should do this:

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

Can you change the function `greeting` to greet in Czech? You can use the function `paty_pad`.


{% filter solution %}
``` python
def paty_pad(name):
    if name == 'Hubert':
        return 'Huberte'
    elif name[-1] == 'a':
        return name[:-1] + 'o'
    else:
        return name
        
def greeting(name):
    print('Welcome,', paty_pad(name))

greeting('Hubert')
greeting('Ola')
greeting('Soňa')
```
{% endfilter %}


## Summary

What was new this time?

* **Function** allows you to name several commands and then call them all at once.
* **Parameters** of the function, the values with which the function works,
  are entered in parentheses.
* `return` terminates the function and returns a value.
* 
