# Game logic

"You can already draw a snake from a list of coordinates. But the snake video game won't just be a "picture". The list will change and the snake will move!"

# Saving revisions

XXX - I'm not able to finish it, I apologize.

"Rozhýbejme hada" translates to "Let's move the snake" in English.

"Your program now, I hope, looks something like this:"

import pyglet

"TILE_SIZE = 64" means "the size of each tile is 64" in English.

class GameState:
    def initialize(self):
        self.snake = [(1, 2), (2, 2), (3, 2), (3, 3), (3, 4), (3, 5), (4, 5)]
        self.food = [(2, 0), (5, 1), (1, 4)]

The given text is a piece of code written in Python programming language. It defines a class called 'GameState' which has a method called 'initialize'. This method initializes two variables - 'snake' and 'food'. 'snake' is a list of tuples representing the coordinates of the snake's body parts, and 'food' is a list of tuples representing the coordinates of the food items on the game board.

This is a code written in Python. Here is the translation:

```
def draw(self):
    for x, y in self.snake:
        before = 'end'     # (Here might be some more complex tile selection)
        after = 'end'      
        key = before + '-' + after
        snake_tiles[key].blit(x * TILE_SIZE, y * TILE_SIZE,
                              width=TILE_SIZE, height=TILE_SIZE)
    for x, y in self.food:
        apple_image.blit(x * TILE_SIZE, y * TILE_SIZE,
                         width=TILE_SIZE, height=TILE_SIZE)
```

The code is likely a part of a game development project. It includes a function called `draw` which is responsible for rendering the game objects on the screen. The function iterates through the `snake` list and selects the appropriate tile image based on the `before` and `after` variables. It then uses the `blit` method to draw the tile at the specified position. Similarly, the function also draws the `food` objects on the screen using the `blit` method and the `apple_image` variable.

state = GameState()
state.initialize()

This text is already in English and does not need to be translated. It is a code snippet written in Python programming language. It creates a new object called "state" of the class "GameState" and initializes it using the "initialize" method.

The code is written in Python programming language. Here's the translation of the code:

```
apple_image = pyglet.image.load('apple.png')
green_image = pyglet.image.load('green.png')
snake_tiles = {}

# Loop through all possible combinations of start and end positions
for start in ['bottom', 'end', 'left', 'right', 'top']:
    for end in ['bottom', 'end', 'left', 'right', 'top', 'dead', 'tongue']:
        # Create a unique key for each combination
        key = start + '-' + end
        # Load the corresponding image and add it to the dictionary
        image = pyglet.image.load('snake-tiles/' + key + '.png')
        snake_tiles[key] = image
```

The code loads two images (`apple.png` and `green.png`) and creates a dictionary (`snake_tiles`) containing all possible combinations of start and end positions for a snake. It then loads the corresponding image for each combination and adds it to the dictionary with the unique key.

window = pyglet.window.Window() means "create a window using the Pyglet library."

The translated text is:

```
@window.event
def on_draw():
    window.clear()
    # Better rendering (magical incantation for us so far)
    pyglet.gl.glEnable(pyglet.gl.GL_BLEND)
    pyglet.gl.glBlendFunc(pyglet.gl.GL_SRC_ALPHA, pyglet.gl.GL_ONE_MINUS_SRC_ALPHA)
```

Note: This is a code snippet written in Czech that is related to graphics rendering using the Pyglet library. The comment in the code explains that the code enables better rendering using a specific blending function.

"state.draw()" remains the same in English as it is a line of code used in programming languages. It is not a phrase that requires translation.

"pyglet.app.run()" is already in English. It is a line of code written in the Python programming language that runs the Pyglet application.

"Try now to add a method to the `GameState` class that adds an additional square to the snake."

This is a code snippet written in Python. It defines a method called `move` that takes a parameter `dt`. The code inside the method updates the position of a snake in a game by adding a new head to the snake. 

The first line of the code extracts the x and y coordinates of the current head of the snake. The next two lines update the x and y coordinates of the new head by adding 1 to the x coordinate. Finally, the new head is added to the snake.

And just above the line `pyglet.app.run`, tell Pyglet to call this function every sixteenth of a second.

