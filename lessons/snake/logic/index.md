# Game logic

You can already draw a snake from a list of coordinates. But the snake video game won't just be a "picture". The list will change and the snake will move!

# Let's move the snake

Your program now, I hope, looks something like this:
```python
import pyglet

TILE_SIZE = 64

class GameState:
    def initialize(self):
        self.snake = [(1, 2), (2, 2), (3, 2), (3, 3), (3, 4), (3, 5), (4, 5)]
        self.food = [(2, 0), (5, 1), (1, 4)]

    def draw(self):
        for x, y in self.snake:
            before = 'end'     
            after = 'end'      
            key = before + '-' + after
            snake_tiles[key].blit(x * TILE_SIZE, y * TILE_SIZE,
                                  width=TILE_SIZE, height=TILE_SIZE)
        for x, y in self.food:
            apple_image.blit(x * TILE_SIZE, y * TILE_SIZE,
                             width=TILE_SIZE, height=TILE_SIZE)

state = GameState()
state.initialize()

apple_image = pyglet.image.load('apple.png')
green_image = pyglet.image.load('green.png')
snake_tiles = {}
for start in ['bottom', 'end', 'left', 'right', 'top']:
    for end in ['bottom', 'end', 'left', 'right', 'top', 'dead', 'tongue']:
        key = start + '-' + end
        image = pyglet.image.load('snake-tiles/' + key + '.png')
        snake_tiles[key] = image

window = pyglet.window.Window()

@window.event
def on_draw():
    window.clear()
    # Better drawing (for us magic for now)
    pyglet.gl.glEnable(pyglet.gl.GL_BLEND)
    pyglet.gl.glBlendFunc(pyglet.gl.GL_SRC_ALPHA, pyglet.gl.GL_ONE_MINUS_SRC_ALPHA)

    state.draw()

pyglet.app.run()
```
Try to add to class GameState method that adds an tile to snake. 
```python
    def move(self, dt):
        x, y = snake[-1]
        new_x = x + 1
        new_y = y
        new_head = new_x, new_y
        snake.append(new_head)
```
And just above the row `pyglet.app.run` tell Pyglet, that it should be called every 1/6 second:
```python
pyglet.clock.schedule_interval(state.move, 1/6)
```

Does it work?
So add `del snake[0]` to that method so that the snake does not grow infinitely. 
Do you know what this command does? If not, take a look at the notes on lists again!

Can you modify the function to make the snake crawl upwards? Or downwards?

If yes, congratulations! The remaining part is to control the direction of the snake using the arrow keys on the keyboard, and most of the game will be done!

For sure, I am attaching my solution:
{% filter solution %} 
In the `move` method, it is necessary to set the variables `new_x` and `new_y` differently:

For upward movement:

```python
new_x = old_x
new_y = old_y + 1
``` 

"And down:"

```python
new_x = old_x
new_y = old_y - 1
```

This code sets the value of `new_x` to be the same as `old_x`, and sets the value of `new_y` to be one less than the value of `old_y`.

{% endfilter %}


## Control

Now to the promised control. Specifically, first to the direction changes.

The snake in the game crawls in the same direction until the player presses a key and changes the direction.

To make sure that the snake "remembers" where it is crawling, it is necessary to have a direction as part of the game state. Let's save it in an attribute called `snake_direction`.

What exactly should be stored there? 
How to represent direction in Python - using numbers, tuples, and so on?

{{ figure( img=static('coord-vectors.svg'), alt="Mřížka s X a Y souřadnicemi", ) }}

The most convenient solution is probably to store how many squares the snake should move, separately in the <var>x</var> and <var>y</var> directions. So, as a pair:

(`1, 0`) = right (by one square in the positive <var>x</var> direction; do not move in the <var>y</var> direction)
(`-1, 0`) = left (by one square in the negative <var>x</var> direction)
(`0, 1`) = up (+<var>y</var>, but do not move in the <var>x</var> direction)
(`0, -1`) = down (-<var>y</var>)

Add the new attribute to the `initialize` method.

```python
self.snake_direction = 0, 1
```

In the `move` method, change the setting of `new_x` and `new_y` according to the new attribute.
```python
dir_x, dir_y = self.snake_direction
new_x = old_x + dir_x
new_y = old_y + dir_y
```

