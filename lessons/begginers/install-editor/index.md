# Editor installation

Editor, a program for text editing, is a basic tool for every programmer.
Therefore, it is good to invest a little time into it.

It's more or less irrelevant which programming editor you use.
If you already have a favorite one, you just need to set it up; if not, we can recommend one for you.
However, if you're using Notepad in Windows or TextEdit (an editor pre-installed in macOS), it won't be enough.
Similarly, programs like Word or Writer are not suitable.

## What a programmer's editor can do

The text editor for programmers allows you to edit plain text - letters.
Unlike programs such as Word, Writer or Pages, it does not allow you to *format* text, that is, to create headings, color, enlarge the font for individual words, insert images, and so on.

Using the editor, you will enter commands to the computer, so you don't need formatting.
Take a look at the difference between the following commands for someone who has to follow them:

* Draw me a lamb!
* <font color="green">Draw <big><big>me</big> <u>a lamb</u>!</big></font>

Our editors do not know formatting, but it does not mean that they are completely "stupid" tools.
To make it more convenient for you to edit these programs, they have several tricks.

Support for multiple files
:   Larger projects consist of multiple files that you can have open in the editor at the same time.

Line numbering
:   A number is displayed before each line.
    This will be very useful when Python complains that the error is on line 183.

Indentation
:   In Python, it is important how many spaces a line starts with.
    Properly set up editor significantly simplifies indentation for us.

Syntax highlighting
:    Although we cannot set the color directly for individual letters,
    the editor can give us a hint about how the computer will understand our instructions by syntax highlighting.
    But it's just a hint: a programmer with a differently configured editor may have the same file colored quite differently.

> [note]
>
> As an illustration, this is what a piece of code can look like in an editor:
> 
>```python
>    1  @app.route('/courses/<course:course>/')
>    2  def course_page(course):
>    3      try:
>    4          return render_template(
>    5              'course.html',
>    6              course=course,
>    7              plan=course.sessions,
>    8          )
>    9      except TemplateNotFound:
>    10          abort(404)
>```

## Editor selection and settings

If you choose an editor, click on its name and you will be taken to instructions for downloading and setting it up.
(You don't have to come back to this page again.)

* [Visual Studio Code]({{ subpage_url('vscode') }}) - recommended editor for Windows and macOS (and suitable for Linux as well).
  Recently, it has become probably the most popular code editor.
  It offers many features and has a large user and developer base, so it is constantly improving.

  Recently, it is capable of more and more - even things that are a bit disturbing for a beginner.
  Don't be afraid to adjust or turn off some features.

On Linux, you probably already have Gedit or Kate installed.
Try looking in the system menu to see if you have one of them (or run them from the command line as `gedit` or `kate`).
If you do, click on the link below and configure the editor.
If you don't have either, select Visual Studio Code (see above).

* [Gedit]({{ subpage_url('gedit') }}) - is usually found on systems with the GNOME environment.
* [Kate]({{ subpage_url('kate') }}) - is usually found on systems with the KDE environment.

There are also other editors for which we have guides or have recommended in older versions of these materials.
If you decide to use one of them, you won't make a mistake.

* [Notepad++]({{ subpage_url('notepad-plus-plus') }}) - an undemanding editor for Windows suitable for slower computers

If you already have your favorite editor - Vim, Emacs, Geany, etc., use that one:

[Others]({{ subpage_url('others') }}) - If you have a different editor, make sure it is correctly set up.

### IDE

There are also more complex and powerful editors, so-called IDEs (Integrated Development Environments), such as [PyCharm], [Eclipse] or [KDevelop].
They have many advanced features that help programmers: auto-completion, renaming, running programs, managing virtual environments, and more. 
However, they are not very suitable for beginners.

If you still want to use such an editor, you should already know it quite well: know what the editor does for you and how to fix it when it does soething wrong.

Coaches usually only know one editor - the one they use - so they may not be able to quickly help with advanced IDE.

[PyCharm]: https://www.jetbrains.com/pycharm/
[Eclipse]: https://eclipse.org/
[KDevelop]: https://www.kdevelop.org/