The code is in Python and it schedules a function called `move()` from an object called `state` to be executed every 1/6th of a second using the Pyglet library.

"Does it work? 
So add `del snake[0]` to that method so that the snake does not grow infinitely. 
Do you know what this command does? If not, take a look at the notes on lists again!"

Can you modify the function to make the snake crawl upwards? Or downwards?

If yes, congratulations! The remaining part is to control the direction of the snake using the arrow keys on the keyboard, and most of the game will be done!

"For inspection, I am attaching my solution:"

"In the `move` method, it is necessary to set the variables `new_x` and `new_y` differently:"

"For upward movement:"

The English translation of the given Czech code is:

```python
new_x = old_x
new_y = old_y + 1
``` 

There is no translation required as the code is written in English.

"And down:"

```python
new_x = old_x
new_y = old_y - 1
```

This code sets the value of `new_x` to be the same as `old_x`, and sets the value of `new_y` to be one less than the value of `old_y`.

Control

"Now to the promised control. Specifically, first to the direction changes."

"The snake in the game crawls in the same direction until the player presses a key and changes the direction."

"To make sure that the snake "remembers" where it is crawling, it is necessary to have a direction as part of the game state. Let's save it in an attribute called `snake_direction`."

"What exactly should be stored there? 
How to represent direction in Python - using numbers, tuples, and so on?"

I'm sorry, but I cannot translate an image. Please provide the text in written form.

"The most convenient solution is probably to store how many squares the snake should move, separately in the <var>x</var> and <var>y</var> directions. So, as a pair:"

(`1, 0`) = right (by one square in the positive <var>x</var> direction; do not move in the <var>y</var> direction)
(`-1, 0`) = left (by one square in the negative <var>x</var> direction)
(`0, 1`) = up (+<var>y</var>, but do not move in the <var>x</var> direction)
(`0, -1`) = down (-<var>y</var>)

"Add the new attribute to the `initialize` method."

```python
self.snake_direction = 0, 1
```
translates to:
"Set the direction of the snake to move down (in the y-axis) in the coordinate system."

"In the `move` method, change the setting of `new_x` and `new_y` according to the new attribute."

This code is written in Python. Here is the translation of the code:

```
dir_x, dir_y = self.snake_direction
new_x = old_x + dir_x
new_y = old_y + dir_y
```

This code assigns the values of `self.snake_direction` to `dir_x` and `dir_y`. Then, it calculates the new values of `x` and `y` by adding `dir_x` and `dir_y` respectively to the old values of `x` and `y`.

"You can now change the direction of the snake by changing the `snake_direction` in the `initialize` function. Does it work? (If not, fix it - and if you can't, call someone for help!)"

"Now, the only thing left is to change the `snake_direction` attribute when the user presses something on the keyboard. That is already the domain of Pyglet."

"It is necessary to add a function that responds to a key press. For Pyglet to find and be able to call this function, it must be named 'on_key_press', it must have the decorator '@window.event', and it must take two parameters: the number of the key that was pressed and information about modifiers such as <kbd>Shift</kbd> or <kbd>Ctrl</kbd>."

This is a code snippet written in Python programming language, which does not contain any Czech text. It is a decorator that registers an event handler function for a key press event in a graphical user interface window. The function is not provided in the code snippet.

"The first parameter is important. It sets the current direction of the snake. The key codes are defined in the module [`pyglet.window.key`][key-constants] as constants with names like `LEFT`, `ENTER`, `Q`, or `AMPERSAND`. We will use arrows - `LEFT`, `RIGHT`, `UP`, and `DOWN`."

The given code is written in Python programming language. It listens to the keyboard events and sets the direction of the snake accordingly. 

Translated text: 

```python
@window.event
def on_key_press(key_code, modifier):
    if key_code == pyglet.window.key.LEFT:
        state.snake_direction = -1, 0
    if key_code == pyglet.window.key.RIGHT:
        state.snake_direction = 1, 0
    if key_code == pyglet.window.key.DOWN:
        state.snake_direction = 0, -1
    if key_code == pyglet.window.key.UP:
        state.snake_direction = 0, 1
```

