# Dictionaries

"Another type of value that can contain additional values within it is a *dictionary*. Imagine a translation dictionary, such as this Czech-English one:"

* **Jablko**: Apple
* **Knoflík**: Button
* **Myš**: Mouse

"The dictionary in Python contains *records*, and each record assigns some *value* to a *key*.
In our example, the value *Apple* is assigned to the key *Jablko*,
the value *Button* belongs to the key *Knoflík*
and the key *Myš* points to *Mouse*."

"In Python, such a dictionary would be written as follows:"

``` python
slovnik = {'Jablko': 'Apple', 'Knoflík': 'Button', 'Myš': 'Mouse'}
```

This is a Python dictionary that translates Czech words to English:

- 'Jablko' translates to 'Apple'
- 'Knoflík' translates to 'Button'
- 'Myš' translates to 'Mouse'

"These keys and values are words - short texts, i.e. strings, that need to be put in quotation marks. Each key is separated from its value by a colon, individual pairs are separated from each other by a comma, and the entire dictionary is enclosed in curly braces."

"When you want to find something in such a dictionary, you need to know what to look for. You need a *key*. Using square brackets, you can find out the value that corresponds to a given key."

``` 
slovnik['Jablko']
'Apple'
```

Translation: 

```
slovnik['Jablko']
'Apple'
```

This appears to be a code snippet written in Czech that accesses a dictionary (slovnik) and retrieves the English translation for the word "Jablko", which is "Apple".

"It's similar to lists, only in square brackets there's no index (order of the element) or range with a colon, but rather a key."

[note]
On the contrary, it is not possible - the dictionary does not allow you to directly determine the key based on the value.
For translation from English to Czech, you would need a second dictionary.

"Changing dictionaries."

"What happens when the key is not in the dictionary?"

This is an error message in Python. It says: "KeyError: 'Pes'". It means that the key "Pes" is not found in the dictionary (slovnik).

"Python complains about `KeyError` - a key error."

Similarly to lists, dictionaries can also be modified. You create a new entry like this:

```python
>>> dictionary['Pes'] = 'Dog'
>>> dictionary
{'Jablko': 'Apple', 'Knoflík': 'Button', 'Myš': 'Mouse', 'Pes': 'Dog'}
```

The text is a Python code snippet for adding a new key-value pair to a dictionary. The key is 'Pes' which means 'Dog' in English. The existing dictionary contains the translations for the words 'Jablko' (Apple), 'Knoflík' (Button), and 'Myš' (Mouse).

[note]

Unlike a translation dictionary, a Python dictionary does not have to be sorted alphabetically. It is not necessary because the computer can quickly search even without sorting.

If you need to change an existing record, use the same command. Only one value can belong to one key.

```
>>> slovnik['Pes'] = 'Extension cord'
>>> slovnik
{'Jablko': 'Apple', 'Knoflík': 'Button', 'Myš': 'Mouse', 'Pes': 'Extension cord'}
```

Translation: 

```
>>> slovnik['Pes'] = 'Extension cord'
>>> slovnik
{'Jablko': 'Apple', 'Knoflík': 'Button', 'Myš': 'Mouse', 'Pes': 'Extension cord'}
```

Note: This is already in English, so no translation is necessary.

"Should we mention non-homogeneous dictionaries?"

"If you want to delete a record from the dictionary, it is done similarly to lists with the command 'del'."

```
>>> del slovnik['Pes']
>>> slovnik
{'Jablko': 'Apple', 'Knoflík': 'Button', 'Myš': 'Mouse'}
```

Translation: 

```
>>> del slovnik['Pes']
>>> slovnik
{'Jablko': 'Apple', 'Knoflík': 'Button', 'Myš': 'Mouse'}
```

This is a code snippet written in Python programming language. It removes the key-value pair with the key 'Pes' from the dictionary named 'slovnik' and then prints the updated dictionary. The dictionary contains translations of words from Czech to English. The updated dictionary now includes only three words - 'Jablko' (Apple), 'Knoflík' (Button), and 'Myš' (Mouse).

"And if you want to find out how many records are in the dictionary, you will ask similarly as for the number of characters in a string or elements in a list. You will use the `len()` function."

The translation of the Czech text is: 

``` 
>>> len(slovnik)
3
``` 

This is actually a code snippet in Python programming language, so there is no direct translation to English. It is asking the interpreter to return the length of the variable "slovnik", which is most likely a dictionary containing three items.

I'm sorry, but there is no Czech text provided for me to translate. Please provide the text and I will be happy to assist you.

* Contacts
* When a number isn't a number
* More numbers

"To ponder" or "for reflection."

"To each key can only belong one value. How would you arrange it to have more values?"

"Try to save these contacts to a Python variable:"

Katka:
* 4925219

Jirka:
* 7477058
* 3251156

Verča:
* 1019103

This text appears to be a list of names and associated numbers in Czech.

More values can be stored in a list.
The values will be lists of numbers:

```pycon
>>> contacts = {'Katka': ['4925219'], 'Jirka': ['7477058', '3251156'], 'Verča': ['1019103']}
```

"Verča has moved abroad and has a new number: `+897 3788509`."

I'm sorry, but there is no Czech text provided. Please provide the text you would like me to translate.

"Shrnutí" in Czech means "summary" in English.

"Great! What do you know about dictionaries?"

The following is the English translation of the Czech text:

* A **record** consists of a **key** and a **value**.
* In a dictionary, you search for an item using a **key**.
* Records can be overwritten, added, or deleted using `del`.

Are you ready for the next part?