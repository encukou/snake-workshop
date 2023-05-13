"Draw me a snake."

"Most video games have the entire game world stored as a bunch of numbers, texts, lists, and other data objects that describe everything in the game. This state changes over time, either automatically or based on the player's actions. And quite often - usually about sixty times per second - the state of the game is converted into an image that is shown to the player."

In order to display a snake, you will first need to define the game state - input what should be rendered.

"Try to think about what the state will contain: what does the computer have to remember about the game to be able to display the current state?"

It will need, for example, the current position of all parts of the snake: where does it start? Does it turn right or left? How long is it? On the other hand, you don't need to save the color of the snake state - every snake in this game will be the same.

"Have you ever wondered how to record the position of a snake using numbers, lists, and other basic data types?"

"Representation of a snake."

"Probably the easiest way to "memorize" a game snake on a computer is by using a list of coordinates."

Do you remember from school the Cartesian coordinates? It's that part of mathematics that may have seemed to have no practical application. However, for computer graphics, coordinates are like letters for the Czech language. Let's refresh our memory.

"Each point in the plane (even on the screen!) can be described by two numbers: the <var>x</var>-coordinate and the <var>y</var>-coordinate. The <var>x</var>-coordinate tells us how far to the left the point is from some origin, and the <var>y</var>-coordinate tells us how far up it is. We will choose the corner of the window in which our snake will crawl as that 'origin'."

Unlike in school geometry, the snake will crawl on a square grid. It's like on a chessboard - when a pawn goes to D5, D indicates how much it is to the left of the edge and 5 how much "up".

Here is a snake that starts at coordinates (1, 2) and has its head at (4, 5):

I'm sorry, but I cannot translate an image. However, the image appears to be a snake on a chessboard with coordinates.

You may notice that the mathematical notation of the coordinates - (1, 2) - corresponds to the way <var>n</var>-tuples are written in Python. This is not a coincidence! A pair of numbers is a perfect way to store the coordinates of a snake piece.

"The snake has more pieces, and otherwise long snakes will have a different number of them. It is good to use a list for this. A list of coordinates. And because the coordinates for us will be a pair of numbers, the list of coordinates will be a list of pairs of numbers."

"The snake from the picture above will look like this in Python:"

The Czech text is already in English and it is a Python code that defines a list of tuples. The list is named "had" and it contains tuples with two integers each.

"This is the representation of a snake - what needs to be known about a specific snake in terms of the game."

"To computers (and programmers?) this is enough. But let's try to display it in color, like an image, so that even the snake and the player of our future game understand it. But first, a little bit of staff culture."

"Profi software" translates to "Professional software" in English.

"Now, when you start writing professional software, two changes will come compared to how you wrote programs during warm-up."

"The first change will be English. For variable names, functions, and similar, a more universal language than Czech is almost always used so that anyone from around the world can participate in the project. Therefore, a variable with a snake will be named `snake`."

The English translation of the given Czech text is:

```python
snake = [(1, 2), (2, 2), (3, 2), (3, 3), (3, 4), (3, 5), (4, 5)]
``` 

There is no need for translation as the given text is a Python code and it is written in English. The code creates a list called "snake" that contains tuples representing the coordinates of the snake's body parts.

"I will continue to write comments in Czech for clarity. If you are proficient in English, feel free to translate it into English as well!"

"The second change will be the use of a custom class. At this moment, it doesn't make much sense: the snake game could be written using built-in classes (lists, numbers, etc.), but as we go further, you would find out that everything will be easier with a class. In a real project, you would then introduce the class: you would perform refactoring, an improvement of the project structure without changing its functionality."

"However, rewriting an existing project is quite prone to errors, especially if you don't fully understand the program. For this snake project, we will cheat a little and take advantage of the fact that the author of this text knows how the story ends. It will ultimately be easier with the class, trust me."

"The class will be named "GameState" and will contain the game state and methods for its functionality. The first method will be called "initialize" and will set the initial state of the game - that is, the position of the snake."

