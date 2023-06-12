{% extends lesson.slug + '/_linux_base.md' %}

{% block name_gen %} editor {% endblock %}

{% block install %}

If you are using an editor for which we do not have instructions, you will have to set it up yourself.
Here are a few tips on what to watch out for.

{% endblock %}

{% block setup %}

## Line numbering

Make sure that your editor numbers the lines.
If not, check the settings and find out how to turn it on.

## Syntax highlighting 

Save a file with the extension `.py`, for example `test.py`, and copy the following program into it:

```python
def foo():
    return "abc" * 2
```

If the text is automatically colored (even with colors different from here), your editor is set up correctly.
Otherwise, check the settings and find out how to turn it on.

## Indentation

By pressing the <kbd>Tab</kbd> key at the *beginning of a line*, 4 spaces are inserted.
For writing and sharing code in Python, it is important that there are four spaces and that they are truly spaces.

If they are spaces, you can find out by selecting the indentation at the beginning with the mouse.
If you can select individual spaces, everything is fine.

If it is not possible to select individual spaces or if pressing <kbd>Tab</kbd> inserts a different number than 4, check the settings for options such as 'indentation size' or 'replace tabs with spaces'.

## Checking the style of source code

Editors often support the installation of plugins that can make coding easier and help with its control.
One of the most useful is a plugin for checking the correct style of source code.
Python has typographic rules.
For example, a space is written after a comma, but not before it.
They are optional, the program will work even if they are not followed, but they help write clear code, so it is good to follow them from the beginning.
These rules are described in the document [PEP8](https://www.python.org/dev/peps/pep-0008/).

Try to find and install such a plugin for your editor.

{% endblock %}
