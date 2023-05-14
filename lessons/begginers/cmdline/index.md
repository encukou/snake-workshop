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

In this lesson, we will become familiar with the *command line* - a black window used by programmers to enter text commands.

For most of what the command line can do, you can also use something else - an icon on the desktop, a special program or editor, a web application - but these tricks have two disadvantages:
* they often differ between different computers, so fewer people will be able to help you with "your" version, and
* text can be easily copied from the command line, which simplifies collaboration via email or chat.

At first glance, it may look unnatural, but you can get used to it.

Although it may not be the easiest way to start programming, mastering the basics of working with the command line will definitely pay off in the long run. And that's what this course is about.

The command line (or program, also known as *console* or *terminal*;
in English, *command line*, *console*, *terminal*) is opened differently on different systems:

* Windows (Czech): Start → type "cmd" on the keyboard → Command Prompt
* Windows (English): Start → type "cmd" on the keyboard → Command Prompt
* macOS (English): Applications → Utilities → Terminal
* Linux (GNOME, Czech): Activities → search for "Terminál"
* Linux (GNOME, English): Activities → search for "Terminal"
* Linux (KDE): Main Menu → search for "Konsole"

If you don't know what to do, try either Googling or asking someone more experienced.

After opening the console, you will be greeted by a *prompt*: a line that prompts you to enter a command. The prompt ends on Unix systems (such as Linux and macOS) with the character `$`; on Windows, it ends with the character `>`.

Before the symbol '$' or '>' there will probably be some additional information, which is, however, omitted in these materials. And it will also be omitted in most other instructions you find on the internet. Because every computer can be a little different.

{% call sidebyside(titles=['Unix (Linux, macOS)', 'Windows']) %}
$
---
>
{% endcall %}

According to the system, the actual commands you will be entering will also differ: Unix systems (Linux and macOS) understand different commands than Windows.

>[Note] Font size
>If the font in Windows is too small, click on the window icon and select Options.
>In the Font tab, you can then choose a larger font.
><!-- XXX: are the Czech names correct? -->
>
>{{ figure(
     img=static('windows-cmd-properties.png'),
     alt='Screenshot of command prompt menu',
) }}
>
>On other systems, look for settings or try
><kbd>Ctrl</kbd>+<kbd>+</kbd> and
><kbd>Ctrl</kbd>+<kbd>-</kbd> (or with Shift).

# First command

Let's start with a command that is the same everywhere. Type `whoami` (from English *who am I?*) and press <kbd>Enter</kbd>. Your login name will appear. For example, for Helena it would look like this:

{% call sidebyside() %}
$ whoami
helena
---
> whoami
pocitac\Helena
{% endcall %}

>[note]
>The character `$` or `>` in the example is only there to make it clear that you are entering a command into the command line. The computer will display it, usually with something before it, so >don't type it {{gnd('alone')}}! Just enter `whoami` and press <kbd>Enter</kbd>.
>
>Similarly, the computer will display the login name on its own.

## Current directory

The command line always works in some *directory*, also known as a *folder*. "Directory" and "folder" are synonyms, you can use either of them.

The command that is called `pwd` or `cd` (from *print working directory* or *current directory*) will tell you in which directory you currently are in the system.

{% call sidebyside() %}
$ pwd
/home/helena/
---
> cd
C:\Users\helena
{% endcall %}

The second line "> cd C:\Users\helena" is a command used in Windows operating systems, which stands for "change directory". It changes the current directory to "C:\Users\helena".

The current directory is usually displayed in the command line prompt, before the `$` or `>` sign. But it's good to know `pwd`/`cd` just in case you get lost. Sometimes it's displayed in a shortened form. And in the future, you may have to work on a computer that displays something else before the `$` sign.

You may know something like the current directory from graphic programs where you select files: typically, the upper (or lower on Mac) part shows which directory is currently being displayed. The command line can also show files, but you have to ask for it.

## What is in the directory?

The command `ls` or `dir` (from English *list* - enumerate, respectively *directory* - folder) will show you what the current directory contains: all files, including subdirectories, that are located in the current directory.

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
     
     
## Change of the current directory

The current directory can be changed using the `cd` command (from English 'change directory'). After `cd`, write the name of the directory you want to go to. If you have a directory named `Desktop` or `Plocha`, go there. Then don't forget to verify that you are in the right place.

If you use Linux or macOS, be careful with letter case: on these systems, `Desktop` and `desktop` are two different names.

If you use Windows, you have already used `cd` - this command behaves differently depending on whether you write something after it or not.

{% call sidebyside() %}
$ cd Desktop
$ pwd
/home/helena/Desktop
---
> cd Desktop
> cd
C:\Users\helena\Desktop
{% endcall %}

>[note] Note for Windows
>If you are switching to a directory on a different disk, for example `D:` instead of `C:`, you need to enter the name of the disk with a colon as a special command in addition to `cd` (for >example, `D:`).

## Creating a directory

How about trying to create a directory? This is done by the command 'mkdir' (from English 'make directory'). After this command, write the name of the directory you want to create - in our case 'zkouska'."

{% call sidebyside() %}
$ mkdir zkouska
---
> mkdir zkouska
{% endcall %}

When the directory is created, you can navigate to it similarly as you {{gnd('went', 'went')}} to `Desktop` or `Plocha` a moment ago.

{% call sidebyside() %}
$ cd zkouska
---
> cd zkouska
{% endcall %}     

List the contents of the current directory using `ls` or `dir` now. One of the listed directories will be `zkouska`.

## In the graphic search tool

