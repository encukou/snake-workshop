# Cycles

"Programmers don't like to repeat themselves. Programming is about automation: we won't greet every person separately, let's take a list of fifty people and greet them all at once!"

"No, some programmers are probably not very socially gifted. But automation really comes in handy elsewhere!"

"Do you still remember lists? Make a list of names."

The translated text is: ```python
names = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'Ty']
```

"With the list, you will want to do this:"

"For each name from the list of names:
* greet by the given name."

In Python, such a *loop* - repetition "for each element of the list" - is written using the `for` command.

```
for name in names:
    greet(name)
```

(Note: I assumed that "jmeno" means "name" and "jmena" means "names", and that "pozdrav" means "greet".)

"The entire program will therefore look like this:"

The Czech text translates to the following English code:

```python
def greet(name):
    print('Welcome,', name)
```

The code is written in Czech, but it appears to be a simple Python program that creates a list of names (Rachel, Monica, Phoebe, Ola, Ty) and then uses a function called "pozdrav" to greet each name in the list. The English translation of the code is:

```
names = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'Ty']
for name in names:
    greet(name)
```

"And when we start it:"

```
$ python3 python_intro.py
Welcome, Rachel
Welcome, Monica
Welcome, Phoebe
Welcome, Ola
Welcome, You
```

"As you can see, everything you have indented inside the `for` loop will be repeated for each element of the `jmena` list."

I'm sorry, but the text you provided appears to be a placeholder or a code snippet. It does not contain any meaningful Czech text to translate. Please provide the correct text.

"Opakuj <var>n</var>-krát" in English means "Repeat <var>n</var> times".

"You can use the `for` loop with values other than lists."

"It is often used with the `range()` function. When you want to repeat something 200 times, write:"

"I will never throw a plastic bag into a campfire again!"

"How does it work?
`for i in range(X)` can be translated as "for every number from zero to <var>X</var>".
The function `range` creates that sequence of numbers from zero to <var>X</var>.
Python stores each number in the variable `i` as it iterates through the loop."

The English translation of the given Czech code is:

```python
for i in range(5):
     print(i)
```

```
0
1
2
3
4
```

This code uses a loop to print the numbers from 0 to 4. The `range(5)` function generates a sequence of numbers from 0 to 4, which are then printed one by one using the `print()` function inside the loop.

Notice that the number `5` itself is not included in the result:
`range(5)` counts from 0 to 4.
When you start counting from zero and want to have five numbers, you end up with four.

"Summary"

"You learned:"

* "Cyklus" means a way to repeat a certain procedure multiple times in a row.
* "Range" helps when you need a specific number of repetitions.