You can now change the direction of the snake by changing the `snake_direction` in the `initialize` function. Does it work? (If not, fix it - and if you can't, call someone for help!)

Now, the only thing left is to change the `snake_direction` attribute when the user presses something on the keyboard. That is already the domain of Pyglet.

It is necessary to add a function that responds to a key press. For Pyglet to find and be able to call this function, it must be named 'on_key_press', it must have the decorator '@window.event', and it must take two parameters: the number of the key that was pressed and information about modifiers such as <kbd>Shift</kbd> or <kbd>Ctrl</kbd>.
```python
@window.event
def on_key_press(key_code, modifier):
    ...
```

The first parameter is important. It sets the current direction of the snake. The key codes are defined in the module [`pyglet.window.key`](https://pyglet.readthedocs.io/en/pyglet-1.3-maintenance/modules/window_key.html#key-constants) as constants with names like `LEFT`, `ENTER`, `Q`, or `AMPERSAND`. We will use arrows - `LEFT`, `RIGHT`, `UP`, and `DOWN`.


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

The second parameter will not be needed in our game, but it must be in the function header.

The function `on_key_press` needs to be placed somewhere after setting up the `window` (so that `window.event` is available) and before `pyglet.app.run()` (because setting up controls after the game has started is unnecessary). The best way is to place it next to another function with the `@window.event` decorator, so that they are nicely together.

Does it work?
Can you control the direction of the snake?
That's great!
However, during testing, you will definitely come across a few things that need to be finished.

* The snake shouldn't have the opportunity to climb out of the window.
* The snake should eat food and grow.
* The game should end when the snake hits itself or the edge of the window.

Let's solve them one by one.


## So far so good, but now we will hit a bump

"Snake" games like ours have two variations: either there is a "wall" around the playground and the player loses when hitting the edge, or the playground is "endless" - the snake crawls through the edge and appears on the other side. We will program the first variation - the wall.

To find out if the snake "crawled out" of the left edge of the window, it is necessary to check if the <var>x</var>-coordinate of the head is less than 0. This should be done immediately after obtaining the new coordinates of the head - specifically, right after the line `new_head = new_x, new_y` in the `move` method.

And what to do in such a crash?
To start with, the easiest thing to do is to end the game.
For this, Python has the `exit()` function, which works similarly to when an error occurs in the program.
Instead of a long error message, it shows the given text.

The end of the program is not a very pleasant way to tell the player that they lost. However, we will change this part soon, so for now this simple way will suffice.

```python
def move(self):
    old_x, old_y = self.snake[-1]  # Get the current position of the snake's head
    dir_x, dir_y = self.snake_direction  # Get the direction in which the snake is moving
    new_x = old_x + dir_x  # Calculate the new x-coordinate of the snake's head
    new_y = old_y + dir_y  # Calculate the new y-coordinate of the snake's head
    new_head = new_x, new_y  # Create a tuple with the new coordinates as the new head of the snake
    
    # New code - checking if the player has gone out of the playing area
    if new_x < 0:
        exit('GAME OVER')

    self.snake.append(new_head)
    del self.snake[0]
```
I believe that you can manage to do the same check for climbing out from the bottom edge.

But how to treat the remaining edges - the right and the top ones? It is necessary to know the size of the window. And Pyglet knows it; the class with state should not have access to the window!

The behavior of the game depends on the size of the game board. This information will therefore have to be part of the state. For starters, set a size - say 10x10 - in `initialize`.
```python
        self.width = 10
        self.height = 10
```
And then arrange for the game to end after hitting an invisible wall around the large 10x10 square field. Test all variants thoroughly - the northern, southern, eastern and western wall. The snake is virtual, so you don't have to worry about creating a bump on it by hitting the walls.

{% filter solution %}

    def move(self):
        old_x, old_y = self.snake[-1]
        dir_x, dir_y = self.snake_direction
        new_x = old_x + dir_x
        new_y = old_y + dir_y

        # Checking if the player has gone outside of the game area
        if new_x < 0:
            exit('GAME OVER')
        if new_y < 0:
            exit('GAME OVER')
        if new_x >= self.width:
            exit('GAME OVER')
        if new_y >= self.height:
            exit('GAME OVER')

        new_head = new_x, new_y
        self.snake.append(new_head)
        del self.snake[0]

{% endfilter %}

And then in the file with the game, right after you create the state (`state = GameState()`) and the window, set the *actual* size. Use integer division so that the number of tiles is in whole numbers.
```python
state.width = window.width // TILE_SIZE
state.height = window.height // TILE_SIZE
```

## Feeding

So. The snake is in the cage, it can't climb out anymore. What's next?

Now you have to take care of the snake: feed it regularly. But before that, it is necessary to teach it how to eat at all - it is not yet accustomed to our food. When you manage to do that, it will grow like crazy!

Specifically, you must ensure that when the snake crawls onto a square with food, the food disappears. To achieve this, you can use:
* the `in` operator, which determines whether something (such as coordinates) is in a list (such as a list of food coordinates), and
* the `remove` method, which removes a specified element from a list (based on the *value* of the element - as opposed to `del`, which removes based on position).

To check the climb out of the playing area, you need to enter a code that does the following:" 

+ If the new position of the head is in the list of food coordinates:
  * Remove this position from the list of food coordinates."

Can you write it?

{% filter solution %}
```python
        if new_head in self.food:
            self.food.remove(new_head)
```
{% endfilter %}

Try to see if it works. The snake should eat food.

But there is still a need to arrange so that after each bite it grows a bit. But how? Which direction should it grow?

Here it is good to look at the existing code and realize what it does.

Our snake crawls in such a way that it first grows in the front (using `append`) and then shrinks in the back (using `del self.snake[0]`). 

So in order for the snake to grow after eating, it is enough to *skip* the shrinking! And by *skip* I mean to condition it using `if`. The logic of eating and shrinking of the snake will be:

+ When a snake eats food, the food disappears. The snake does not get smaller. 
+ Otherwise (when the snake does not eat food), the snake will shrink (and thus not grow).

Translated into Python:
```python
        if new_head in self.food:
            self.food.remove(new_head)
        else:
            del self.snake[0]
```

For those who are beginning to get lost, I will provide the entire 'move' method. But woe to those who copy the code without trying to understand it!
{% filter solution %}
```python
    def move(self):
        old_x, old_y = self.snake[-1]
        dir_x, dir_y = self.snake_direction
        new_x = old_x + dir_x
        new_y = old_y + dir_y
        new_head = new_x, new_y

        # Kontrola vylezení z hrací plochy
        if new_x < 0:
            exit('GAME OVER')
        if new_y < 0:
            exit('GAME OVER')
        if new_x >= self.width:
            exit('GAME OVER')
        if new_y >= self.height:
            exit('GAME OVER')

        self.snake.append(new_head)
        if new_head in self.food:
            self.food.remove(new_head)
        else:
            del self.snake[0]
```
{% endfilter %}


## New food 

When a snake already knows how to eat, it is necessary to provide it with a regular supply of food. Ideally, each eaten meal should be replaced with a new one.

Add the following new method to the `GameState` class, which is able to add food:
```python
    def add_food(self):
        x = 0
        y = 0
        position = x, y
        self.food.append(position)
```

Then call this method - find the code in the program that is executed when a new food needs to be added, and add the following line there:
```python   
        self.add_food()
```
This method adds food at position (0, 0), which is always in the same corner. It's good just for... well, for verifying that the food is really being added to the list. It would be nice if the new food always appeared somewhere else, at a random location. You can use the `random.randrange` function for that. Remember that calling `randrange(N)` returns a random integer from 0 to <var>N</var> - 1.

What range of numbers do you need for snake food?

When you realize it, try adding chance to the program: the food should appear on a *completely random* square on the game board.

Don't forget about `import random` - it belongs at the very beginning of the file. But make any further changes only in the `add_food` method.

{% filter solution %}
```python
    def add_food(self):
        x = random.randrange(self.width)
        y = random.randrange(self.height)
        position = x, y
        self.food.append(position)
```
{% endfilter %}

When you test it, you will probably find out that a *completely random* tile is not ideal. Sometimes food appears on a tile with a snake, or even on another piece of food. It is therefore good to check this situation, and when the choice falls on a full tile, do not add food.
```python
        if (position not in self.snake) and (position not in self.food):
            self.food.append(position)
```

When you try *this*, you will find out that sometimes no new food is added at all. That's not a good option either - the snake would still be hungry. What to do about it?

Surprisingly good (although not *completely* ideal) solution is to try selecting the square several times. When an empty square falls, put the food there; when a full square falls, just try again.

However, it is necessary to limit the number of attempts so that in a situation where the field is *completely* full, the computer does not keep selecting endlessly. Let's say that if we don't manage to select an empty field after 100 attempts, we give up. There is probably enough food already.

The method `add_food` after all modifications will look like this:

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

If it works for you, also arrange for food to be at random positions at the start of the game.
{% filter solution %} 
In the `initialize` method, instead of setting `self.food` to a list with food positions, you can write:
```python
        self.food = []
        self.add_food()
        self.add_food()
```
Then at the beginning of the game, two random foods will be waiting for the snake.{% endfilter %}

## End

The snake can now grow to enormous dimensions - and the only way to lose is by hitting the wall. Make sure the game ends even if it hits itself.

How to do it?
For the `move` method, in addition to checking if the player has climbed out of the playing area, provide code that will do the following:

+ If the coordinates of the new head are already part of the snake: 
    * End the game (similarly to hitting the wall).

Can you translate it into Python?
{% filter solution %}
```python
        # Checking if the snake has collided
        if new_head in self.snake:
            exit('GAME OVER')
```
{% endfilter %}

Done!

## Pause

However, it is not good to end the whole program and close the window at the end of the game.

It's better to "pause" the game and show the player the situation in which the unfortunate snake ended up, so that they can learn from it for next time.

To make it possible, we will add another attribute to the game: 'alive'. It will be set to 'True' as long as the snake is alive. When the snake hits something, 'alive' will be set to 'False', and from then on the snake will not move anymore. It is also good to show graphically that the snake is not doing well - the player will then be more likely to feel guilty.

Try to think where in the code the following pieces of code, which implement the game loss, belong.
```python
        # Initial setting of the attribute
        self.alive = True
```
```python
        # Stopping the snake
        self.alive = False
```
```python
        # Preventing movement
        if not self.alive:
            return
```

```python
        # Graphic indication
        if after == 'end' and not state.alive:
            after = 'dead'
```
{% filter solution %}
* "Initial attribute setting" to the `initialize` method.
* "Stopping the snake" instead of *all* occurrences of `raise("Game Over")`.
* "Preventing movement" at the very beginning of the `move` method (the `return` statement will immediately terminate the execution of the method).
* "Graphic indication" after the section for selecting the image for the snake piece.
{% endfilter %}

## And that's it?

Congratulations, you have a functional and playable game! I hope you are proud of yourself!

Have something sweet, you deserve it.

<hr>

Here is my solution. It may differ quite a bit from yours at this time - that is completely normal.
Don't look here until you program the snake {{gnd('yourself', 'yourself')}}. A person learns from mistakes and constant testing - and especially a programmer. Learning from already solved problems is harder.
{% filter solution %}
```python
import random
import pyglet

TILE_SIZE = 64

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

    def draw(self):
        for x, y in self.snake:
            before = 'end'     # (Tady případně je nějaké
            after = 'end'      #  složitější vybírání políčka)
            if after == 'end' and not state.alive:
                after = 'dead'
            key = before + '-' + after
            snake_tiles[key].blit(x * TILE_SIZE, y * TILE_SIZE,
                                  width=TILE_SIZE, height=TILE_SIZE)
        for x, y in self.food:
            apple_image.blit(
                x * TILE_SIZE, y * TILE_SIZE, width=TILE_SIZE, height=TILE_SIZE)

    def move(self):
        if not self.alive:
            return

        old_x, old_y = self.snake[-1]
        dir_x, dir_y = self.snake_direction
        new_x = old_x + dir_x
        new_y = old_y + dir_y

        # Kontrola vylezení z hrací plochy
        if new_x < 0:
            self.alive = False
        if new_y < 0:
            self.alive = False
        if new_x >= self.width:
            self.alive = False
        if new_y >= self.height:
            self.alive = False

        new_head = new_x, new_y
        if new_head in self.snake:
            self.alive = False
        self.snake.append(new_head)

        if new_head in self.food:
            self.food.remove(new_head)
            self.add_food()
        else:
            del self.snake[0]

    def add_food(self):
        for try_number in range(100):
            x = random.randrange(self.width)
            y = random.randrange(self.height)
            position = x, y
            if (position not in self.snake) and (position not in self.food):
                self.food.append(position)
                return

apple_image = pyglet.image.load('apple.png')
snake_tiles = {}
for start in ['bottom', 'end', 'left', 'right', 'top']:
    for end in ['bottom', 'end', 'left', 'right', 'top', 'dead', 'tongue']:
        key = start + '-' + end
        image = pyglet.image.load('snake-tiles/' + key + '.png')
        snake_tiles[key] = image

window = pyglet.window.Window()

state = GameState()
state.initialize()
state.width = window.width // TILE_SIZE
state.height = window.height // TILE_SIZE


@window.event
def on_draw():
    window.clear()
    pyglet.gl.glEnable(pyglet.gl.GL_BLEND)
    pyglet.gl.glBlendFunc(pyglet.gl.GL_SRC_ALPHA, pyglet.gl.GL_ONE_MINUS_SRC_ALPHA)
    state.draw()


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


def move(dt):
    state.move()


pyglet.clock.schedule_interval(move, 1/6)

pyglet.app.run()
```
{% endfilter %}

## What's next? 

Can you find any other improvements that could be made?

Try the following extensions, for example. They are roughly sorted by complexity:

+ Improve the controls (and gameplay!) according to the [manual](../handling).

+ Every 30 seconds of the game, new food will be added automatically, so there will be more of them on the playing field.

+ When the snake crawls out of the window, instead of the end of the game, it appears on the other side. (See [instructions](../toroid).)

+ There will be two snakes; the second one is controlled by the keys <kbd>W</kbd> <kbd>A</kbd> <kbd>S</kbd> <kbd>D</kbd>. (It's best to create a new class, `Snake`, and move all the snake's state from `GameState` to it. Then keep a list of snakes in `GameState`. This change needs to be adapted throughout the entire program.)

+ The game will gradually speed up. (It is best to modify the 'move' function so that it automatically plans when to call itself. The use of 'schedule_interval' will no longer be necessary.)