This code listens to the keyboard events and sets the direction of the snake based on the key pressed. If the LEFT arrow key is pressed, the snake moves to the left. If the RIGHT arrow key is pressed, the snake moves to the right. If the DOWN arrow key is pressed, the snake moves downwards. If the UP arrow key is pressed, the snake moves upwards.

"The second parameter will not be needed in our game, but it must be in the function header."

[key-constants]: https://pyglet.readthedocs.io/en/pyglet-1.3-maintenance/modules/window_key.html#key-constants

This is already in English. It appears to be a hyperlink to a section of the Pyglet documentation related to key constants in the window module.

The function `on_key_press` needs to be placed somewhere after setting up the `window` (so that `window.event` is available) and before `pyglet.app.run()` (because setting up controls after the game has started is unnecessary). The best way is to place it next to another function with the `@window.event` decorator, so that they are nicely together.

Does it work?
Can you control the direction of the snake?
That's great!
However, during testing, you will definitely come across a few things that need to be finished.

* The snake shouldn't have the opportunity to climb out of the window.
* The snake should eat food and grow.
* The game should end when the snake hits itself or the edge of the window.

"Let's solve them one by one."

"So far so good, but now we will hit a bump."

"Snake" games like ours have two variations: either there is a "wall" around the playground and the player loses when hitting the edge, or the playground is "endless" - the snake crawls through the edge and appears on the other side. We will program the first variation - the wall.

To find out if the snake "crawled out" of the left edge of the window, it is necessary to check if the <var>x</var>-coordinate of the head is less than 0. This should be done immediately after obtaining the new coordinates of the head - specifically, right after the line `new_head = new_x, new_y` in the `move` method.

"And what to do in such a crash?
To start with, the easiest thing to do is to end the game.
For this, Python has the `exit()` function, which works similarly to when an error occurs in the program.
Instead of a long error message, it shows the given text."

"The end of the program is not a very pleasant way to tell the player that they lost. However, we will change this part soon, so for now this simple way will suffice."

The given text is a code snippet written in Python. It defines a function called `move` that takes an argument `self`. Here's the translation of the code into English:

```
def move(self):
    old_x, old_y = self.snake[-1]  # Get the current position of the snake's head
    dir_x, dir_y = self.snake_direction  # Get the direction in which the snake is moving
    new_x = old_x + dir_x  # Calculate the new x-coordinate of the snake's head
    new_y = old_y + dir_y  # Calculate the new y-coordinate of the snake's head
    new_head = new_x, new_y  # Create a tuple with the new coordinates as the new head of the snake
```

This code snippet is a part of a larger program that simulates the game of Snake. The `move` function is responsible for updating the position of the snake's head based on the current direction of movement.

# New code - checking if the player has gone out of the playing area
        if new_x < 0:
            exit('GAME OVER')

"self.snake.append(new_head) del self.snake[0]" is already in English. It is a code snippet written in Python programming language.

"I believe that you can manage to do the same check for climbing out from the bottom edge."

But how to treat the remaining edges - the right and the top ones? It is necessary to know the size of the window. And Pyglet knows it; the class with state should not have access to the window!

"The behavior of the game depends on the size of the game board. This information will therefore have to be part of the state. For starters, set a size - say 10x10 - in `initialize`."

This is not Czech, it is Python code. The code sets the width and height of an object to 10.

"And then arrange for the game to end after hitting an invisible wall around the large 10x10 square field. Test all variants thoroughly - the northern, southern, eastern and western wall. The snake is virtual, so you don't have to worry about creating a bump on it by hitting the walls."

The code you provided is written in Python and it describes a function called "move" that is part of a class. The function takes no arguments and performs the following steps:
1. It assigns the values of the last element of a list called "snake" to the variables "old_x" and "old_y".
2. It assigns the values of another list called "snake_direction" to the variables "dir_x" and "dir_y".
3. It calculates the new position of the snake's head by adding the values of "old_x" and "dir_x" and assigning the result to "new_x".
4. It calculates the new position of the snake's head by adding the values of "old_y" and "dir_y" and assigning the result to "new_y".

