# {% block heading %}Installation of {% block name_gen %} editor {{ var('editor_name') }} {% endblock %}{% endblock %}

{% block install %}

Editor {{ editor_name }} - download it from its [homepage]({{ editor_url }}) and install it.

{% endblock %}

## Setup

{% block setup %}

(This shouldn't be visible)

{% endblock %}

## Indentation practice

As already mentioned, in Python it is important how many spaces a line starts with.
Therefore, it will be useful for us to know how to quickly indent blocks of text.
Let's see how to do it.

Copy this text into the editor:
```
OPHELIA:
Good my lord,
How does your honour for this many a day?
HAMLET:
I humbly thank you; well, well, well.
OPHELIA:
My lord, I have remembrances of yours
That I have longed long to re-deliver.
I pray you, now receive them.
HAMLET:
No, not I.
I never gave you aught.
OPHELIA:
My honour’d lord, you know right well you did,
And with them words of so sweet breath compos’d
As made the things more rich; their perfume lost,
Take these again; for to the noble mind
Rich gifts wax poor when givers prove unkind.
There, my lord.
```
(An excerpt from *Hamlet* by W. Shakespeare)

This text is not very clear, so we will try to space it out to make it look like this:
```
OPHELIA:
    Good my lord,
    How does your honour for this many a day?
HAMLET:
    I humbly thank you; well, well, well.
OPHELIA:
    My lord, I have remembrances of yours
    That I have longed long to re-deliver.
    I pray you, now receive them.
HAMLET:
    No, not I.
    I never gave you aught.
OPHELIA:
    My honour’d lord, you know right well you did,
    And with them words of so sweet breath compos’d
    As made the things more rich; their perfume lost,
    Take these again; for to the noble mind
    Rich gifts wax poor when givers prove unkind.
    There, my lord.
```

To indent one line, set the cursor at the beginning of the line and press the <kbd>Tab</kbd> key.
Each time you press it, the line will be indented by 4 spaces.

If you indent too much, you can reduce the indentation using <kbd>Shift</kbd>+<kbd>Tab</kbd>.

If you want to indent multiple lines at once, select them all and press <kbd>Tab</kbd>. You can also "unindent" the whole selection using <kbd>Shift</kbd>+<kbd>Tab</kbd>.

And that's it! Now you not only have the editor set up, but you also know how to use it.
