# Infinite cage

Instead of ending the game when hitting the edge of the window, you can let the snake "pass through" and appear on the other side.

From a game logic standpoint, it's not as complicated as it may sound. It's enough to set the appropriate value for the end of the game in the `move` function. However, it's necessary to be careful where to use `new_x` and where to use `new_y`, where to use `width` and where to use `height`, and where to add or subtract one, so that everything fits when numbering from zero. Give it a try!

{% filter solution %}
```python
        if new_x < 0:
            new_x = self.width - 1
        if new_y < 0:
            new_y = self.height - 1
        if new_x >= self.width:
            new_x = 0
        if new_y >= self.height:
            new_y = 0
```
{% endfilter %}

However, if you draw a snake (instead of a caterpillar), you will now encounter a problem with selecting the correct pieces - the edge of the snake game visually divides it into two smaller parts. I leave the solution to this problem to the reader - with the note that it is a very difficult problem.

## Residual solution

Can the logic of climbing out of the window be solved more simply? Yes, it can!
Mathematicians have come up with an operation called the *remainder of division*.
It does exactly what you need - the remainder of division of the new coordinates by the size of the field gives a coordinate that lies within the field.
When the previous coordinate was one larger than the maximum, the remainder of division will be zero; when it was -1, we get the maximum.

Python uses the operator `%` for the remainder after division. Try it out.

``` 
>>> 6 % 10      # Remainder after dividing six by ten
6
>>> 10 % 10
0
>>> -1 % 10
9
```

The entire code for controlling and handling climbing out of the playing area can be replaced by two lines.

```python
new_x = new_x % self.width
new_y = new_y % self.height
```
Similar mathematical 'shortcuts' can often make life easier for programmers. However, coming up with them is not always easy. But don't worry: if you're not interested in studying computer science at school, know that it's possible to do it without 'shortcuts'. It just might be a bit more convoluted at times.

>[note]
>The fact that there is exactly the operation we need is not entirely a coincidence. The mathematical simplicity is rather the *reason* why the playing field behaves this way in many old games. <This is called [toroidal topology](https://en.wikipedia.org/wiki/Torus#Topology) in professional terms.

>[note] For mathematicians
>Experienced mathematicians may now complain about the need to define the remainder of division of a negative number. Therefore, I will add that Python intentionally [defines it appropriately](https://docs.python.org/3/reference/expressions.html#binary-arithmetic-operations) for this purpose; `a % b` always has the same sign as `b`.

## Rendering

In your free time, try to fix the problem. I recommend returning to the 'abstract' function that only prints coordinates and directions:

```
1 2 tail right
2 2 left right
3 2 left top
3 3 bottom top
3 4 bottom top
3 5 bottom right
4 5 left head
```

If you follow the instructions, you have this function saved in the file `smery.py`. First, fix it and then 'transplant' the solution into the game.
