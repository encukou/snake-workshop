# Installation of {% block name_gen %} editor {{ var('editor_name') }} {% endblock %}

{% block install %}

Editor {{ editor_name }} - download it from its [homepage]({{ editor_url }}) and install it.

{% endblock %}

## Settings

{% block setup %}

(This shouldn't be seen.)

{% endblock %}

## Practice of indentation

As already mentioned, in Python it is important how many spaces a line starts with. Therefore, it will be useful for us to know how to quickly indent blocks of text. Let's show how to do it.

Copy this text into the editor:
```
Ofelie:
Oh prince!
How has Your Highness been for so long?
Hamlet:
Humbly thanking you: great, great, great.
Ofelie:
I still have gifts from you, prince,
which I have longed to return. Please,
accept them now.
Hamlet:
Who? Me? I never
gave you anything.
Ofelie:
You did, Your Highness. And along with the gifts, words
so sweet that each of them
had their fragrance. It has now faded,
and so I am returning them. The richest gifts
turn into trash when the giver frowns.
Here, Your Highness.
```
(An excerpt from the play Hamlet, written by W. Shakespeare, translated by E. A. Saudek to Czech and by chatGPT back to English :))

This text is not very clear, so we will try to space it out to make it look like this:
```
Ofelie:
  Oh, Prince!
  How has Your Highness been for so long?
Hamlet:
  Thank you humbly: great, great, great.
Ofelie:
  I still have gifts from you, Prince,
  which I have longed to return. Please,
  accept them now.
  and so on.
```

To indent one line, set the cursor at the beginning of the line and press the <kbd>Tab</kbd> key. Each time you press it, the line will be indented by 4 spaces.

If you indent too much, you can reduce the indentation using Shift+Tab.

If you want to indent multiple lines at once, select them all and press <kbd>Tab</kbd>. You can also "unindent" the selection using <kbd>Shift</kbd>+<kbd>Tab</kbd>.

And that's it! Now you not only have the editor set up, but you also know how to use it.
