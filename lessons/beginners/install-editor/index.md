# Editor installation

A *text editor*, or just *editor*, is a programmer's most important tool.
Let's invest a little time into setting one up.

If you already have a favorite editor, you just need to set it up; if not, we can recommend one for you.
However, if you're using Notepad in Windows or TextEdit (an editor pre-installed in macOS), it won't be enough.
Fancy programs like Word or Writer are also not suitable.


## What a programmer's text editor can do

A good text editor allows you to edit plain text.
Unlike programs such as Word, Writer or Pages, it does not allow you to *format* text, that is, to create headings, color, enlarge the font for individual words, insert images, and so on.
When we give commands to the computer, such formatting would only get in the way – for example, the following commands are exactly the same for someone who has to follow them:

* Draw me a lamb!
* <font color="green">Draw <big><big>me</big> <u>a lamb</u>!</big></font>

While our editors do not know formatting, they should know a few tricks to make programming more convenient:

Support for multiple files
:   Larger projects consist of multiple files that you can have open in the editor at the same time.

Line numbering
:   A number is displayed before each line.
    This will be very useful when Python complains that the error is on line 183.

Indentation
:   In Python, indentation – how many spaces a line starts with – is important .
    An editor that's properly set up will help us keep track of this.

Syntax highlighting
:    Although we cannot directly set the colour of individual letters,
    the editor can apply formatting to give us a hint about how the computer will understand our instructions.
    But it's just a hint: a programmer with a differently configured editor may have the same file coloured quite differently.

> [note]
>
> As an illustration, this is what a piece of code can look like in an editor.
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

Choose an editor and click on its name for instructions for downloading and setting it up.
(You don't have to come back to this page again.)

* [Visual Studio Code]({{ subpage_url('vscode') }}) - recommended editor for Windows and macOS (and suitable for Linux as well).
  This is currently the most popular code editor among programmers.
  It offers many features and is constantly improving.

  Recently, it is capable of more and more - even things that are a bit 
  distracting for a beginner.
  Don't be afraid to adjust or turn off some features.

On Linux, you probably already have Gedit or Kate installed.
Try looking in the system menu to see if you have one of them (or run them from the command line as `gedit` or `kate`).
If you do, click on the link below and configure the editor.
If you don't have either, select Visual Studio Code (see above).

* [Gedit]({{ subpage_url('gedit') }}) - is usually found on systems with the GNOME environment.
* [Kate]({{ subpage_url('kate') }}) - is usually found on systems with the KDE environment.

There are also other editors for which we have guides or have recommended in older versions of these materials.
It's perfectly fine to use one of them.
And if you already have your favorite editor - Vim, Emacs, Geany, etc., use that one.

* [Notepad++]({{ subpage_url('notepad-plus-plus') }}) - an undemanding editor for Windows suitable for slower computers
* [Others]({{ subpage_url('others') }}) - If you have a different editor, make sure it is correctly set up.



### IDE

There are also more complex and powerful editors, so-called IDEs (Integrated Development Environments), such as [PyCharm], [Eclipse] or [KDevelop].
They have many advanced features that help programmers: auto-completion, renaming, running programs, managing virtual environments, and more. 
However, they are not very suitable for beginners.

If you still want to use such an editor, you should already know it quite well: know what the editor does for you and how to fix it when it does soething wrong.

Coaches usually only know one editor - the one they use - so they may not be able to quickly help with advanced IDE.

[PyCharm]: https://www.jetbrains.com/pycharm/
[Eclipse]: https://eclipse.org/
[KDevelop]: https://www.kdevelop.org/
