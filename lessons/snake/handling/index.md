> [warning]
> This is a machine-generated translation.

# Improvement of Snake controls

Maybe you will notice, especially if you have played some version of the game Snake before, that the controls of your new game are a bit frustrating. And maybe it's not entirely easy to figure out why.

The (mainly) two reasons are responsible for it.

1. When you press two arrows quickly in a row, only the second one will be reflected in the snake's next move.
2. When the snake is moving to the left and the player presses the right arrow, the snake will turn and hit its head against its neck.

Let's solve them.

## Queue of instructions

When you press two arrows quickly one after the other, only the second one will be visible in the next move of the snake.

From the program's perspective, this behavior makes sense - after pressing an arrow, its direction is saved and the last saved direction is used during the snake's "move". However, it is difficult to quickly turn the snake with this behavior: the player must be careful not to press more than one arrow for each "move". It would be better if *all* pressed keys were saved, and the snake would react to a maximum of one key per move. It could then "save" the others for future moves.

Such a 'queue' of keystrokes can be stored in a list. Add a list to the game state for this purpose (in the `__init__` method).
```python
        self.queued_directions = []
```

Fill this queue after every key press using the 'append' method. It is necessary to change most of the 'on_key_press' function - instead of changing the attribute, the new direction is added to the list. To avoid writing 'append' four times, you can save the new direction in a helper variable:
```python
@window.event
def on_key_press(key_code, modifier):
    if key_code == pyglet.window.key.LEFT:
        new_direction = -1, 0
    if key_code == pyglet.window.key.RIGHT:
        new_direction = 1, 0
    if key_code == pyglet.window.key.DOWN:
        new_direction = 0, -1
    if key_code == pyglet.window.key.UP:
        new_direction = 0, 1
    state.queued_directions.append(new_direction)
```


And back to logic. In the `move` method, instead of `dir_x, dir_y = self.snake_direction`, select the first unused element from the queue. Don't forget to delete it from the queue so it can be used next.

```python
if self.queued_directions:
    new_direction = self.queued_directions[0]
    del self.queued_directions[0]
    self.snake_direction = new_direction
```

Check that it works.

## Not a step back

When the player presses the arrow in the opposite direction to which the snake is currently crawling, the snake will turn and hit its head against its neck.

From the program's perspective, it makes sense again: if the snake crawls to the left, the square to the right of its head is full. So when the snake starts crawling to the right, it hits the square with the snake and the player loses. However, from the perspective of the game (and biology!), hitting the neck doesn't make much sense. It would be better to completely ignore the direction change.

And how to recognize the opposite direction?
When the snake crawls to the right, `(1, 0)`, then the opposite direction is to the left, `(-1, 0)`.
When it crawls down, `(0, -1)`, then the opposite direction is up, `(0, 1)`.
In general, for a direction of (x, y), the opposite direction is (-x, -y).

However, we are currently working with whole <var>n</var>-tuples, so both <var>x</var> and <var>y</var> need to be "unpacked". The code will therefore look like this:

```python
old_x, old_y = self.snake_direction
new_x, new_y = new_direction
if (old_x, old_y) != (-new_x, -new_y):
    self.snake_direction = new_direction
```

Replace it with the original `self.snake_direction = new_direction`.