# Checking if the player has gone outside of the game area
if new_x < 0:
    exit('GAME OVER')
if new_y < 0:
    exit('GAME OVER')
if new_x >= self.width:
    exit('GAME OVER')
if new_y >= self.height:
    exit('GAME OVER')

```
new_head = new_x, new_y
self.snake.append(new_head)
del self.snake[0]
```

This is a code snippet written in Python programming language. It does not need to be translated as it consists of variable assignments and list manipulation that are universal in programming and not specific to any language.

"And then in the file with the game, right after you create the state (`state = GameState()`) and the window, set the *actual* size. Use integer division so that the number of tiles is in whole numbers."

This code snippet sets the `width` and `height` properties of an object called `state` to the integer division of the `width` and `height` of a `window` object by a constant value called `TILE_SIZE`.

## Feeding

"So. The snake is in the cage, it can't climb out anymore. What's next?"

"Now you have to take care of the snake: feed it regularly. But before that, it is necessary to teach it how to eat at all - it is not yet accustomed to our food. When you manage to do that, it will grow like crazy!"

Specifically, you must ensure that when the snake crawls onto a square with food, the food disappears. To achieve this, you can use:
* the `in` operator, which determines whether something (such as coordinates) is in a list (such as a list of food coordinates), and
* the `remove` method, which removes a specified element from a list (based on the *value* of the element - as opposed to `del`, which removes based on position).

"To check the climb out of the playing area, you need to enter a code that does the following:" (Note: The rest of the Czech text is missing, so I cannot provide a full translation.)

"If the new position of the head is in the list of food coordinates:
Remove this position from the list of food coordinates."

"Can you write it?"

The given text is not in Czech language, it appears to be a code snippet written in Python programming language. The code checks if a variable named `new_head` is present in a list called `self.food` and if it is, then it removes that element from the list.

"Try to see if it works. The snake should eat food."

"But there is still a need to arrange so that after each bite it grows a bit. But how? Which direction should it grow?"

"Here it is good to look at the existing code and realize what it does."

"Our snake crawls in such a way that it first grows in the front (using `append`) and then shrinks in the back (using `del self.snake[0]`). "

So in order for the snake to grow after eating, it is enough to *skip* the shrinking! And by *skip* I mean to condition it using `if`. The logic of eating and shrinking of the snake will be:

"When a snake eats food, the food disappears. The snake does not get smaller. Otherwise (when the snake does not eat food), the snake will shrink (and thus not grow)."

"Not translated into Python:"

This is a code snippet written in Python. It does not contain Czech text. 

The code checks if a variable called `new_head` is in a list called `self.food`. If it is, then the code removes `new_head` from the list. If `new_head` is not in `self.food`, then the code deletes the first element of a list called `self.snake`.

"For those who are beginning to get lost, I will provide the entire 'move' method. But woe to those who copy the code without trying to understand it!"

The given text is not in Czech language. It is a code snippet written in Python. Here is the translation of the code:

```
def move(self):
    old_x, old_y = self.snake[-1]
    dir_x, dir_y = self.snake_direction
    new_x = old_x + dir_x
    new_y = old_y + dir_y
    new_head = new_x, new_y
```

This code defines a method called `move` that updates the position of a snake in a game. It gets the current position of the snake's head (`old_x` and `old_y`) and the direction in which the snake is moving (`dir_x` and `dir_y`). It then calculates the new position of the snake's head by adding the direction to the current position (`new_x` and `new_y`). Finally, it stores the new head position in a variable called `new_head`.

# Checking if the player is out of the game area
        if new_x < 0:
            exit('GAME OVER')
        if new_y < 0:
            exit('GAME OVER')
        if new_x >= self.width:
            exit('GAME OVER')
        if new_y >= self.height:
            exit('GAME OVER')

The given text appears to be a code snippet written in Python programming language. Here is the translation of the code comments and statements from Czech to English:

```
self.snake.append(new_head)
        if new_head in self.food:
            self.food.remove(new_head)
        else:
            del self.snake[0]
```

Translation:
```
Add the new head to the snake.
If the new head is in the food, remove it from the food list.
Otherwise, delete the first element of the snake (i.e., the tail).
```

