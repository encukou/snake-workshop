# Lists

In addition to strings and whole numbers, Python has other types of values.

Now we will look at one that is called *list*.
This is a value that contains other values within it.

Lists are entered by entering several values separated by commas, enclosed in square brackets.
Try creating a list of numbers from the lottery, for example.

```pycon
>>> [3, 42, 12, 19, 30, 59]
[3, 42, 12, 19, 30, 59]
```

So that you could work with such a list, save it to a variable:

```pycon
lottery = [3, 42, 12, 19, 30, 59]
```

So, you have a list!
But what can you do with it?
Look at how many numbers are on the list.
You can use a function that you already know.
Can you guess which one it is?

{% filter solution %}
```pycon
>>> len(lottery)
6
```

The function `len()` can determine not only the length of a string, but also the length of a list - that is, the number of its elements.
{% endfilter %}

Now try to sort the list. There is a method called `sort` for that.

```pycon
>>> lottery.sort()
```
This method doesn't return anything, but it quietly changes the order of numbers in the list. Print it again to see what happened.

```pycon
>>> lottery
[3, 12, 19, 30, 42, 59]
```
The numbers in the list are now sorted from lowest to highest value.

The `reverse` method works similarly, it reverses the order of elements. Try it out!

```pycon
>>> lottery.reverse()
>>> lottery
[59, 42, 30, 19, 12, 3]
```

## Adding to the list

Similarly to strings, lists can be concatenated using the `+` operator.

```pycon
>>> lottery + [5, 6, 7, 8]
[59, 42, 30, 19, 12, 3, 5, 6, 7, 8]
```
This will create a new list, the original one remains unchanged.

```pycon
>>> lottery
[59, 42, 30, 19, 12, 3]
```

If you want to add something to the original list, you can do so using the `append` method.
But be careful! This method needs to know what to add to the list.
The new value is entered in parentheses.

```pycon
>>> lottery.append(199)
```

The method again does not return anything, so it is necessary to write out a check for control.

```pycon
>>> lottery
[59, 42, 30, 19, 12, 3, 199]
```

## Selecting elements

When you want to take a closer look at one item from the list, it is useful to have the option to select a specific element.
In Python, square brackets are used for this.

If you want to select an element, enter the name of the list followed immediately by square brackets with the ordinal number of the element you want.

```pycon
>>> lottery[1]
```
Do you get the first element?

{% filter solution %}
```pycon
>>> lottery
[59, 42, 30, 19, 12, 3, 199]
>>> lottery[1]
42
```
No, you will receive the second element.

Programmers count from zero. So if you want the first element, ask Python for element number zero.

```pycon
>>> loterie[0]
42
```
At first, it's strange, but you can get used to it.
{% endfilter %}

The number of an element is also called an *index* and the process of selecting elements is called *indexing*.

Try indexing with other indices: 3, 100, 7, -1, -2, -6 or -100.
Try to predict the result before entering the command.
How will you do?

{% filter solution %}
```pycon
>>> lottery
[59, 42, 30, 19, 12, 3, 199]

>>> lottery[3]
19
```
Index 3 means the fourth element.

```pycon
>>> lottery[7]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
```
Element with index 7 does not exist - it results in error.

```pycon
>>> loterie[1000]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
```
Same for index 1000.

```pycon
>>> loterie[-1]
199
```
Index -1 means the *last* element.

```pycon
>>> loterie[-2]
3
```
Index -2 means the one before the last element.

```pycon
>>> loterie[-6]
42
```
Index -6 means the sixth element from the end.

```pycon
>>> loterie[-100]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
```

Such element does not exist, we get error.
{% endfilter %}


## Removal

If you want to remove something from the list, you can use indexes again.
This time with the `del` command.
Use the following code to remove the first number from the list, i.e. element number 0:

```pycon
>>> del lottery[0]
```

Then list it again. Something is missing!

```pycon
>>> lottery
[42, 30, 19, 12, 3, 199]
```

How would you remove the last element?

{% filter solution %}
```pycon
>>> del lottery[-1]
>>> lottery
[42, 30, 19, 12, 3]
```
{% endfilter %}

Sometimes it happens that you don't want to delete an element by position, but by what its value in the list.
For this purpose, the `remove` value is used, which finds and removes the given value:

```pycon
>>> lottery
[42, 3]
>>> lottery.remove(3)
>>> lottery
[42]
```

## Slicing

Apart from selecting one element from the list, it is also possible to select several elements - a part of the list, called a "sublist".

Make another longer list of numbers.

```pycon
>>> numbers = ["First", "Second", "Third", "Fourth"]
``` 

If you want to select elements from the second one onwards, put the number of this element in square brackets and then a colon.

```pycon
>>> numbers[1]
'Second'
>>> numbers[1:]
['Second', 'Third', 'Fourth']
``` 

By selecting a sub-list, the main list does not change, so you can continue selecting further:

```pycon
>>> numbers
['First', 'Second', 'Third', 'Fourth'].
>>> numbers[1:] 
['Second', 'Third', 'Fourth'].
>> numbers[2:] 
['Third', 'Fourth'].
>> numbers[3:] 
['Fourth'].
>> numbers[4:] 
[].
```

If you want to select elements from the beginning *up to* a certain element, put a colon *before* the number of the element you don't want in the result.

``` pycon
>>> numbers[2]
'Third'
>>>  numbers[:2]
['First', 'Second']
``` 

Task: If you have a list, how do you select all elements except the last one?
{% filter solution %} 
The last number has an index of -1, so I will select elements up to -1.

```pycon
>>> numbers[:-1]
['First', 'Second', 'Third']
``` 
Do you also see a smiley face in the code for selecting everything except the last element?
{% endfilter %}

The beginning and the end can be combined - you can put the number before or after the colon.

```pycon
>>> numbers
['First', 'Second', 'Third', 'Fourth']
>>> cisla[1:-1]
['Second', 'Third']
```

Slicing works also for the `del` command. Try deleting the middle two numbers:

```pycon
>>> numbers
['First', 'Second', 'Third', 'Fourth']
>>> del numbers[1:-1]
>>> numbers
['First', 'Fourth']
```

## Slicing strings

Square brackets also work with strings where they select letters:

```pycon
>>> food = 'chocolate'
>>> food[3]
'o'
>>> food[2:5]
'oco'
```

However, strings cannot be changed: `del`, `sort`, or `append` only work on lists.

XXX: this task is probably not a good idea
Task: Imagine you have a Czech female name in the variable `jmeno` such as `'Ola'`, `'Krystýna'`, or `'Růžena'`.
How do you create the second case? 

Take the name up to the last letter and add `'y'`. For example:

{% filter solution %}
``` python
>>> name = 'Růžena'
>>> name[:-1] + 'y'
'Růženy'
>>> name = 'Krystýna'
>>> name[:-1] + 'y'
'Krystýny'
```
{% endfilter %}

## Summary

Phew! There was quite a lot to learn about lists. Let's summarize what you already know:

* A **list** is an ordered sequence of values.
* Using **methods**, a list can be sorted (`sort`) and reversed (`reverse`), or an element can be added (`append`) or removed (`remove`) from it.
* Elements can be **selected** or **deleted** (`del`) by index.
* The numbering starts **from zero**, negative numbers take elements from the end.
* A **sublist** is a certain part of a list.
* With **strings**, selecting elements and substrings works similarly.

Are you ready for the next part?
