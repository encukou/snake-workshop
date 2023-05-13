# Graphics

Now we will show you how to write a graphical application.

The Python language itself contains tools for drawing images, but they are not very suitable for creating games. Therefore, we will use a library (extension) called Pyglet, which is specifically built for interactive graphics.

But we have to install it separately first. The safest way is to enter the following two commands into the command line with the virtual environment turned on. (There are also simpler ways, but they require a "correctly" configured system.)

Update the `pip` tool, which is capable of installing libraries for Python:
```console
(venv)$ python -m pip install --upgrade pip
```
(In translation: **Python**, run the **m**odule **pip** and tell it to **in**stall and optionally **upgrade** the **pip** library.)

Installing Pyglet itself:
```console
(venv)$ python -m pip install pyglet
```
(In translation: **Python**, run the **m**odule **pip** and tell it to **in**stall the **pyglet** library.)

For me, the installation looks something like this:

```console
(venv)$ python -m pip install --upgrade pip
Requirement already satisfied: pip in ./venv/lib/python3.6/site-packages (18.0)
(venv)$ python -m pip install pyglet
Collecting pyglet
  Downloading pyglet-1.2.4-py3-none-any.whl (964kB)
Installing collected packages: pyglet
Successfully installed pyglet-1.2.4
```
The important thing is "Successfully installed", or "Requirement already satisfied" at the end. This means that the library is ready to use!

## Program skeleton

Now try to create a new file in the editor, save it as `graphics.py`, and write the following program in it:

```python
import pyglet
window = pyglet.window.Window()
pyglet.app.run()
print('Done!')
```

Run it. A black window should appear.
>[note] Is the window not black? On some computers (often with macOS and some types of Linux), it happens that the window is not black, but there is some "mess" in it. That's okay. Before we start drawing in the window, we >will clean up the mess.

>[note] If you receive the error `AttributeError: module 'pyglet' has no attribute 'window'`, check that you named the file `graphics.py` and not `pyglet.py`. Save the file in the editor as `graphics.py`, delete any file named >`pyglet.py`, and try again.

>[note] Another mistake?
>Graphics are a sensitive matter - you are using a system with many parts that can break (Python, Pyglet, OpenGL, graphics card and its driver, operating system, ...).
>If it doesn't work for you, it's best to consult with an expert.

Done? Let's explain what is happening in this program.

The command `import pyglet` will give you access to the graphics library, just like `import random` gives you access to functions related to random numbers.

The call to `pyglet.window.Window()` creates a new *window* on the screen. It returns an object that can be used to control this window; it is stored in the variable `window`.

The call to `pyglet.app.run()` then launches the application.

The simple programs you have written so far are descriptions of a process - similar to cooking recipes. A sequence of steps that Python executes sequentially from the first to the last. Sometimes something is repeated and some steps can be "wrapped" into a function, but we have always described one procedure from beginning to end so far.

Programs for more complex applications look more like a manual for a car mechanic than a recipe. They describe what should happen in a given situation. For example, a program for a text editor could look like this:

+ When the user presses a letter on the keyboard, add it to the document.
+ When the user presses <kbd>⌫ Backspace</kbd>, erase the last letter.
+ When the user presses the Save button, write the file to disk.

And such a program can be written as a "recipe" - but that recipe is the same for all applications:

+ do foreever:
  * Wait until something interesting happens (pressing a key, button, ...)
  * React to the situation that has occurred.

And that is exactly what `pyglet.app.run()` does. It processes *events*, situations that need to be responded to. In your program, it currently responds to the window close button and the <kbd>Esc</kbd> key by closing the window and exiting.

"Your programming task now is to describe what other events are interesting and how to respond to them."

## Event management

"The easiest event you can handle is typing on a keyboard."

"Try putting the following code just above the line 'pyglet.app.run()' in the program:"

This is a code snippet written in Python, not Czech. It defines an event listener for a window object. When the user types text into the window, the `on_text` function will be called and the text will be printed to the console.

"What is this?
It is a function definition, but at the beginning it has a *decorator* - the line starting with an at sign.
The `window.event` decorator is a way to tell Pyglet to run this function when something interesting happens."

"What's interesting? Pyglet finds out based on the function name: 'on_text' reacts to text. Whenever the user presses a key, Pyglet calls your function!"

"And what does your function do? It calls `print`. You already know that. The text entered will be displayed on the console from which you are running the program."

[note]
The `print()` function still outputs text to the same place as before.
Just because a graphical window is open doesn't mean that everything will suddenly start writing to it.

Drawing

"How to write in a textbox? That is a bit more complicated than in a console. The text in the box can have different colors, sizes, fonts, and can be shifted or rotated in various ways."

"All these font attributes need to be saved (along with the text itself) in the `Label` object (meaning 'label'). Try it - put the following code under the line with `window = `:"

(Note: The word "popisek" in the original text is translated as "label" in English, which is the commonly used term for the GUI element in programming.)

"Hello!"

In the variable `label` you will now have a label with the text "Hello" that belongs to position (10, 20) - 10 points from the right edge of the window and 20 points from the bottom.

[note]

Other properties besides position are not specified here, so reasonable "default" values will be used: white color, small but readable font.

"The caption, however, will not write itself. Similarly to calling `print` to display text in the console, responding to the *window drawing* event - `on_draw` - is necessary to draw text."

Put this code under the `on_text` function:

This is not Czech text, it appears to be Python code. The code is defining an event handler for a window object. When the window is drawn, it will clear the window and draw a label.

"This function is called by Pyglet whenever it is necessary to draw the content of the window. In animations (movies or games), this is often required 60 times per second ("60 FPS")."

The function does two things:
* Clears the entire window (paints it black)
* Renders text.

