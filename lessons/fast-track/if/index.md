# Conditions

"You will want to perform a lot of things in the code only if certain conditions are met. Python has *conditional statements* for this purpose."

"We will now try to gradually write a program that verifies a secret password."

"To start, write a program that outputs `True` when you enter the word `čokoláda` (chocolate in English). If a different password is entered, it will output `False`."

```python
password = input('Enter password: ')
print(password == 'chocolate')
```

"When - then"

"Printing `True` is not very interesting. A better program would do this:"

* Asks for a secret password
* When the password is correct:
    * Allows the user inside.

In English, "když" is translated as "if". And that is also the name of a Python command. It is used like this:

```python
password = input('Enter password: ')
if password == 'chocolate':
    print('Correct! Welcome.')
```

"The conditional statement begins with `if`, continues with a condition (such as a comparison) and ends with a colon."

"After the line with `if`, there is an *indented* command - there are 4 spaces at the beginning of the line. Python recognizes that this part of the program should be executed only when the condition is true."

"Save and run"

```
(venv) $ python python_intro.py
Enter password: chocolate
Correct! You may enter.
(venv) $ python python_intro.py
Enter password: sesame
```

"Odsazování" in English means "indentation" or "spacing".

"Just because four spaces are needed at the beginning of a line doesn't mean you have to press the spacebar four times. Some editors automatically indent (if you write the line with 'if' correctly). However, in all properly configured editors, you can indent using the <kbd>↹ Tab</kbd> key, and the <kbd>⇧ Shift</kbd>+<kbd>↹ Tab</kbd> combination will return the line back one indentation level."

"Jinak" in English means "otherwise" or "differently".

"In the previous example, the code was executed only if the condition was met. An even better program would be this one:"

Here's the English translation of the Czech text:

* Asks for the secret password
* When the password is correct:
    * Lets the user in
* Otherwise <small>(i.e., if the password was incorrect)</small>:
    * Triggers the alarm

Python has the command `else` for that - "otherwise":

```python
password = input('Enter password: ')
if password == 'chocolate':
    print('Correct! Welcome.')
else:
    print('WARNING! WARNING!')
    print('UNAUTHORIZED ACCESS!')
```

"Funuje to?" translates to "Does it work?" in English.

```
(venv) $ python python_intro.py
Enter password: chocolate
Correct! You may enter.
(venv) $ python python_intro.py
Enter password: sesame
WARNING! WARNING!
UNAUTHORIZED ENTRY!
```

"More options"

Sometimes it happens that a program needs to decide between multiple options. For this purpose, the `elif` command is used (short for "else if" in English).

"By using this method, it is possible to comment on the volume of the music."

Ask about the volume, remember the numerical response.
* When the volume is up to 20:
    * it displays "It's quite quiet."
* Otherwise, when the volume is up to 40:
    * it displays "Like good background music."
* Otherwise, when the volume is up to 60:
    * it displays "Great, I hear all the details."
* Otherwise, when the volume is up to 80:
    * it displays "Good for a party."
* Otherwise, when the volume is up to 100:
    * it displays "A bit too loud!"
* Otherwise:
    * it displays "My ears are bleeding!"

"In Python, it would be written like this:"

```python
volume = int(input('What is the radio volume set to? '))
if volume < 20:
     print("It's quite quiet.")
elif volume < 40:
     print("Good background music.")
elif volume < 60:
     print("Great, I can hear all the details.")
elif volume < 80:
     print("Good for a party.")
elif volume < 100:
     print("A bit too loud!")
else:
    print("My ears are bleeding!") 
```

```
(venv) $ python python_intro.py
What is the radio volume set to? 28
Good as background music.
```

Notice that only one option is always selected. If you enter `28`, Python will reach `volume < 40`, display the appropriate message, and skip all other options.

Summary.

"What did you see in this lesson?"

The following is the English translation of the Czech text:

*The commands **if** (if), **elif** (else, if), and **else** (else) condition other commands.
* **Indentation** is used for conditional commands that follow `if`, etc.