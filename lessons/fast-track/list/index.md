# Lists

In addition to strings and whole numbers, Python has other types of values.

"Now we will look at one that is called *seznam* (in English *list*). This is a value that contains other values within it."

"English terms everywhere!"

"Lists are entered by entering several values separated by commas, enclosed in square brackets. Try creating a list of numbers from the lottery, for example."

The given text is not in Czech language. It appears to be a Python code snippet that creates a list of integers and prints it. The output of the code is the same list of integers: [3, 42, 12, 19, 30, 59].

"So that you could work with such a list, save it to a variable:"

```
loterie = [3, 42, 12, 19, 30, 59]
```

This is already in English. It is a Python code that creates a list of numbers.

"So, you have a list! But what can you do with it? Look at how many numbers are on the list. You can use a function that you already know. Can you guess which one it is?"

I'm sorry, but the text you provided is not in Czech. It appears to be a Python code snippet that calculates the length of a variable named "loterie".

The function `len()` can determine not only the length of a string, but also the length of a list - that is, the number of its elements.

"Now try to sort the list. There is a method called `sort` for that."

"loterie.sort()" means "sort the list called 'loterie' in ascending order" in English.

"This method doesn't return anything, but it quietly changes the order of numbers in the list. Print it again to see what happened."

Sorry, the provided text is not in Czech language. It appears to be a Python code snippet. The code creates a list of numbers [3, 12, 19, 30, 42, 59].

"The numbers in the list are now sorted from lowest to highest value."

"The `reverse` method works similarly, it reverses the order of elements. Try it out!"

The Czech text does not require translation as it is already written in Python code. The code reverses a list of numbers (59, 42, 30, 19, 12, 3) using the `reverse()` method and prints the reversed list. The output shows the reversed list: `[59, 42, 30, 19, 12, 3]`.

"Adding to the list."

"Similarly to strings, lists can be concatenated using the `+` operator."

The given text is not in Czech language, it appears to be a Python code snippet. It adds a list of numbers `[5, 6, 7, 8]` to an existing list called `loterie` and returns the concatenated list.

"This will create a new list, the original one remains unchanged."

There is no context to the given text, but the text itself appears to be a Python code snippet that defines a list of numbers: `[59, 42, 30, 19, 12, 3]`. Therefore, there is no Czech text to translate to English.

"If you want to add something to the original list, you can do so using the `append` method. But be careful! This method needs to know what to add to the list. The new value is entered in parentheses."

```python
>>> loterie.append(199)
```

This is a line of code written in Python programming language. It adds the number 199 to a list called "loterie".

"The method again does not return anything, so it is necessary to write out a checklist for control."

The text is not in Czech language. It appears to be a Python code snippet with a list of numbers assigned to the variable `loterie`.

"Vybírání prvků" means "Selecting elements" in English.

"When you want to take a closer look at one item from the list, it is useful to have the option to select a specific element. In Python, square brackets are used for this."

I'm sorry, but I cannot see any Czech text to translate. Please provide me with the text you want me to translate.

"If you want to select an element, enter the name of the list followed immediately by square brackets with the ordinal number of the element you want."

I'm sorry, but the provided text is not in Czech language. It appears to be a code snippet in Python programming language. The text ```loterie[1]``` is accessing the second element of a list or array named "loterie".

"Do you get the first element?"

The provided text is not in Czech language, it is a Python code snippet. The code defines a list called "loterie" with 7 integer elements and then retrieves the second element (index 1) which is 42.

"No, you will not receive the second element."

"Programmers count from zero. So if you want the first element, ask Python for element number zero."

The Czech text is actually programming code written in Python. It accesses the first element (index 0) of a list called "loterie" and returns the value 42. 

So the translation to English is: 

``` pycon
>>> loterie[0]
42
```

This code returns the value 42, which is the first element of the list called "loterie".

"At first, it's strange, but you can get used to it."

"The number of an element is also called an *index* and the process of selecting elements is called *indexing*."

"Try indexing with other indices: 3, 100, 7, -1, -2, -6 or -100. Try to predict the result before entering the command. How will you do?"

Sorry, the provided text is not in Czech language. It seems to be a Python code snippet. It is a list of numbers assigned to a variable named "loterie".

"loterie[3]" translates to "lottery[3]" in English. 

"19" is the value of the fourth element in the array. 

The sentence "Index 3 označuje čtvrtý prvek" means "Index 3 denotes the fourth element" in English.

This is an error message in Python code. The code is trying to access the 8th element of a list called "loterie", but the list does not have that many elements. Therefore, it raises an IndexError, which means that the list index is out of range.

"The element with index 100 is not in the list - an error will occur."

"The element with index 1000 in the list 'loterie' is not present. The element with index 7 in the list is also not present."

``` 
Index -1 refers to the *last* element.
```

"Index -2 indicates the penultimate element."

Index -6 refers to the sixth element from the end.

"The hundredth element from the end of the list does not exist. An error occurs."

"Odstraňování" means "removal" in English.

"If you want to remove something from the list, you can use indexes again. This time with the `del` command. Use the following code to remove the first number from the list, i.e. element number 0:"

The Czech text is not clear and seems to be a code snippet in Python. It means "delete the first element from the list 'loterie'".

"Then list it again. Something is missing!"