This is not Czech, but rather a piece of Python code defining a class called `GameState`. The `initialize` method of this class initializes a list called `snake` with tuples representing the coordinates of the snake's body.

# Creating a specific object
state = GameState()
state.initialize()

"Now you can work with the game state - for example, print a list of snake coordinates."

Notice that within the class `self` is used, but outside it's `state`. It should be the same throughout the rest of the program you write. Similarly, in the `Kotatko` class, you used `self` but outside it's `mourek` or `micka`.

"In the editor, open a new file, save it as 'snake.py' and write this program skeleton into it. We will further develop it."

Start the program (`cd` to the directory with the program; `python had.py`). Does it work? 
(It is quite important that it works - if you do not see a list output, do not continue reading and rather fix the program.)

[note]
Please use the name `GameState` for the class and name the attribute `snake` (and later others) according to the materials.
It will be useful for you.

## Logical and display coordinates

"We need to solve one basic problem when rendering a snake: converting *logical coordinates* to *screen coordinates*."

"The displays of computers work similarly to our coordinate "chessboard": they are square grids full of squares. Each square - *pixel* - can be set to a color. The main difference compared to a chessboard is that there are many, many more pixels on the screen."

If each "game" square was 10x10 pixels in size, then the snake head from the example, which has "game" coordinates (4, 5), will be rendered on the screen on the square that starts at (40, 50).

I'm sorry, but I cannot translate the text as there is no text provided in the question. The image shows a snake on a "chessboard" with screen coordinates.

"The tail with "game" (*logical*) coordinates (1, 2) is drawn on a square with coordinates (10, 20)."

## Playing Tic-Tac-Toe

To draw a snake, we will use the Pyglet window. Here is the basic structure of a Pyglet application, which you should already understand:

import pyglet

"window = pyglet.window.Window()" translates to English as "create a window using the Pyglet library."

The translation of the given Czech text to English is as follows:

`@window.event def on_draw(): window.clear()`

(Note: This appears to be a code snippet rather than a typical sentence or phrase, so the translation is simply a transcription of the text.)

"pyglet.app.run()" is already in English. It is a line of code written in the Python programming language using the Pyglet library, which runs the Pyglet application.

"Add the Pyglet application skeleton to your program. The import line conventionally belongs at the very beginning; add the rest *after* your existing code."

Sorry, that's not Czech. It's Python code. It imports the pyglet library.

class GameState:
    def initialize(self):
        self.snake = [(1, 2), (2, 2), (3, 2), (3, 3), (3, 4), (3, 5), (4, 5)]

Translation: This is a Python code that defines a class called GameState. The class has a method called "initialize" that initializes an attribute called "snake" with a list of tuples representing the coordinates of the snake's body parts on a game board.

state = GameState() 
state.initialize()

This is already in English and does not require translation.

window = pyglet.window.Window() translates to "create a window using the Pyglet library" in English.

This is a code snippet written in Python programming language, not Czech language. 

The code uses the Pygame library to create a window and define a function called "on_draw". This function is called whenever the window needs to be redrawn. 

The first line "@window.event" is a decorator used in Pygame library to define an event handler function. 

The second line "def on_draw():" defines the "on_draw" function. 

The third line "window.clear()" clears the window before redrawing it.

"pyglet.app.run()" is already in English. It is a line of code written in the Python programming language using the Pyglet library, which runs the Pyglet application.

Download the file [green.png]({{ static('green.png') }}) - a green square - and put it in the directory where you write your code.

"Add a line before `window = ...` that loads this image."

"green_image = pyglet.image.load('green.png')" translates to "Load the image file 'green.png' and assign it to the variable 'green_image' using the Pyglet library."

Then try adding drawing of an image at the coordinates (40, 50) with a size of 10 inside the `on_draw` function.

The code is not in Czech language, it is in Python programming language. 

This line of code is blitting (copying) an image called "green_image" onto another surface at position (40, 50) with a width of 10 and height of 10 pixels.

Run the program (`cd` to the directory with the program; `python snake.py`). Does it work?
(It is important again that it works - if you do not see a green square,
do not read further and rather fix the program.)