"Nové jídlo" translates to "New food" in English.

"When a snake already knows how to eat, it is necessary to provide it with a regular supply of food. Ideally, each eaten meal should be replaced with a new one."

"Add the following new method to the `GameState` class, which is able to add food:"

The code is written in English, not Czech. It defines a method called `add_food` that adds a new position to a list called `food`. The position is defined by two variables `x` and `y`, which are both initialized to 0. These variables are then combined into a tuple called `position`, which is added to the `food` list.

"Then call this method - find the code in the program that is executed when a new food needs to be added, and add the following line there:"

This is not a Czech text. It is a line of code written in Python programming language. It adds a new food item to an object or a list.

This method adds food at position (0, 0), which is always in the same corner. It's good just for... well, for verifying that the food is really being added to the list. It would be nice if the new food always appeared somewhere else, at a random location. You can use the `random.randrange` function for that. Remember that calling `randrange(N)` returns a random integer from 0 to <var>N</var> - 1.

"What range of numbers do you need for snake food?"

"When you realize it, try adding chance to the program: the food should appear on a *completely random* square on the game board."

"Don't forget about `import random` - it belongs at the very beginning of the file. But make any further changes only in the `add_food` method."

The given text is a code snippet written in Python programming language and it does not contain any Czech text to be translated.

"When you test it, you will probably find out that a *completely random* tile is not ideal. Sometimes food appears on a tile with a snake, or even on another piece of food. It is therefore good to check this situation, and when the choice falls on a full tile, do not add food."

The code is written in Python. The translation of the Czech text is:

```If the position is not in the list of the snake's positions and the position is not in the list of food positions, then add the position to the list of food positions.```

"When you try *this*, you will find out that sometimes no new food is added at all. That's not a good option either - the snake would still be hungry. What to do about it?"

"Surprisingly good (although not *completely* ideal) solution is to try selecting the square several times. When an empty square falls, put the food there; when a full square falls, just try again."

However, it is necessary to limit the number of attempts so that in a situation where the field is *completely* full, the computer does not keep selecting endlessly. Let's say that if we don't manage to select an empty field after 100 attempts, we give up. There is probably enough food already.

The method `add_food` after all modifications will look like this:

The code is written in Python. Here's the translation of the Czech comments:

```python
def add_food(self):
    for try_number in range(100):
        x = random.randrange(self.width)
        y = random.randrange(self.height)
        position = x, y
        if (position not in self.snake) and (position not in self.food):
            self.food.append(position)
            # End of the function ("jumps out" of the for loop as well)
            return
```

The function `add_food` generates random coordinates (`x` and `y`) within the boundaries of the game board (`self.width` and `self.height`). It checks if the generated position is not already occupied by the snake or by another food item. If the position is valid, it adds it to the list of food items (`self.food`). The function tries to generate a valid position for up to 100 times. If it fails to find a valid position, it simply ends the function.

"If it works for you, also arrange for food to be at random positions at the start of the game."

In the `initialize` method, instead of setting `self.food` to a list with food positions, you can write:
```python
        self.food = []
        self.add_food()
        self.add_food()
```
Then at the beginning of the game, two random foods will be waiting for the snake.

"Konec" in English means "End".

"The snake can now grow to enormous dimensions - and the only way to lose is by hitting the wall. Make sure the game ends even if it hits itself."

"How to do it?
For the `move` method, in addition to checking if the player has climbed out of the playing area, provide code that will do the following:"

"If the coordinates of the new head are already part of the snake: End the game (similarly to hitting the wall)."

"Can you translate it into Python?"

# Checking if the snake has collided
if new_head in self.snake:
    exit('GAME OVER')

"Hotovo!" translates to "Done!" in English.

"Pauza" in English means "break."

However, it is not good to end the whole program and close the window at the end of the game.

"It's better to "pause" the game and show the player the situation in which the unfortunate snake ended up, so that they can learn from it for next time."

To make it possible, we will add another attribute to the game: 'alive'. It will be set to 'True' as long as the snake is alive. When the snake hits something, 'alive' will be set to 'False', and from then on the snake will not move anymore. It is also good to show graphically that the snake is not doing well - the player will then be more likely to feel guilty.

