# Cycles

Programmers don't like to repeat themselves. Programming is about automation: we won't greet every person separately, let's take a list of fifty people and greet them all at once!

No, some programmers are probably not very socially gifted. But automation really comes in handy elsewhere!

Do you still remember lists? Make a list of names.

```python
names = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'Ty']
```

With the list, you will want to do this:

* For each name from the list of names:
+ greet by the given name.

In Python, such a *loop* - repetition "for each element of the list" - is written using the `for` command.

```
for name in names:
    greet(name)
```

The entire program will therefore look like this:


```python
def greet(name):
    print('Welcome,', name)

names = ['Rachel', 'Monica', 'Phoebe', 'Ola', 'Ty']
for name in names:
    greet(name)
```

And when we execute it:

```
$ python3 python_intro.py
Welcome, Rachel
Welcome, Monica
Welcome, Phoebe
Welcome, Ola
Welcome, You
```

As you can see, everything you have indented inside the `for` loop will be repeated for each element of the `names` list.


## Repeat <var>n</var> times

You can use the `for` loop with values other than lists.

It is often used with the `range()` function. When you want to repeat something 200 times, write:


```python
for i in range(200):
     print("I will never throw a plastic bag into a campfire again!")
```

How does it work
`for i in range(X)` can be translated as "for every number from zero to <var>X</var>".
The function `range` creates that sequence of numbers from zero to <var>X</var>.
Python stores each number in the variable `i` as it iterates through the loop.


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


Notice that the number `5` itself is not included in the result:
`range(5)` counts from 0 to 4.
When you start counting from zero and want to have five numbers, you end up with four.

## Summary

You learned:

* "Cycle" means a way to repeat a certain procedure multiple times in a row.
* "Range" helps when you need a specific number of repetitions.