"As you can see, the square is quite small. We should use larger squares, let's say 64 pixels."

"That number is 'shot from the side'. We will use it several times in the program and you may want to modify it later. Therefore, we will save it as a *constant* (a variable that we will not change). Constants are traditionally named in capital letters and are written immediately after the `import` line (although it is not technically necessary). So, add the following line after the `import` line:"

The English translation of the given Czech text is: 

```python
TILE_SIZE = 64
``` 

It is the same in both languages and represents a variable named "TILE_SIZE" with a value of 64.

"...and in the call of 'green.blit' take into account the size of the square."

This code is not in Czech language, it is Python code. 

It means that an image called "green_image" is being displayed on the screen starting at the position of 4 times the size of a tile in the x-axis and 5 times the size of a tile in the y-axis. The displayed image has a width and height of one tile size.

"The code is a bit longer now, but when you want to change the size of the square, you just need to do it in one place."

"Did you succeed? Do you have a bigger square?
If not, try to go through the program line by line and check it.
Or compare it to the sample solution (which is a faster option, but you will learn less)."

Sorry, but the text you provided is not in Czech language. It's a Python code that imports the pyglet module.

"TILE_SIZE = 64" translates to "TILE_SIZE = 64" in English. The text is written in English and does not require translation.

class GameState:
    def initialize(self):
        self.snake = [(1, 2), (2, 2), (3, 2), (3, 3), (3, 4), (3, 5), (4, 5)]

Translation: The given text is a code snippet written in Python programming language. It defines a class named "GameState" with a method named "initialize". The method initializes an attribute named "snake" with a list of tuples containing coordinates of different parts of a snake.

state = GameState()
state.initialize()

This text is already in English and does not require translation. It is a code snippet in Python programming language that creates a new instance of the GameState class and initializes it.

"green_image = pyglet.image.load('green.png')" translates to English as "Load the image 'green.png' and assign it to the variable 'green_image' using Pyglet."

window = pyglet.window.Window() translates to "create a window using the pyglet library" in English.

This is not a complete sentence or phrase, but rather a code snippet written in Python programming language. It appears to be related to drawing and clearing a window, and blitting (copying) an image onto it at specific coordinates and dimensions.

"pyglet.app.run()" in Czech is the same as "pyglet.app.run()" in English. It is a line of code used in programming with the Pyglet library.

"Sázení hada" translates to "Planting a snake" in English.

"We don't want to display a square, but a snake. Actually, we will want to display the whole state of the game - the snake will be just the most important part. Therefore, create a new method called `draw` in the `GameState` class and for now, put the drawing of the square (calling `green_image.blit`) inside it."

The code you provided is not Czech text, it is Python code. 

However, the code initializes a `GameState` class and creates a `snake` attribute with a list of tuples representing the positions of the snake in a game.

The code is written in English, so there is no need to translate it. It is Python code that defines a function called "draw" which blits an image onto a surface at a specific location and size. It also defines an event handler for the "on_draw" event, which clears the window and calls the "draw" function.

"The modified program should do the same thing as before: draw a square. However, now it is drawn in the `draw` method, which has better access to the coordinates of the snake. Try to draw it!"

"Remember that you can 'iterate' through a list of pairs using a 'for' loop and 'unpacking' an <var>n</var>-tuple."

```
def draw(self):
    for x, y in self.snake:
        ...
        # (Put the code for drawing a square with coordinates x, y here)
```

This is a code snippet written in Python. The comments are in Czech and are instructing the programmer to write code that will draw a square with the given coordinates x and y.

"Can you handle it?
In the end, there should be a snake made up of squares visible - at least roughly."

I'm sorry, but I cannot translate an image. Please provide the text in written form.

"If it doesn't work, don't despair, check it again and ask for advice. Use the sample solution only as a last resort to move forward. Or for checking!"

Sorry, but the text you provided is not in Czech language. It is actually a Python code that imports the pyglet module.

"TILE_SIZE = 64" means the size of a tile is 64 in English.