You will not often work *only* with the command line. It pays off to be able to open the current directory from the command line in other programs as well.

Open the file browser. This program is different on every system.

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

Maybe you know how to navigate to the directory that is active in the command line by clicking "navigate to" in this program. However, in the future, it will be more complicated, so it will be good to try copying the text from the command line and pasting it into the file browser.

Unfortunately, it is done differently on every system. And because the well-known shortcut <kbd>Ctrl</kbd>+<kbd>C</kbd> and <kbd>Ctrl</kbd>+<kbd>V</kbd> do something different in the command line than copying, it is probably done differently than you are used to.

First, use the command `cd` or `pwd` to have the full name of the directory `zkouska` printed out.

{% call sidebyside() %}
$ pwd
/home/helena/Desktop/zkouska
---
> cd
C:\Users\helena\Desktop\zkouska
{% endcall %}


### Copying from the command line.

On Linux, select the text with your mouse and then either:
* right-click and select *Copy*, or
* press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>C</kbd>.
(Note that in the command line, you must use Shift in addition.)

On macOS, select the text with your mouse and then press <kbd>⌘ Command</kbd>+<kbd>C</kbd>.

On Windows, in the command prompt menu (icons in the upper left corner), select *Edit* → *Mark*, select the text with your mouse, and copy it using <kbd>Enter</kbd>.

### Opening in a file browser

It depends on the program you are using on **Linux**. Either:
* press <kbd>Ctrl</kbd>+<kbd>L</kbd> and insert the directory name using
  <kbd>Ctrl</kbd>+<kbd>V</kbd>, or
* select the directory name at the top, delete it, and insert a new one using
  <kbd>Ctrl</kbd>+<kbd>V</kbd>.
In both cases, confirm with <kbd>Enter</kbd>.

On **macOS**, select the *Go* menu → *Go to Folder*, paste the directory name using
<kbd>⌘ Command</kbd>+<kbd>V</kbd> and confirm by pressing <kbd>Enter</kbd>.

On Windows, click on the name of the directory at the top. This will convert it to editable text. Delete it and use <kbd>Ctrl</kbd>+<kbd>V</kbd> to paste the new name instead. Confirm with <kbd>Enter</kbd>.

Now you can look at the Desktop or in some graphic program for browsing directories: you will find that the directory was really created.

### Inserting into the command line.

Sometimes you open a file in the file browser and you will want to switch to it in the command line. Copying the directory name should not be a problem; however, pasting it into the command line can be different than in other programs.

* Linux: <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>V</kbd> 
* macOS: <kbd>⌘ Command</kbd>+<kbd>V</kbd> 
* Windows: Menu *Edit* → *Paste* 

> [note]
> If there are spaces or other special characters such as `*#$%^()><;"?` in the name, you must enclose it in quotes in the command line: before and after the name, type `"`, for example:
>
>```console
>$ cd "my super directory"
>```

However, it is better not to use spaces and special characters in file names.

## Observation of Changes

"ry to see that changes you make to the text on the computer will also be reflected in the document.

In a graphical browser that looks at the same directory that is active in your command line, create a new file or directory. Then, using the command `ls` or `dir`, check that it was actually created. Then delete it in the graphical program - and make sure in the command line that it is really deleted.

On the computer, you have only one set of files that can be manipulated by both graphic programs and command line.

## One level up

And the last thing: if you are now in the directory `Desktop/zkouska` (or `Plocha/zkouska`, `Desktop\zkouska`, etc.), how do you get back to `Desktop`?

The command `cd Desktop` will not work: it would tell the computer to switch to the `Desktop` directory *in the current directory*. But there is no `Desktop` directory in the `zkouska` directory! On the contrary, `zkouska` is in `Desktop`. Technically speaking, the `Desktop` directory is *superior* to the current directory.

The parent directory has a special name `..`, which consists of two dots. Go to it by typing `cd ..` and then make sure that you are really in `Desktop`.

{% call sidebyside() %}
$ cd ..
$ pwd
/home/helena/Desktop
---
> cd ..
> cd
C:\Users\helena\Desktop
{% endcall %}

Another `cd ..` would move you to another parent directory - in our example, `helena`.

## The End

There are of course many more commands.

When you learn them, you can fully control the computer from the command line: create files, delete them, run programs, change settings, and so on. However, it would take a separate course to cover all of that, so we'll stop here.

Try one more command, the one that closes the command line: `exit`.

The command "exit" works the same on all systems. The same applies to surprisingly many commands (except for the basic ones like "cd", "pwd", and "ls"). Therefore, in the rest of these materials, I will not use examples that are specific to a particular operating system.

And I will be using the Unix prompt `$`. You will come across this convention in most online tutorials. If you are using Windows, it is good to get used to `$` even though your command line uses `>` instead.

Try then what the command 'exit' does.

```console
$ exit
```
     
And that's the introduction to the command line done.

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
        <td>change directory</td>
        <td><code>cd test</code><br><code>cd ..</code></td>
    </tr>
    <tr>
        <td><code>pwd</code></td>
        <td><code>cd</code></td>
        <td>print working directory</td>
        <td><code>pwd</code><br><code>cd</code></td>
    </tr>
    <tr>
        <td><code>ls</code></td>
        <td><code>dir</code></td>
        <td>list directory contents</td>
        <td><code>ls</code><br><code>dir</code></td>
    </tr>
    <tr>
        <td><code>exit</code></td>
        <td><code>exit</code></td>
        <td>exit</td>
        <td><code>exit</code></td>
    </tr>
</table>

We will explain further commands such as `python` or `git` when they are needed, after you install them.