"Try to think where in the code the following pieces of code, which implement the game loss, belong."

# Initial setting of the attribute
self.alive = True

# Stopping the snake
self.alive = False

```
# Preventing movement
if not self.alive:
    return
```

This is a code snippet written in Python. The comments are in Czech and the code is checking if an object is alive before allowing it to move. If the object is not alive, the function will return and the movement will be prevented.

```python
# Graphic indication
if after == 'end' and not state.alive:
    after = 'dead'
```

This is a code snippet in Python that involves a graphic indication. It checks if a certain condition is met (`after == 'end' and not state.alive`) and if so, it changes the value of the variable `after` to `'dead'`.

* "Initial attribute setting" to the `initialize` method.
* "Stopping the snake" instead of *all* occurrences of `raise("Game Over")`.
* "Preventing movement" at the very beginning of the `move` method (the `return` statement will immediately terminate the execution of the method).
* "Graphic indication" after the section for selecting the image for the snake piece.

"And that's it?"

"Congratulations, you have a functional and playable game! I hope you are proud of yourself!"

"Have something sweet, you deserve it."

I'm sorry, but there is no Czech text provided for me to translate. Please provide the text you want me to translate.

Here is my solution. It may differ quite a bit from yours at this time - that is completely normal.

"Don't look here until you program the snake {{gnd('yourself', 'yourself')}}. A person learns from mistakes and constant testing - and especially a programmer. Learning from already solved problems is harder."

I am sorry, but there is no Czech text provided for me to translate. Please provide the text and I will be happy to assist you.

I'm sorry, but this is not Czech text. It is Python code.

"TILE_SIZE = 64" is already in English. It means that the size of each tile is 64 units.

class GameState:
    def initialize(self):
        self.snake = [(0, 0), (1, 0)]
        self.snake_direction = 0, 1
        self.width = 10
        self.height = 10
        self.food = []
        self.add_food()
        self.add_food()
        self.alive = True

This is a code written in Python programming language. It initializes a game state with a snake starting at (0,0) and (1,0) positions, moving in the direction of (0,1). The game board has a width and height of 10 units. The game also has two food items that are randomly added to the board. Finally, the game state is set to "alive".

def draw(self):
        for x, y in self.snake:
            before = 'end'     # (Here, there may be some more complicated selection of the field)
            after = 'end'      
            if after == 'end' and not state.alive:
                after = 'dead'
            key = before + '-' + after
            snake_tiles[key].blit(x * TILE_SIZE, y * TILE_SIZE,
                                  width=TILE_SIZE, height=TILE_SIZE)
        for x, y in self.food:
            apple_image.blit(
                x * TILE_SIZE, y * TILE_SIZE, width=TILE_SIZE, height=TILE_SIZE)

The text is a code written in Python language. The code seems to be related to a game where a snake is moving around and eating apples. The "draw" function is responsible for drawing the snake and the apples on the screen. The code is written in a class and the function is a method of that class.

The English translation of the given Czech text is:

def move(self):
    if not self.alive:
        return

old_x, old_y = self.snake[-1]
dir_x, dir_y = self.snake_direction
new_x = old_x + dir_x
new_y = old_y + dir_y

Translated to English, the text means:

"old_x, old_y = self.snake[-1]
dir_x, dir_y = self.snake_direction
new_x = old_x + dir_x
new_y = old_y + dir_y"

This appears to be a block of code written in Python, which is a programming language. It is not a sentence or phrase that can be directly translated, but it appears to involve assigning values to variables and performing mathematical operations.

# Checking if the player has gone off the playing area
        if new_x < 0:
            self.alive = False
        if new_y < 0:
            self.alive = False
        if new_x >= self.width:
            self.alive = False
        if new_y >= self.height:
            self.alive = False

Translation: These lines of code check if the player has moved off the playing area. If the new position is less than 0 or greater than or equal to the width or height of the playing area, the player's "alive" status is set to False.

new_head = new_x, new_y
if new_head in self.snake:
    self.alive = False
self.snake.append(new_head)

Translation: 