class GameState:
    def initialize(self):
        self.snake = [(1, 2), (2, 2), (3, 2), (3, 3), (3, 4), (3, 5), (4, 5)]

Translation: The given text is a Python code that defines a class named GameState. The class has a method named initialize which initializes an attribute named snake with a list of tuples containing coordinates of positions in a game.

This is not Czech text, but rather a snippet of Python code. Here is a translation:

The code is defining a function called "draw" that takes no arguments. Within the function, there is a for loop that iterates over the coordinates of a list called "snake". On each iteration, the code calls a method called "blit" on an object called "green_image". This method takes four arguments: the x and y coordinates of the current snake segment multiplied by a constant called "TILE_SIZE", and the width and height of each segment (which are also both equal to "TILE_SIZE").

state = GameState()
state.initialize()

This is already in English. It is a simple code snippet that creates a new instance of the GameState class and initializes it.

"green_image = pyglet.image.load('green.png')" translates to "Load the image 'green.png' and assign it to the variable 'green_image' using Pyglet."

window = pyglet.window.Window() translates to "window equals pyglet dot window dot Window open parenthesis close parenthesis" in English.

The translated text from Czech to English is:

```
@window.event
def on_draw():
    window.clear()
    state.draw()
```

This is a piece of code written in Python programming language. It clears the window and draws the state.

"pyglet.app.run()" is a line of code written in the programming language Python. It is used to start the event loop of the Pyglet library, which is used for creating games and multimedia applications.

## Feeding

"To have something to do in the game, we will need food for the snake. Download the image [apple.png]({{ static('apple.png') }}) into the project directory and add coordinates for the food to the `initialize` method."

```python
self.food = [(2, 0), (5, 1), (1, 4)]
```

translates to:

```python
self.food = [(2, 0), (5, 1), (1, 4)]
```

There is no need for translation as the text is already in English.

"Then try to draw apples on these coordinates using the `draw` method."

You will need a few things for that:
* to load the `apple_image` image similarly to how you load the green square - you set the `green_image` variable
* to repeatedly draw the `apple_image` image similarly to how you draw green squares - by calling `green_image.blit` in a loop.

I'm sorry, but the text you provided is not in Czech. It appears to be Python code. Here's the translation of the code to English:

"Import the pyglet module."

"TILE_SIZE = 64" means the value of the constant "TILE_SIZE" is 64.

class GameState:
    def initialize(self):
        self.snake = [(1, 2), (2, 2), (3, 2), (3, 3), (3, 4), (3, 5), (4, 5)]
        self.food = [(2, 0), (5, 1), (1, 4)]

This is a code snippet written in Python. The code defines a class called GameState with a method called initialize. The method initializes two variables: snake and food. Snake is a list of tuples representing the coordinates of the snake's body. Food is a list of tuples representing the coordinates of the food that the snake can eat.

This is a code snippet written in Python. It is not Czech text. 

The code is defining a function called "draw" that loops through the coordinates of "snake" and "food" and displays them on the screen using images of a green block and an apple, respectively. The coordinates are multiplied by a constant "TILE_SIZE" to determine the size of the images.

state = GameState()
state.initialize()

This is already in English and does not need to be translated. It is a code snippet that creates a new instance of the GameState class and initializes it.

apple_image = pyglet.image.load('apple.png')
green_image = pyglet.image.load('green.png')

(There is no need to translate this text as it is already in English.)

window = pyglet.window.Window() translates to "create a window using the Pyglet library."

The English translation of the given Czech text is:

```
@window.event
def on_draw():
    window.clear()
    state.draw()
```

Note: This is a code snippet written in Python programming language. It is not a sentence or phrase that requires translation.

"pyglet.app.run()" is the code syntax in the Python programming language, which runs the Pyglet application.

"You may notice that the image in the game has slightly jagged edges. This is due to the way we render in Pyglet. A full explanation would not fit in this guide and requires a deeper understanding of computer graphics. Therefore, I will only provide the solution. In the `on_draw` function, right after `clear`, add the following three lines:"

