# Classes

You have already familiarized yourself with a lot of *classes* of objects that you can work with in Python: with numbers that can be added and multiplied, for example; with strings that can be converted to capital letters; with lists that you can sort; with dictionaries that can be searched.
As you continue studying programming further, you'll discover additional classes of objects: files that can be read; web pages that can be sent to a browser; buttons that can be pressed, and so on.
There are countless classes.

And just as you can define a function using `def`, you can also create a new class {{gnd('himself', 'herself')}}. This is mainly used when you need a lot of objects in the program that have common behavior. Whole numbers, objects of the `int` class, have different values but they can all be added. Each list, object of the `list` class, can have different content, but all lists can be sorted.

The task for this section is to create a class called *kitten*, which can have different names, but all of them can meow and eat.

Start with meowing:

```python
class Kitten:
    def purr(self):
        print("Meow!")
``` 

Just like functions are defined using `def`, classes have the keyword `class`, after which you write the name of the class, a colon, and then the indented body of the class. Similar to how `def` creates a function, the `class` statement creates a new class and assigns it to a variable with the given name (here `Kitten`).

Classes are traditionally named with a capital letter to avoid confusion with 'normal' values.

>[note]
>Basic classes (`str`, `int`, etc.) do not have capital letters, mainly for historical reasons - they were originally functions.

In a class body, you can define methods that look just like functions - except they have a first argument `self`. But we'll explain that later - first, try purring:
```
# Creating a specific object
mourek = Kitten()

# Method call
mourek.purr() 
``` 

When you define a class (using the `class` block), it doesn't mean that there is a kitten in your program yet. A class is like a recipe or a manual: when you buy a cookbook, you will theoretically know how to bake a cake, what such a cake will look like, and that it can be eaten. But it still doesn't mean that you have the actual cake!

You create a specific object by calling a class: you use the class as a function, `Kitten()`, and the result is a new object of your class that you can now use.

Meow!

## Attributes

In objects created from 'custom' classes, you can set *attributes* - information that is stored with the given object. Attributes are marked by writing a period between the value and the name of its attribute.
```python
mourek = Kitten()
mourek.name = 'Mourek'
print(mourek.name)
```
The string `'Mourek'` now "belongs" to a specific kitten. When you create another kitten, you can name it differently - set its attribute `name` to a different string.

```python
micka = Kitten()
micka.name = 'Micka'

print(micka.name)
print(mourek.name)
```

## Parameter `self`.

Now let's briefly return to methods. Specifically, to the `self` parameter.

Each method has access to a specific object it works on, precisely through the `self` argument. Now that you have named the kittens, you can use `self` in the `purr` method to access the name of the specific kitten.

```python
class Kitten:
    def purr(self):
        print("{}: Meow!".format(self.name))

mourek = Kitten()
mourek.name = 'Mourek'

micka = Kitten()
micka.name = 'Micka'

mourek.purr()
micka.purr()
```


What happened? The expression `mourek.purr` represents a *method*. When you call it (`mourek.purr()`), the `mourek` object is passed to the `purr` function as the first argument, `self`.

Can such a method take more than one argument?
It can - `self` will be automatically added as the first argument,
the rest of the arguments will be taken from the method call.
For example:

```python
class Kitten:
    def purr(self):
        print("{}: Meow!".format(self.name))

    def eat(self, food):
        print("{}: Yum yum! I like the {}!".format(self.name, food))" 

mourek = Kitten()
mourek.name = 'Mourek'
mourek.eat('fish')
```

## Summary

Classes can do much more, but the basics are: all objects of a given class have some common behavior (for example, kittens can meow). And at the same time, each object also has its own information, just for it (for example, a kitten's meowing).

It is worth writing your own class when you have more objects with similar behavior in the program, or when you just need to have a set of functions (or methods) neatly together.

And that's it.
*You are absolutely great!* 
This was a difficult lesson, so you should be proud of yourself.
We are very proud of you for coming this far!

Take a short break - stretch, take a walk, close your eyes - before you start the next chapter. :)

