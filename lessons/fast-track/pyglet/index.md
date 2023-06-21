> [warning]
> This is a machine-generated translation, meant to support the in-person workshop.

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

Your programming task now is to describe what other events are interesting and how to respond to them.

## Event management

The easiest event you can handle is typing on a keyboard.

Try putting the following code just above the line 'pyglet.app.run()' in the program:
```python
@window.event
def on_text(text):
    print(text)
```

What is this?
It is a function definition, but at the beginning it has a *decorator* - the line starting with an at sign.
The `window.event` decorator is a way to tell Pyglet to run this function when something interesting happens.

What's interesting? Pyglet finds out based on the function name: 'on_text' reacts to text. Whenever the user presses a key, Pyglet calls your function!

And what does your function do? It calls `print`. You already know that. The text entered will be displayed on the console from which you are running the program.

>[note]
>The `print()` function still outputs text to the same place as before.
>Just because a graphical window is open doesn't mean that everything will suddenly start writing to it.

## Drawing

How to write in a textbox? That is a bit more complicated than in a console. The text in the box can have different colors, sizes, fonts, and can be shifted or rotated in various ways.

All these font attributes need to be saved (along with the text itself) in the `Label` object (meaning 'label'). Try it - put the following code under the line with `window = `:
```python
label = pyglet.text.Label("Ahoj!", x=10, y=20)
```
In the variable `label` you will now have a label with the text "Hello" that belongs to position (10, 20) - 10 points from the right edge of the window and 20 points from the bottom.

> [note]
>  Other properties besides position are not specified here, so reasonable "default" values will be used: white color, small but readable font.

The caption, however, will not write itself. Similarly to calling `print` to display text in the console, responding to the *window drawing* event - `on_draw` - is necessary to draw text.

Put this code under the `on_text` function:
```python
@window.event
def on_draw():
    window.clear()
    label.draw()
```
This function is called by Pyglet whenever it is necessary to draw the content of the window. In animations (movies or games), this is often required 60 times per second ("60 FPS").

The function does two things:
* Clears the entire window (paints it black)
* Renders text.

In the window, you will now see a greeting!

Try changing the `on_text` function so that the entered text is displayed in a window instead of on the console. This is done by assigning the text to the *attribute* `label.text`.
```python
@window.event
def on_text(text):
    print('Starý text:', label.text)
    label.text = text
    print('Nový text:', label.text)
```

Can you add new text to the old one in this function so that the program works as a simple text editor?

{% filter solution %}
```python
@window.event
def on_text(text):
    label.text = label.text + text
```
{% endfilter %}

## Other events

What other events can be responded to? They are all described in the Pyglet documentation (https://pyglet.readthedocs.io/en/latest/modules/window.html#pyglet.window.Window.on_activate). Here are a few interesting ones.

### Key pressed

The keys that do not enter text (arrows, <kbd>Backspace</kbd> or <kbd>Enter</kbd>, etc.) can be recognized in the `on_key_press` event.

The function `on_key_press` has two arguments: the first one is the keycode, which you can compare with a constant from [pyglet.window.key](https://pyglet.readthedocs.io/en/latest/modules/window_key.html#key-constants). The second one determines the pressed modifiers such as <kbd>Shift</kbd> or <kbd>Ctrl</kbd>.
```python
@window.event
def on_key_press(key_code, modifier):
    if key_code == pyglet.window.key.BACKSPACE:
        label.text = label.text[:-1]

    if key_code == pyglet.window.key.ENTER:
        print('Zadaná zpráva:', label.text)
        window.close()
```

On macOS, you may need to replace `BACKSPACE` with `DELETE`.  (Or at home, study [the method](https://pyglet.readthedocs.io/en/latest/programming_guide/keyboard.html#motion-events) for doing it automatically and correctly.)

### Mouse click

When handling the `on_mouse_press` event, you will receive information about the position of the click (the <var>x</var> and <var>y</var> coordinates) as well as information about the mouse button and modifier that was pressed.

Like this, for example, the caption will move to the location of the click:

```python
@window.event
def on_mouse_press(x, y, button, modifier):
    label.x = x
    label.y = y
```

## Animation

A slightly different type of event is the ticking of a clock: something that occurs regularly.

This is how animations are created, when something on the screen changes and is redrawn very often - for example, 60 times per second.

How to do it in Pyglet?
Once again, it is necessary to define a function, but this time it will not be enough to just use `window.event`.
Pyglet needs to know how often to call the function.
Tell it by calling `pyglet.clock.schedule_interval` with two arguments:
the name of the function and the time between each call - ¹/₆₀ seconds.
Write all of this again before the line `pyglet.app.run()`:
```python
def tik(dt):
    label.x = label.x + 1

pyglet.clock.schedule_interval(tik, 1/60)
```
Pyglet now moves the text 1 pixel to the right every sixtieth of a second.

## The whole program

In case you get lost or don't know where a particular piece of code belongs, I am providing a sample program for reference.

```python
import pyglet
window = pyglet.window.Window()
label = pyglet.text.Label("Hello!", x=10, y=20)


@window.event
def on_draw():
    window.clear()
    label.draw()


@window.event
def on_text(text):
    label.text = label.text + text


@window.event
def on_key_press(key_code, modifier):
    if key_code == pyglet.window.key.BACKSPACE:
        label.text = label.text[:-1]

    if key_code == pyglet.window.key.ENTER:
        print('Zadaná zpráva:', label.text)
        window.close()


@window.event
def on_mouse_press(x, y, button, modifier):
    label.x = x
    label.y = y

def tik(dt):
    label.x = label.x + 1

pyglet.clock.schedule_interval(tik, 1/60)

pyglet.app.run()
```

So much for the training graphic application. What have you learned

* The function `pyglet.window.Window()` from the `pyglet` module creates a window.
* The decorator `@window.event` marks a function that Pyglet will call in response to a certain event: keyboard input (`on_text`), drawing (`on_draw`), key press (`on_key_press`), etc.
* By calling `pyglet.app.run()`, you tell Pyglet that everything is set up and it should start the application.