```python
# Better rendering (a magical spell for us for now)
pyglet.gl.glEnable(pyglet.gl.GL_BLEND)
pyglet.gl.glBlendFunc(pyglet.gl.GL_SRC_ALPHA, pyglet.gl.GL_ONE_MINUS_SRC_ALPHA)
```

This code is written in Python and is enabling blending for better rendering. The `glEnable` function is used to enable blending, while the `glBlendFunc` function is used to specify how the blending should be done. In this case, it is using the source alpha and one minus source alpha to blend the colors.

Loading snake pieces

"Now that you know how to draw a snake from squares, we will try to make it more beautiful. Download the archive [snake-tiles.zip]({{ static('snake-tiles.zip') }}) and unpack it so that the `snake-tiles` directory with images is at the same level as the game program. The directory structure should look like this:"

I'm sorry, but I cannot translate the Czech text as it is contained in an image and I do not have access to the image. Could you please provide the text in a written format?

"There are many 'pieces' of a snake stored in the archive, which we can draw instead of green squares. The pieces look like this. Notice the names - each piece of the snake either connects two sides of the picture, or a side of the picture with the head or tail. Depending on where the snake crawls from and to on a particular square, the picture is named <code><var>from</var>-<var>to</var>.png</code>."

"Kousky hada" in English means "Pieces of snake".

[note]
What are those strange "snake eggs"?
<img src="{{ static('snake-tiles/end-end.png') }}" alt="" style="display:block; float:left; margin: 2px; border: 1px solid #ccc; border-radius: 1px;">
This is in case the snake is only one square long - and thus has its head and tail on the same square.
In the completed game, we will not get into such a state (the snake will start with a length of 2), but these images will be useful before we finish the game.

"Let's now *read* these pictures. We could do it gradually, for example like this:"

The code loads images of snake tiles including bottom-left, bottom-right, and bottom-top.

"But there are a lot of pictures, doing it this way would be tedious and you would probably forget some."

"So we will automatically load the pictures in a cycle and put them into a dictionary."

"The program will look like this:"

*Start with an empty dictionary.
*For each *beginning* (`bottom`, `end`, `left`, `right`, `top`):
  *For each *end* (`bottom`, `end`, `left`, `right`, `top`, `dead`, `tongue`):
    *We will load the image "<var>beginning</var>-<var>end</var>"; put this
      <var>key</var> into a variable
    *Load the image <var>key</var>.png
    *Save the image into the dictionary under <var>key</var>.

"Neboli, přeloženo do Pythonu" translates to "Or, translated into Python" in English.

This is a code snippet written in Python. Here's the translation of the code:

```
snake_tiles = {} # create an empty dictionary named snake_tiles
for start in ['bottom', 'end', 'left', 'right', 'top']: # iterate through the list of starting positions
    for end in ['bottom', 'end', 'left', 'right', 'top', 'dead', 'tongue']: # iterate through the list of ending positions
        key = start + '-' + end # concatenate the start and end positions with a hyphen
        image = pyglet.image.load('snake-tiles/' + key + '.png') # load the image file for the current position combination
        snake_tiles[key] = image # add the image to the dictionary with the key as the position combination
```

The code appears to be loading images of different snake tile combinations and storing them in a dictionary for later use.

"Put this code near the place where you load other images (`pyglet.image.load`). Then print the entire dictionary for checking: `print(snake_tiles)`. The output will look quite messy, but maybe you will recognize the dictionary in it - *{key: value, key: value, ...}*."

The text appears to be a dictionary with keys representing different parts of an image, with each key's value being an ImageData object of size 64x64. Without further context, it is difficult to provide a more specific translation.

## Caterpillar

"And now try to incorporate image loading into the snake program!"

"In the rendering function, use one of the images instead of `green_image`, for example `snake_tiles['end-end']`."

"Instead of squares, there will now be balls - instead of a snake, you will have a "caterpillar"."

The Czech text in the image is "Housenka" which means "Caterpillar" in English.

Sorry, but the text you provided is not Czech. It appears to be Python code. Specifically, it is importing the "pyglet" module.

