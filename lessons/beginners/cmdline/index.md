{%- macro sidebyside(titles=['Unix', 'Windows']) -%}
    <div class="row side-by-side-commands">
        {%- for title in titles -%}
            <div class="col">
                <h4>{{ title }}</h4>
{%- filter markdown() -%}
```{%- if title.lower().startswith('win') -%}dosvenv{%- else -%}console{%- endif -%}
{{ caller() | extract_part(loop.index0, '---') | dedent }}
```
{%- endfilter -%}
            </div>
        {%- endfor -%}
    </div>
{%- endmacro -%}

# Command line

Let us introduce you to your first new friend: the *command line*!

This is the black window all hackers use.
It might look a bit scary at first but really it's just a prompt waiting for commands from you.

## What is the command line?

The command line is a text-based application for controlling your computer.
Other names for it are: *cmd*, *command-line interface* *(CLI)*, *prompt*, *console* or *terminal*.

It can be used for viewing, handling, and manipulating files, much like Windows Explorer or Finder on the Mac, but without the graphical interface.
Instead of clicking, you'll type in commands using a keyboard!

Why do it this way? Graphical windows and buttons are familiar to most people, but they have two disadvantages:
* they often differ between different computers, so fewer people will be able to help you with "your" version, and
* text can be easily copied around, which makes it easy to collaborate via email or chat.

Although it may not be the easiest way to start,
this workshop is about giving you a taste of what programmers do,
so we're starting here.


## Opening the command line

The way to open the command line (also known as *console* or *terminal*) is different on different systems:

* **Windows**: go to the Start menu → type "cmd" on the keyboard → select *Command Prompt*
* **macOS**: go to Applications → Utilities → Terminal
* **Linux** (GNOME): Activities → search for "Terminal"
* **Linux** (KDE): Main Menu → search for "Konsole"

If you don't know what to do, try Googling or asking someone more experienced.

After opening the console, you will be greeted by a *prompt*: a line that asks you to enter a command.
The prompt ends with the character `$` on Unix systems (such as Linux and macOS); and with `>` on Windows.

Before the `$` or `>` symbol, there will probably be some additional information, which is different on each computer.
The examples here (like most other instructions you find on the internet) will omit that information, and just show the final `$` or `>` like this:

{% call sidebyside(titles=['Unix (Linux, macOS)', 'Windows']) %}
$
---
>
{% endcall %}

## Font size

On Windows, if the font is too small, click on the window icon and select Options.
In the Font tab, you can then choose a larger font.

{{ figure(
     img=static('windows-cmd-properties.png'),
     alt='Screenshot of command prompt menu',
) }}

On other systems, look for settings or try
<kbd>Ctrl</kbd>+<kbd>+</kbd> and
<kbd>Ctrl</kbd>+<kbd>-</kbd> (or with Shift).


# Your first command

Let's start with your first command: `whoami` (the question *“who am I”* without spaces).
Type it after the `$` or `>` and press <kbd>Enter</kbd>.
Your login name will appear.
For example, if your name was <var>Helena</var> the conversation would look like this:

{% call sidebyside() %}
$ whoami
helena
---
> whoami
computer\Helena
{% endcall %}

>[note]
>The character `$` or `>` in this example is only there to make it clear that you are entering a command into the command line.
>The computer will display it, usually with something before it, so 
>don't type it in! Just enter `whoami` and press <kbd>Enter</kbd>.
>
>Similarly, the computer will display the login name on its own.

Let's try some more commands!
Each computer can have a slightly different set of commands, so make sure to follow instructions for your operating system.


## Current directory

It'd be nice to know where are we now, right?

The command line always works in some *directory*, also known as a *folder*
(these mean one and the same thing).

The command `pwd` or `cd` (from *print working directory* or *current directory*) will tell you in which directory you currently are.
Try it! You'll see something like this:

{% call sidebyside() %}
$ pwd
/home/helena/
---
> cd
C:\Users\helena
{% endcall %}

The current directory is usually also displayed somewhere in the command line prompt, before the `$` or `>` sign.
But in the future, you may have to work on a computer that displays it differently or not at all, so it's good to know the `pwd`/`cd` command.

You might be familiar with a “current directory” from the window used to select files in graphical programs.
Typically, this  window shows the contents of a single directory.

The command line can also show what's in the current directory, but you have to ask for it.


