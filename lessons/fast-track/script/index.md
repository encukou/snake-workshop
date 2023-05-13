# Save it

So far, you have written all programs in the console in the interactive mode of Python, in which Python always responded with a result after a command was written. When you exit Python (or turn off the computer), everything you have programmed so far will be lost.

Larger programs are more durable: they are saved in files and can be run again anytime.

It's time to try it out. You will need:

1. End interactive mode of Python
2. Open code editor
3. Save code to a new file
4. Run code from the file!

As a first step, turn off Python. There is a function for that: `exit()`.

```pycon
>>> exit()
``` 

So you'll get back to the command line. Do you remember it? You won't see `>>>` anymore, but a line ending with `$` or `>`. Commands like `cd` and `mkdir` will work here, but not Python commands like `1 + 1`.

I hope you have installed a text editor. Now open it, create a new file and write this command into it:
```python
print('Hello, PyLadies!')
```

Save a new file under a descriptive name: `python_intro.py`.
Save it to a directory where you keep files for this workshop.
The name must end with `.py`: this extension tells the editor or operating system that it is a Python program and Python can run it.

>[Note] Syntax highlighting
>After saving, the text should be colored. In interactive Python mode, everything should have the same color, but now you should see that the function name `print` is set in a different color than the string in parentheses. >You don't choose the colors {{gnd('yourself', 'yourself')}}, the editor selects them based on how Python understands the code. It's called "syntax highlighting" and it's a useful feature. It takes a little practice, but > >colors can suggest that you're missing a quote after the string or have a typo in a keyword like `del`. That's one of the reasons we use programming editors :)

If you have the file saved, it's time to run it! Using the skills you learned in the command line section, *change the directory* to where you saved the file. {% if var('coach-present') -%} (If you don't know what to do next, ask your coach for help.) {% endif %}"

Now, using Python, run the code in the file: enter the command `python`, a space and the name of the file to run. (It's similar to the `cd` command for a specific directory - <code>cd <var>directory_name</var></code>.)

```
(venv) $ python python_intro.py
Hello, PyLadies!
```

This is an output from running a Python script called `python_intro.py` while in a virtual environment (`venv`). The script outputs the message "Hello, PyLadies!" to the console.

Does it work? Can you see the text? If yes, you have just run your first real Python program! Do you feel awesome?

## Output

The function `print()` that you used can *output* something on the screen. In the console, the values of expressions were automatically printed so that you could check them continuously, but programs in files tend to be more complex and outputs from every step would be confusing. Therefore, you need `print()` for outputting. Try the following program:
```
name = 'Ola'

"I am" + name     #  Python will not display this.
print(name * 8)  #  This is displayed!
```

Then run the program.
```
(venv) $ python python_intro.py
OlaOlaOlaOlaOlaOlaOlaOla
```

What happened?
When you run a program file, Python goes through it from top to bottom, line by line, executing individual commands:
* sets the variable `name` to the string `'Ola'`,
* concatenates the strings `'I am'` and `'Ola'`, but discards the result,
* repeats the string `'Ola'` eight times and prints the result using `print()`. 

You can put multiple values separated by commas inside the parentheses of the `print()` function. Try changing the contents of the file to the following program and run it again:
```
name = 'Amálka'
age = 5
print('I am', jmeno, 'and I am', vek, 'years old')

print('Next year I will be', vek + 1)
```

## Input 

Another useful function is `input()`, which can ask a question. It will then return the answer as a string, which you can save to a variable.
```
name = input('What is your name?')
print(name, 'knows how to program!')
```

When you run the program, it will ask you a question. Enter the answer directly into the command line using your keyboard. Python will read it and use it as the result of the `input` function, which will store it in the `name` variable. And as part of the next line of the program, it will print it out.

```
(venv) $ python python_intro.py
What's your name? Ola
Ola knows how to program!
(venv) $ python python_intro.py
What's your name? Princess
Princess knows how to program!
```

The function `input()` from the keyboard always returns text: when the user enters `1234`, Python takes it as a string of digits 1, 2, 3, 4.

When you want to load a number from the keyboard instead of text, you have to use a function that can convert a string to a number:

```python
year = int(input('What is the current year? '))
print('Last year was', year - 1)
```

## Comments

Did you notice in one of the previous program notes the symbol `"#"`?

```python
name = 'Ola'
"I am" + name   # This will not be printed by Python.
print(name * 8) # This is it!
```

These are so-called "comments". They are intended for humans only: Python completely ignores them.

"Now tha you are saving your programs to the disk and can return to them, it is important that they are *readable*: so that not only computers, but also people can recognize what those instructions are supposed to do. Whenever you write a more complex piece of code, try to add a comment with an explanation. When you return to the program in a few days or months, you will thank yourself!

## Summary

The following is the English translation of the Czech text:

* The command **python** runs a saved file as a Python program.
* The function **print** outputs values.
* The function **input** reads strings that the user enters on the keyboard.
* **Comments** can clarify complex code. Python ignores them.