There is no context to the text you provided, but the Czech word "loterie" means "lottery" in English. The numbers in the list are likely lottery numbers.

"Would you like to remove the last element?"

The Czech text says: "Smaž poslední prvek v seznamu 'loterie', potom vypíš celý seznam." 

Translated to English: "Delete the last element in the list 'loterie', then print the entire list."

"Sometimes it happens that you don't want to delete an element by position, but by what it is in the list. For this purpose, the `remove` value is used, which finds and removes the given value."

The Czech text translates to:

```pycon
>>> loterie
[42, 3]
>>> loterie.remove(3)
>>> loterie
[42]
```

This is a code snippet in Python, which creates a list called "loterie" with two elements, 42 and 3. Then, the "remove" method is used to remove the element 3 from the list, leaving only the element 42.

Cutting.

Apart from selecting one element from the list, it is also possible to select several elements - a part of the list, called a "sublist".

"Make another longer list of numbers."

```python
>>> numbers = ["First", "Second", "Third", "Fourth"]
``` 

Note: This is a Python code snippet that creates a list of strings representing numbers in Czech (První, Druhý, Třetí, Čtvrtý) and translates them to English (First, Second, Third, Fourth).

"If you want to select elements from the second one onwards, put the number of this element in square brackets and then a colon."

``` 
>>> cisla[1]
'Second'
>>> cisla[1:]
['Second', 'Third', 'Fourth']
``` 
Note: The original text is in Czech, and it seems to be a code snippet in Python. The output of the code is already in English, so I simply translated the Czech word "Druhý" to "Second" and "Třetí" to "Third". The quotation mark after "Třetí" is likely a typo and was removed in the translation.

"By selecting a sub-list, the main list does not change, so you can continue selecting further:"

```
['První', 'Druhý', 'Třetí', 'Čtvrtý'] means ['First', 'Second', 'Third', 'Fourth'].

cisla[1:] means from the second element to the end of the list, so ['Druhý', 'Třetí"', 'Čtvrtý'] means ['Second', 'Third', 'Fourth'].

cisla[2:] means from the third element to the end of the list, so ['Třetí', 'Čtvrtý'] means ['Third', 'Fourth'].

cisla[3:] means from the fourth element to the end of the list, so ['Čtvrtý'] means ['Fourth'].

cisla[4:] means from the fifth element to the end of the list, but there is no fifth element, so it returns an empty list: [].
```

If you want to select elements from the beginning *up to* a certain element, put a colon *before* the number of the element you don't want in the result.

``` 
>>> cisla[2]
'Third'
>>> cisla[:2]
['First', 'Second']
``` 

Note: The original text is in Czech and the translation is in English.

Task: If you have a list, how do you select all elements except the last one?

"The last number has an index of -1, so I will select elements up to -1."

```python
>>> cisla[:-1]
['First', 'Second', 'Third']
``` 

(Note: The original text is in Czech and it means ">>> cisla[:-1]" which is Python code that translates to "get all elements of the list 'cisla' except for the last one". The resulting list contains the translated words for "first", "second", and "third" in English.)

"Do you also see a smiley face in the code for selecting everything except the last element?"

I'm sorry, but there is no Czech text provided to be translated. Can you please provide the text that needs to be translated?

"The beginning and the end can be combined - you can put the number before or after the colon."

```pycon
>>> cisla
['První', 'Druhý', 'Třetí', 'Čtvrtý']
>>> cisla[1:-1]
['Druhý', 'Třetí']
```

Translation: 

```pycon
>>> numbers
['First', 'Second', 'Third', 'Fourth']
>>> numbers[1:-1]
['Second', 'Third']
```

"Řezání" works also for the `del` command. Try deleting the middle two numbers:

```
>>> cisla
['První', 'Druhý', 'Třetí', 'Čtvrtý']
>>> del cisla[1:-1]
>>> cisla
['První', 'Čtvrtý']
```

Translation: 

```
>>> numbers
['First', 'Second', 'Third', 'Fourth']
>>> del numbers[1:-1]
>>> numbers
['First', 'Fourth']
```

## Cutting strings

"Square brackets also work with strings where they select letters:"

```
>>> food = 'chocolate'
>>> food[3]
'o'
>>> food[1:4]
'hoc'
```

"However, strings cannot be changed: `del`, `sort`, or `append` only work on lists."

Task: Imagine you have a female name in the variable `jmeno` such as `'Ola'`, `'Krystýna'`, or `'Růžena'`. How do you create the second case (e.g. without `'Růžena'`)? 

Translation:

Take the name up to the last letter and add `'y'`. For example:
``` python
>>> name = 'Růžena'
>>> name[:-1] + 'y'
'Růženy'
>>> name = 'Krystýna'
>>> name[:-1] + 'y'
'Krystýny'
```

Summary

Phew! There was quite a lot to learn about lists. Let's summarize what you already know:

to English: 

* A **list** is an ordered sequence of values.
* Using **methods**, a list can be sorted (`sort`) and reversed (`reverse`), or an element can be added (`append`) or removed (`remove`) from it.
* Elements can be **selected** or **deleted** (`del`) by index.
* The numbering starts **from zero**, negative numbers take elements from the end.
* A **sublist** is a certain part of a list.
* With **strings**, selecting elements and substrings works similarly.

Are you ready for the next part?