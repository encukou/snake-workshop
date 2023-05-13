"Vybírání kousků hada" in English means "Picking pieces of a snake".

Instead of having the same piece of snake everywhere, we will always want to choose the right one.

"How to do it?" "According to what should I choose it?"

"Pictures with pieces of snake are named <code><var>from</var>-<var>to</var></code>. This is not a coincidence - it shows what you need to know in order to choose the right piece."

"When you have a snake according to the following picture, the piece belongs on the tile (3,2) on which the snake crawls from left to up - therefore `snake_tiles['left-top']`."

The image shows a snake on a "chessboard" with coordinates. The square (3, 2) is highlighted and arrows are pointing to the left and up from it, showing where the snake is moving.

"At the ends of the snake, in the names of the pictures, the direction 'end' is replaced."

"For each square, you will need to determine where the snake is crawling on it - that is, the direction to the *previous* and *next* coordinate."

I'm sorry, but the text you provided appears to be a code written in a programming language called "Jinja2". It is used to generate HTML code dynamically. It is not a text that can be translated into English.

This is a **difficult task**. Even though you theoretically know all the necessary information and tools for it now, it is necessary to put them together in the right way. This putting together, *algorithm design*, is the most complex programming discipline.

"Try to think about it, let it settle in your head maybe overnight, go back to the materials from previous lessons (especially the introduction to Python), experiment and discover... And eventually you will figure it out."

"If you don't have time, let's see how we can arrange it."

"This is not the gospel."

"I am describing one possible solution here. There are many other correct ways to choose the snake's squares. Perhaps you will even find another solution easier - and maybe it will even be *your* solution!"

"Simpler subproblems"

"Complicated problems are usually appropriately divided into several simpler problems by programmers. Each one is then solved separately and then put together."

"What simpler tasks could be found here?"

1. Go through all the coordinates and for each of them, determine the previous and next coordinate of the square.
2. When you have two coordinates, determine the direction from one to the other.

The solution to the first one in the table above is to "fill in" the columns with coordinates. The solution to the second one will give you *directions*, parts of the image name, from this information.

"You will need to solve both problems. However, the second one is easier, so let's focus on it."

"Zjistit směr" in English means "to find out the direction".

"You need to tell the computer how to determine the direction from one to the other of two adjacent squares, based on their coordinates."

For example, the direction from (3, 2) to (2, 2) is *left*.
The direction from (3, 2) to (3, 3) is *up*.
(See the picture or the third row of the table above.)

The text is not provided. Please provide the text you would like me to translate.

In Python, you write it as a *function* that takes two arguments (coordinates) and returns the English name of the direction - a string that can be used in the file name of the image.

"When this function is completed, it should be used as follows:"

The given text is not in Czech language, it is Python code. The code defines a function called `direction` that takes two coordinates as input and returns the direction from the first coordinate to the second coordinate. 

The first example input `(3, 2), (2, 2)` indicates that the second coordinate is to the left of the first coordinate, so the function returns `'left'`. 

The second input `(3, 3), (3, 2)` indicates that the second coordinate is below the first coordinate, so the function returns `'bottom'`. 

The third input `(3, 3), 'end'` indicates that the second coordinate is not a valid coordinate and the function returns `'end'`.

"At the ends of the snake, instead of a pair of numbers, something else will be needed as the second coordinate. The string `'end'` works well, but anything that is not a coordinate could be used, such as `False`, `-1`, or even `[]`. An experienced Pythonista would use the value `None`."

How to write such a function?
If you take a closer look at the first three columns of the table above, you may figure out how the coordinates that are to the *left* of each other differ. Or *above* each other.

How to determine the direction between two coordinates:
  * When the second one is not a coordinate:
    * the result is `'end'`
  * When the <var>x</var> of the first one equals the second one's <var>x</var>+1:
    * the result is `'left'`
  * When the <var>x</var> of the first one equals the second one's <var>x</var>-1:
    * the result is `'right'`
  * When the <var>y</var> of the first one equals the second one's <var>y</var>+1:
    * the result is `'bottom'`
  * When the <var>y</var> of the first one equals the second one's <var>y</var>-1:
    * the result is `'top'`

An experienced programmer will now pay attention and ask: "But what if neither of those conditions is true?" Such a situation may not occur in the game (or maybe it will?), but it is still good to catch it and add, for example, "Otherwise, the result is `'end'`" at the end of the process.

"Coming up with this procedure is the more complicated part of solving our problem. The rest is just a nearly literal translation from Czech to Python."