## What is in the directory?

The command `ls` or `dir` (short for *list* or *directory*) will show you what the current directory contains: all the files, including subdirectories.
Try it!

{% call sidebyside() %}
$ ls
Applications
Desktop
Downloads
Music
…
---
> dir
 Directory of C:\Users\helena
05/08/2014 07:28 PM <DIR>  Applications
05/08/2014 07:28 PM <DIR>  Desktop
05/08/2014 07:28 PM <DIR>  Downloads
05/08/2014 07:28 PM <DIR>  Music
…
{% endcall %}


## Changing the current directory

Now, let's go to your `Desktop` directory.
(If you don't see Desktop in the output from `ls` or `dir`, choose a different
one.)

Type `cd`, a space, and the name of the directory you want to go to.

If you use Linux or macOS, be careful with letter case: on these systems, `Desktop` and `desktop` are two different names.

{% call sidebyside() %}
$ cd Desktop
$ pwd
/home/helena/Desktop
---
> cd Desktop
> cd
C:\Users\helena\Desktop
{% endcall %}

Afterwards, verify that you are in the right place using `pwd` or `cd`.

If you use Windows, you have already used `cd` - this command behaves differently depending on whether you write something after it or not.

>[note] Note for Windows
>If you are switching to a directory on a different drive, for example `D:` instead of `C:`,
>you need to enter the name of the drive with a colon (for example, `D:`) as a separate command, in addition to `cd`.

> [note] PRO tip
> If you type `cd D` and then hit <kbd>tab</kbd> on your keyboard,
> the command line will automatically fill in the rest of the name
> so you can navigate faster.
> If there is more than one folder starting with *D*,
> hit the <kbd>tab</kbd> key twice to get a list of options.

## Creating a directory

How about creating a practice directory on your desktop?
For that you can use the command `mkdir` (short for *make directory*) followed
by the name of the directory you want to create.
Try it:

{% call sidebyside() %}
$ mkdir test
---
> mkdir test
{% endcall %}

After you do this, try to list the current directory using `ls` or `dir`.
One of the listed directories will be the newly created `test`.

Next, navigate to the new directory it in the same way
as to `Desktop` a moment ago:

{% call sidebyside() %}
$ cd test
---
> cd test
{% endcall %}

## Using a graphical window

The command line is powerful, but sometimes it's not the right tool for what you need to do.
Let's learn how to open the command line's current directory elsewhere.

Open your system's file browser.

<div class="row side-by-side-commands">
    <div class="col">
        <h4>Linux</h4>
        {{ figure(
            img=static('linux-file-browser.png'),
            alt='Screenshot programu Nautilus na GNOME',
        ) }}
    </div>
    <div class="col">
        <h4>macOS</h4>
        {{ figure(
            img=static('macos-file-browser.png'),
            alt='Screenshot programu Finder na macOS',
        ) }}
    </div>
    <div class="col">
        <h4>Windows</h4>
        {{ figure(
            img=static('windows-file-browser.png'),
            alt='Screenshot průzkumníka na Windows',
        ) }}
    </div>
</div>

You can navigate by clicking around, but that can take too long and sometimes you can get lost.
Let's instead copy a directory name from the command line and paste it into the file browser.

First, you need something to copy.
Use `cd` or `pwd` to display the full name of your current directory, `test`:

{% call sidebyside() %}
$ pwd
/home/helena/Desktop/test
---
> cd
C:\Users\helena\Desktop\test
{% endcall %}

### Copying from the command line

Unfortunately, the way to copy text is different on every system.
Even more unfortunately, on most systems you can't use the well-known shortcuts <kbd>Ctrl</kbd>+<kbd>C</kbd> and <kbd>Ctrl</kbd>+<kbd>V</kbd> to copy/paste in the command line.

On Linux, select the text with your mouse and then either:
* right-click and select *Copy*, or
* press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>C</kbd>.
(Note that in the command line, you must add Shift to the usual copy shortcut.)

On macOS, select the text with your mouse and then press <kbd>⌘ Command</kbd>+<kbd>C</kbd>.

On Windows, in the command prompt menu (icons in the upper left corner), select *Edit* → *Mark*, select the text with your mouse, and copy it using <kbd>Enter</kbd>.

### Opening in a file browser