"In the window, you will now see a greeting!"

"Try changing the `on_text` function so that the entered text is displayed in a window instead of on the console. This is done by assigning the text to the *attribute* `label.text`."

This is Python code, not Czech text. It defines an event handler for a window that prints the old text of a label, sets the label's text to the new text, and then prints the new text of the label.

"Can you add new text to the old one in this function so that the program works as a simple text editor?"

The given text is not in Czech language, it is a code snippet written in Python programming language. It is an event listener function that listens for any text input and updates a label's text with the newly entered text.

"Next events"

"What other events can be responded to? They are all described in the Pyglet documentation (https://pyglet.readthedocs.io/en/latest/modules/window.html#pyglet.window.Window.on_activate). Here are a few interesting ones."

"Stisk klávesy" translates to "Press a key" in English.

"The keys that do not enter text (arrows, <kbd>Backspace</kbd> or <kbd>Enter</kbd>, etc.) can be recognized in the `on_key_press` event."

The function `on_key_press` has two arguments: the first one is the keycode, which you can compare with a constant from [pyglet.window.key](https://pyglet.readthedocs.io/en/latest/modules/window_key.html#key-constants). The second one determines the pressed modifiers such as <kbd>Shift</kbd> or <kbd>Ctrl</kbd>.

This is a code snippet written in Python. It listens for a key press event in a Pyglet window. If the key pressed is the BACKSPACE key, it removes the last character from a label's text.

"If key_code equals pyglet.window.key.ENTER: print('Entered message:', label.text) window closes."

"On macOS, you may need to replace `BACKSPACE` with `DELETE`. {# XXX: is this true? #} (Or at home, study [the method](https://pyglet.readthedocs.io/en/latest/programming_guide/keyboard.html#motion-events) for doing it automatically and correctly.)"

"Kliknutí myši" translates to "Mouse click" in English.

"When handling the `on_mouse_press` event, you will receive information about the position of the click (the <var>x</var> and <var>y</var> coordinates) as well as information about the mouse button and modifier that was pressed."

"Like this, for example, the caption will move to the location of the click."

The code is written in Python, but the text is in Czech. Here's the translation:

```python
@window.event
def on_mouse_press(x, y, button, modifier):
    label.x = x
    label.y = y
```

Translation: When the mouse is clicked, the x and y coordinates of the cursor are assigned to the x and y properties of the label.

"Animace" in English means "animation".

"A slightly different type of event is the ticking of a clock: something that occurs regularly."

This is how animations are created, when something on the screen changes and is redrawn very often - for example, 60 times per second.

How to do it in Pyglet?
Once again, it is necessary to define a function, but this time it will not be enough to just use `window.event`.
Pyglet needs to know how often to call the function.
Tell it by calling `pyglet.clock.schedule_interval` with two arguments:
the name of the function and the time between each call - ¹/₆₀ seconds.
Write all of this again before the line `pyglet.app.run()`:

The code you provided is not in Czech language. It is written in Python programming language. The code defines a function called `tik` that takes a parameter `dt`. The function increments the x-coordinate of a label by 1.

"pyglet.clock.schedule_interval(tik, 1/60)" means "schedule the function 'tik' to be called every 1/60th of a second using the Pyglet clock module" in English.

"Pyglet now moves the text 1 pixel to the right every sixtieth of a second."

## The whole program

"In case you get lost or don't know where a particular piece of code belongs, I am providing a sample program for reference."

This is a Python code. Here's the translation:

```python
import pyglet
window = pyglet.window.Window()
label = pyglet.text.Label("Hello!", x=10, y=20)
```

The code imports the `pyglet` library, creates a window, and places a label with the text "Hello!" at coordinates (10, 20) within the window.

This is a code snippet written in Python programming language, not Czech language. 

It clears the window and draws a label on it when an event occurs.

This code snippet is written in Python programming language and it does not contain any Czech text to be translated. It is a code for an event that occurs when text is inputted into a window. Specifically, it adds the inputted text to the existing text in a label.

The translated text from Czech to English is:

@window.event
def on_key_press(key_code, modifier):
    if key_code == pyglet.window.key.BACKSPACE:
        label.text = label.text[:-1]

This appears to be a code snippet written in Python programming language. It is a function that listens for a key press event. If the key that is pressed is the backspace key, then the last character of a label's text is removed.

if key_code == pyglet.window.key.ENTER:
    print('Entered message:', label.text)
    window.close()

This is a snippet of code written in Python programming language, so it's not exactly Czech text. Here is the translation of the code:

When a mouse button is pressed on the window, the function "on_mouse_press" is triggered. The function takes four arguments: the x and y coordinates of the mouse pointer, the button that was pressed, and any modifier keys that were held down during the click. Inside the function, the x and y attributes of a label object are set to the values of the x and y arguments, respectively.

The provided text is not a complete sentence or phrase. It appears to be a code snippet written in Python programming language. However, I can provide a translation of the code:

"def tik(dt):" means that a function named "tik" is defined, which takes an argument "dt".

"label.x = label.x + 1" means that the value of the "x" attribute of an object named "label" is incremented by 1.

"pyglet.clock.schedule_interval(tik, 1/60)" translates to "schedule the function 'tik' to be called every 1/60th of a second using the Pyglet clock module."

"pyglet.app.run()" is the same in both Czech and English and is a command used in programming to start the pyglet application.

"So much for the training graphic application. What have you learned?"

* The function `pyglet.window.Window()` from the `pyglet` module creates a window.
* The decorator `@window.event` marks a function that Pyglet will call in response to a certain event: keyboard input (`on_text`), drawing (`on_draw`), key press (`on_key_press`), etc.
* By calling `pyglet.app.run()`, you tell Pyglet that everything is set up and it should start the application.