TILE_SIZE = 64 means "the size of a tile is 64".

class GameState:
    def initialize(self):
        self.snake = [(1, 2), (2, 2), (3, 2), (3, 3), (3, 4), (3, 5), (4, 5)]
        self.food = [(2, 0), (5, 1), (1, 4)]

This is a code snippet written in Python. It defines a class called "GameState" and a method called "initialize". In this method, the class initializes two variables: "snake" and "food". "snake" is a list of tuples that represent the positions of the snake's body parts, and "food" is a list of tuples that represent the positions of the food on the game board.

This is Python code, not Czech text. 

It appears to be a method called "draw" that is part of a class. 

The first for loop iterates over the coordinates of the "snake" and uses them to blit an image of a snake tile onto the screen. 

The second for loop iterates over the coordinates of the "food" and uses them to blit an image of an apple onto the screen.

state = GameState()
state.initialize()

This is already in English and does not require translation. It is a piece of code written in Python programming language that creates a new object called "state" from the class "GameState" and then initializes it using the method "initialize()".

The code loads two images, 'apple.png' and 'green.png', using the Pyglet library. It then creates an empty dictionary called 'snake_tiles'. The code then loops through two lists, 'start' and 'end', and concatenates each element of the two lists to create a 'key' variable. The code then loads an image using the Pyglet library and assigns it to a variable called 'image'. Finally, the code adds the image to the 'snake_tiles' dictionary with the 'key' as the key.

window = pyglet.window.Window() translates to "window equals pyglet dot window dot Window open parenthesis close parenthesis" in English.

The English translation of the Czech text is as follows:

@window.event
def on_draw():
    window.clear()
    # Better rendering (magical incantation for us so far)
    pyglet.gl.glEnable(pyglet.gl.GL_BLEND)
    pyglet.gl.glBlendFunc(pyglet.gl.GL_SRC_ALPHA, pyglet.gl.GL_ONE_MINUS_SRC_ALPHA)

"state.draw()" is already in English. It is a line of code that instructs a computer program to draw or display the current state of an object or system.

"pyglet.app.run()" is already in English. It is a line of code used in the Python programming language to run a Pyglet application.

"How to choose squares?
Instead of having the same piece of fabric everywhere,
we will always want to choose the right one."

"How to do it? By what criteria to choose it?"

"Images with pieces of a snake are named <code><var>from</var>-<var>to</var></code>. This is not a coincidence - it shows what you need to know to be able to choose the right piece."

"When you have a snake according to the following picture, the piece that the snake is crawling on from the left up - that is `snake_tiles['left-top']` - belongs to the square (3, 2)."

The text is not provided. Please provide the Czech text that needs to be translated.

"For each field of the snake, you will need to know:
* The <var>x</var> and <var>y</var> coordinates of the field
* The direction in which the snake moves - towards the *previous* and *next* field."

"The values can then be entered into the program something like this:"

```
for ... in ...:   # What will the loop iterate over? The self.snake itself?
    x = ...
    y = ...
    before = ...  # Direction towards the previous field ('left' or 'top' or ...)
    after = ...   # Direction towards the next field

key = before + '-' + after  # name of the tile image
snake_tiles[key].blit(x * TILE_SIZE, y * TILE_SIZE,
                      width=TILE_SIZE, height=TILE_SIZE) 

(Note: This is a code snippet, not a complete sentence in Czech.)

"You need to fill in those missing `...`!"

This is a **difficult task**. Even though you now theoretically know all the necessary information and tools for it, it is necessary to put them together in the right way. This putting together, *algorithm design*, is the most complex programming discipline.

"Try to think about it, let it settle in your head, maybe overnight. Go back to the materials from previous lessons (especially the introduction to Python), try and discover... And in time, you will come up with a solution. Your reward for solving it will be a snake instead of a caterpillar."

"Before you figure it out, the rest of the program won't run away from you. The caterpillar is just as playable as the snake, it just looks different. Feel free to switch to [writing game logic](../logic) with the caterpillar."

"Or do you [let yourself be submitted](../tile-selection)?"