On **Linux**, depending on the file browser you are using, either:
* press <kbd>Ctrl</kbd>+<kbd>L</kbd> and insert the directory name using
  <kbd>Ctrl</kbd>+<kbd>V</kbd>, or
* select the directory name at the top, delete it, and insert a new one using
  <kbd>Ctrl</kbd>+<kbd>V</kbd>.
In both cases, confirm with <kbd>Enter</kbd>.

On **macOS**, select the *Go* menu → *Go to Folder*, paste the directory name using
<kbd>⌘ Command</kbd>+<kbd>V</kbd> and confirm by pressing <kbd>Enter</kbd>.

On **Windows**, click on the name of the directory at the top.
This will make the text editable.
Delete the existing directory and use <kbd>Ctrl</kbd>+<kbd>V</kbd> to paste the new one instead.
Confirm with <kbd>Enter</kbd>.

Now, you should have Desktop open in your graphical window.
Check that you can see `test`, the directory you created earlier.

### Inserting back into the command line

Sometimes you'll open a directory in the file browser and you will want to switch to it in the command line.

Copy the directory name from the file browser. (You might need to make the text editable, as when pasting.)

Then, paste it into the command line.
The shortcut for that can again be different than what you're used to:

* Linux: <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>V</kbd> 
* macOS: <kbd>⌘ Command</kbd>+<kbd>V</kbd> 
* Windows: Menu *Edit* → *Paste* 

> [note]
> If there are spaces or other special characters such as `*#$%^()><;"?` in the name, you must enclose it in quotes in the command line. Before and after the name, type `"`, for example:
>
>```console
>$ cd "my super directory"
>```
>
> You can also rename directories and files to remove any spaces
> and special characters.
> That'll make them easier to work with in the command line.

## Observing changes

The files on your computer can be manipulated by both graphical programs and the command line.
Let's test that!

In your graphical browser, you should have the command line's current directory open. Create a new file or directory there.
Then switch to the command line, and use `ls` or `dir` to check that it was actually created.
Now delete it in the graphical program – and verify that you can't see it any more in the command line.

## One level up

Remember `cd`? There's one more trick you'll need.
If you are now in the directory `Desktop/test` or `Desktop\test`, how do you get back to `Desktop`?

The command `cd Desktop` will not work: it would tell the computer to switch to `Desktop` *in the current directory*, or `Desktop/test/Desktop`.
But there's no directory like that.
And the command line does not dare second-guess what you mean.

The *parent* directory (the one contains the current one) has a special name: `..` ­– two dots.
Go to it by typing `cd ..` and then make sure that you are really back in `Desktop`.

{% call sidebyside() %}
$ cd ..
$ pwd
/home/helena/Desktop
---
> cd ..
> cd
C:\Users\helena\Desktop
{% endcall %}

Another `cd ..` would move you to the next parent directory - in our example, `helena`.

## The end

There are many more commands you can use on the command line.

When you learn them, you can fully control the computer just using text: create files, delete them, run programs, change settings, and so on.
However, it would take a separate course to cover all of that.

So let's wrap up with just one more command – one that closes the command line:

```console
$ exit
```

This command is the same on all systems, so I didn't give a separate example for Windows.
And in the single example, I used the Unix-style prompt, `$` rather than `>`.
Many online tutorials do that.
They mean the same thing: the computer is asking for your command.

## Overview

Here is a table of basic commands that you will need to get started.

<table class="table">
    <tr>
        <th>Unix</th>
        <th>Windows</th>
        <th>Description</th>
        <th>Example</th>
    </tr>
    <tr>
        <td><code>cd <var>directory</var></code></td>
        <td><code>cd <var>directory</var></code></td>
        <td>Change directory</td>
        <td><code>cd test</code><br><code>cd ..</code></td>
    </tr>
    <tr>
        <td><code>pwd</code></td>
        <td><code>cd</code></td>
        <td>Print working directory</td>
        <td><code>pwd</code><br><code>cd</code></td>
    </tr>
    <tr>
        <td><code>ls</code></td>
        <td><code>dir</code></td>
        <td>List directory contents</td>
        <td><code>ls</code><br><code>dir</code></td>
    </tr>
    <tr>
        <td><code>exit</code></td>
        <td><code>exit</code></td>
        <td>Exit</td>
        <td><code>exit</code></td>
    </tr>
</table>

There are many others, and we'll learn about them when as we need them.