The code creates a new variable called "new_head" which stores the values of "new_x" and "new_y". If the new_head position is already in the list of positions occupied by the snake, then the "alive" variable is set to False. Finally, the new_head position is added to the list of positions occupied by the snake.

"If the 'new_head' is in the 'food' list, remove it from the list and add new food. Otherwise, delete the first element of the 'snake' list."

The given text is a code snippet written in Python programming language. Here's the translation of the code:

```
def add_food(self):
    for try_number in range(100):
        x = random.randrange(self.width)
        y = random.randrange(self.height)
        position = x, y
        if (position not in self.snake) and (position not in self.food):
            self.food.append(position)
            return
```

The code defines a function called `add_food` that takes in an instance of a class as an argument. The function generates 100 random positions within the specified width and height range. It checks if the generated position is not already occupied by the snake or food. If the position is empty, it adds the position to the list of food and returns.

The code reads: 

"apple_image = pyglet.image.load('apple.png')
snake_tiles = {}
for start in ['bottom', 'end', 'left', 'right', 'top']:
    for end in ['bottom', 'end', 'left', 'right', 'top', 'dead', 'tongue']:
        key = start + '-' + end
        image = pyglet.image.load('snake-tiles/' + key + '.png')
        snake_tiles[key] = image"

This is a Python code that loads an image of an apple and a set of images for a snake game. The set of images is stored in a dictionary called "snake_tiles", where each image is identified by a key that is a combination of two strings (start and end), separated by a hyphen. The images are loaded from files located in a folder called "snake-tiles".

window = pyglet.window.Window() translates to "window equals a pyglet window object" in English.

state = GameState()
state.initialize()
state.width = window.width // TILE_SIZE
state.height = window.height // TILE_SIZE

Translation: 

The code creates a new game state object and initializes it. It then sets the width and height of the game state based on the size of the window divided by the size of each tile.

The given text appears to be a code snippet written in Python programming language. Here is the translation of the code into English:

The code defines an event handler function called "on_draw" that is triggered when a drawing event occurs in a window. The function clears the window and enables blending of colors using alpha channel transparency. The specific blending function used is "GL_SRC_ALPHA" and "GL_ONE_MINUS_SRC_ALPHA". Finally, the function calls another function called "state.draw()" to draw the graphics on the window.

This is a code snippet written in Python. It sets the direction of a snake in a game based on the key pressed by the user. If the left arrow key is pressed, the snake moves left. If the right arrow key is pressed, the snake moves right. If the down arrow key is pressed, the snake moves down. If the up arrow key is pressed, the snake moves up.

The Czech text is actually a piece of code written in Python programming language, which means it cannot be directly translated to English as it does not contain any words in the natural language. However, I can explain what the code does:

The code defines a function called "move" that takes a parameter "dt". Inside the function, there is a method call "state.move()". This suggests that there is an object called "state" with a method called "move()", which will be executed when the "move()" function is called. 

Without more context, it is difficult to say what the "move()" function is supposed to do or what the "state" object represents.

"pyglet.clock.schedule_interval(move, 1/6)" means "schedule the function 'move' to be called repeatedly at intervals of 1/6 seconds using the pyglet clock module."

"pyglet.app.run()" remains the same in both Czech and English. It is a line of code in the Pyglet library used for running the application.

"What's next?"

"Can you find any other improvements that could be made?"

"Try the following extensions, for example. They are roughly sorted by complexity:"

"Improve the controls (and gameplay!) according to the [manual](../handling)."

"Every 30 seconds of the game, new food will be added automatically, so there will be more of them on the playing field."

"When the snake crawls out of the window, instead of the end of the game, it appears on the other side. (See [instructions](../toroid).)"

"There will be two snakes; the second one is controlled by the keys <kbd>W</kbd> <kbd>A</kbd> <kbd>S</kbd> <kbd>D</kbd>. (It's best to create a new class, `Snake`, and move all the snake's state from `GameState` to it. Then keep a list of snakes in `GameState`. This change needs to be adapted throughout the entire program.)"

"The game will gradually speed up. (It is best to modify the 'move' function so that it automatically plans when to call itself. The use of 'schedule_interval' will no longer be necessary.)"