The code defines a function called "direction" that takes two parameters "a" and "b". If the value of "b" is equal to the string 'end', the function returns the string 'end'.

"Breakdown of coordinates into numbers (x, y) - that is called "obvious" in Czech.
x_a, y_a = a
x_b, y_b = b"

# ... and the logic continues
    if x_a == x_b + 1:
        return 'left'
    elif x_a == x_b - 1:
        return 'right'
    elif y_a == y_b + 1:
        return 'bottom'
    elif y_a == y_b - 1:
        return 'top'
    else:
        return 'end'

This is not Czech text. It appears to be a code snippet written in Python. The code is testing a function called "direction" with various input parameters and checking the output.

"Go through all coordinates."

"Now let's go back to the first problem: how to go through all the squares of the snake and find out the previous and next square for each?"

"Because the difference between coordinates such as (1, 2) and (2, 2) is not very readable at first glance, I will label the pieces of the snake with letters. I will write A instead of (1, 2); B instead of (2, 2); and so on."

The Czech text translates to: "Snake on the chessboard. Each piece of the snake has a letter: A, B, C, ..., G."

"I will draw such a snake as follows:"

"I will draw box A (for which I need to know that it is the beginning and after it is B)
I will draw box B (for which I need to know that before it is A and after it is B)
I will draw box C (for which I need to know that before it is B and after it is D)
...and so on."

This is a piece of code written in Czech that generates an HTML table. It uses a loop to iterate over the data and display it in the table. The table has three rows: 

- The first row displays the letters of the alphabet (A to H) as column headers.
- The second row displays the letter that comes before each letter in the data, except for the first one, which is marked with an "×".
- The third row displays the letter that comes after each letter in the data, except for the last one, which is marked with an "×".

"How to do it? You already have the first row of the table, the list [A, B, C, D, E, F, G] - these are the coordinates of the snake. When you manage to prepare lists with the second row, [×, A, B, C, D, E, F], and the third one, [B, C, D, E, F, G, ×], you can then combine them using the `zip` function. Do you remember it? It goes through several "conversing" lists and gives a tuple of the first elements, then a tuple of the second elements, then the third..."

"Our example was:"

```
Items = ['grass', 'sun', 'carrot', 'river']
Colors = ['green', 'yellow', 'orange', 'blue']
Places = ['on the ground', 'up above', 'on the plate', 'behind the wall']
```

"for vec, barva, misto in zip(veci, barvy, mista):
    print(barva, vec, 'je', misto)" translates to "for item, color, place in zip(items, colors, places):
    print(color, item, 'is', place)" in English.

"But you can use the same way:"

The code defines three lists in Python: `snake`, `prevs`, and `nexts`. 

`snake` contains the values `A`, `B`, `C`, `D`, `E`, `F`, and `G`.

`prevs` contains the values `x`, `A`, `B`, `C`, `D`, `E`, and `F`.

`nexts` contains the values `B`, `C`, `D`, `E`, `F`, `G`, and `x`.

"for coords, prev, next in zip(snake, prevs, nexts):
    print('on the field', coords, 'the snake crawls from', prev, 'to', next)"

The two additional lists need to be "created" from the first one: select the correct piece and add the "missing" element to the correct side.

```python
snake = ['A', 'B', 'C', 'D', 'E', 'F', 'G']
prevs = ['end'] + snake[:-1]
nexts = snake[1:] + ['end']
```

This is a piece of Python code that creates a list called `snake` with the values "A" to "G". It then creates two new lists called `prevs` and `nexts`. `prevs` contains the same values as `snake`, but with the string "end" added to the beginning of the list. `nexts` contains the same values as `snake`, but with the string "end" added to the end of the list.

"for coords, prev, next in zip(snake, prevs, nexts):
    print('on field', coords, 'snake crawls from', prev, 'to', next)"

Or, with "real" coordinates and the `direction` function:

The code you provided is not in Czech language but rather in Python programming language. It creates a list of tuples called "snake" which represents the coordinates of a snake in a grid.

The code translates to:

for coords, prev, next in zip(snake, ['end'] + snake[:-1], snake[1:] + ['end']):
    # direction from current cell to the previous one
    before = direction(coords, prev)  
    # direction from current cell to the next one
    after = direction(coords, next)   
    # concatenate the directions to form a key
    key = before + '-' + after
    # print the key and the current coordinates
    print('draw', key, 'at', coords)

If you've made it this far, I hope you won't have too much trouble "transplanting" this code into your game.