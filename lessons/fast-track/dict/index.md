> [warning]
> This is a machine-generated translation.
> If you're not at the in-person workshop, try the [DjangoGirls tutorial](https://tutorial.djangogirls.org/en/) for an intro to Python!

# Dictionaries

Another type of value that can contain additional values within it is a *dictionary*. Imagine a translation dictionary, such as this Czech-English one:

* **Jablko**: Apple
* **Knoflík**: Button
* **Myš**: Mouse

The dictionary in Python contains *records*, and each record assigns some *value* to a *key*.
In our example, the value *Apple* is assigned to the key *Jablko*,
the value *Button* belongs to the key *Knoflík*
and the key *Myš* points to *Mouse*.

In Python, such a dictionary would be written as follows:

``` python
dictionary = {'Jablko': 'Apple', 'Knoflík': 'Button', 'Myš': 'Mouse'}
```

These keys and values are words - short texts, i.e. strings, that need to be put in quotation marks. Each key is separated from its value by a colon, individual pairs are separated from each other by a comma, and the entire dictionary is enclosed in curly braces.

When you want to find something in such a dictionary, you need to know what to look for. You need a *key*. Using square brackets, you can find out the value that corresponds to a given key.

``` python
dictionary['Jablko']
'Apple'
```
It's similar to lists, only in square brackets there's no index (order of the element) or range with a colon, but rather a key.

>[note]
>The opposite direction is not possible - the dictionary does not allow you to directly determine the key based on the value.
>For translation from English to Czech, you would need a second dictionary.

## Modifying dictionaries

What happens when the key is not in the dictionary?
```pycon
>>> slovnik['Pes']
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'Pes'
```
Python complains about `KeyError` - a key error.

Similarly to lists, dictionaries can also be modified. You create a new entry like this:

```pycon
>>> dictionary['Pes'] = 'Dog'
>>> dictionary
{'Jablko': 'Apple', 'Knoflík': 'Button', 'Myš': 'Mouse', 'Pes': 'Dog'}
```


>[note]
>Unlike a translation dictionary, a Python dictionary does not have to be sorted alphabetically. It is not necessary because the computer can quickly search even without sorting.

If you need to change an existing record, use the same command. Only one value can belong to one key.

```pycon
>>> slovnik['Pes'] = 'Extension cord'
>>> slovnik
{'Jablko': 'Apple', 'Knoflík': 'Button', 'Myš': 'Mouse', 'Pes': 'Extension cord'}
```


If you want to delete a record from the dictionary, it is done similarly to lists with the command 'del'.

```pycon
>>> del slovnik['Pes']
>>> slovnik
{'Jablko': 'Apple', 'Knoflík': 'Button', 'Myš': 'Mouse'}
```

And if you want to find out how many records are in the dictionary, you will ask similarly as for the number of characters in a string or elements in a list. You will use the `len()` function.

``` pycon
>>> len(slovnik)
3
``` 

## To think about 

To each key can only belong one value. How would you arrange it to have more values?

Try to save these contacts to a Python variable:

Katka:
* 4925219

Jirka:
* 7477058
* 3251156

Verča:
* 1019103

{% filter solution %} More values can be stored in a list.
The values will be lists of numbers:

```pycon
>>> contacts = {'Katka': ['4925219'], 'Jirka': ['7477058', '3251156'], 'Verča': ['1019103']}
```
{% endfilter %}

## Summary

Great! What do you know about dictionaries?

* A **record** consists of a **key** and a **value**.
* In a dictionary, you search for an item using a **key**.
* Records can be overwritten, added, or deleted using `del`.

Are you ready for the next part?
