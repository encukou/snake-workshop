> [warning]
> This is a machine-generated translation, meant to support the in-person workshop.

#<var>N</var>-tuple

Do you already know that you can return a value from a function using the `return` statement?


``` python
def double(x):
    return x * 2
``` 

But how to write a function that returns two values? For example, I want to write a function that calculates the quotient and remainder after division.

Two values can be returned as a list.

```python
def quotient_and_remainder(a, b):
    quotient = a // b
    remainder = a % b

    return [quotient, remainder]

print(quotient_and_remainder(5, 2))
```

But it's better to return a *pair* of numbers - two numbers separated by a comma.
```python
def quotient_and_remainder(a, b):
    quotient = a // b
    remainder = a % b

    return quotient, remainder

print(quotient_and_remainder(5, 2))
```

This is called a pair - and similarly, a trio, quartet, quintet, sextet, simply an <var>n</var>-tuple of values is formed.
It works similarly to a list, but it cannot be changed - for example, additional elements cannot be added to it using `append`.
When I have a trio, it always remains as a trio.

When you have an <var>n</var>-tuple, you can *unpack* it by assigning it to several variables.

```
quotient, remainder = quotient_and_remainder(5, 2)

print(quotient)
print(remainder)
```


N-tuples have many uses, for example:

* A point in space has 3 coordinates - a triple of numbers!
* A playing card has a color and a value - a pair of numbers and strings, for example `(2, 'spades')`.

Sometimes it is necessary to add an <var>n</var>-tuple to a list, for example, to save information about a whole pack of playing cards. In similar cases, it is necessary to enclose each <var>n</var>-tuple in parentheses to make it clear where it begins and ends. Here is a list of pairs:


```python
hand = [(2, 'spades'), (10, 'clubs'), (8, 'diamonds')]
``` 

When you have such a list, you can go through it in a `for` loop using unpacking.

```
for value, color in hand:
    print('I am playing', value, 'and they are', color)
```


## Zip

The function `zip` returns an <var>N</var>-tuple or a sequence of <var>n</var>-tuples, which allows you to iterate through multiple lists simultaneously, where the elements correspond to each other.

```python
Items = ['grass', 'sun', 'carrot', 'river']
Colors = ['green', 'yellow', 'orange', 'blue']
Places = ['on the ground', 'up high', 'on the plate', 'behind the wall']


for item, color, place in zip(items, colors, places):
    print(color, item, 'is', place)
```    
    

In this cycle, you will first receive a trio of the first elements from all three lists, then a trio of all second elements, then third, and so on.

## Summary

What did you learn this time?

* Using a *<var>n</var>-tuple*, several values can be combined into one.
* *<var>N</var>-tuples* can be unpacked into several variables.
* The `zip` function returns a sequence of *<var>n</var>-tuples*, in which the elements come from several lists.
