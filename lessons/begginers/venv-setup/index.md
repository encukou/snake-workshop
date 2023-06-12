{%- macro sidebyside(titles=['Unix', 'Windows'], code=True) -%}
    <div class="row side-by-side-commands">
        {%- for title in titles -%}
            <div class="col">
                <h4>{{ title }}</h4>
{%- filter markdown() -%}
{%- if code -%}```
    {%- if title.lower().startswith('win') -%}dosvenv{%- else -%}console{%- endif -%}
{%- endif -%}
{{ caller() | extract_part(loop.index0, '---') | dedent }}
{%- if code -%}```{%- endif -%}
{%- endfilter -%}
            </div>
        {%- endfor -%}
    </div>
{%- endmacro -%}

# Environment settings

In this section, you will:
* prepare a directory to save files for Python beginner courses, and
* activate a virtual environment.

## Preparing directory

Programmers create a lot of files and, more than with many other computer users, it matters to them where the files are stored.

The procedure below is by no means the only way to organize files.
However, if you use this tried and tested method, it can greatly simplify the lives of those who will help you with any problems.

{%- if var('pyladies') -%}
{% set rootname = 'pyladies' %}
{%- else -%}
{% set rootname = 'learn-python' %}
{%- endif %}

First, create a directory (folder) where you will have files for the Python course.
It can be, for example, `{{ rootname }}` in your home directory.
(You can also name it something else, but `{{ rootname }}` is used in the examples below.)

You must not move the selected directory after creating it. Therefore, I do not recommend creating it on the Desktop.

> [note]
> If you ever move the directory to another location, the *virtual environment* we will create in a moment will stop working.
> You would have to delete it and create a new one.

You will need this directory for the rest of the course and for any subsequent courses.
Therefore, note where it is exactly - copy its entire name, which you can then paste into `cd` in the command line or into a graphical file browser.

### Directory for every lesson

The new directory is currently empty.
However, this will soon change and the more things there are in it, the more important it will be to have the content organized.

To start, we will create a new subdirectory for each lesson of this course.
To keep these directories nicely organized, we will number them: this first lesson will have the number '00', next you will create directory '01', and so on.

All of them will be in your new directory that you created a moment ago.

Create the directory '00' now.
You may not put anything in it today, but it will be useful to have it as an example for next time.

### Switching

Then open the command line and use the `cd` command to switch to the directory where you just created `00` (i.e. not directly into `00`).
For example:

 ```console
$ cd {{ rootname }}
```

Then check that you are in the right place:
* Use the command `pwd` (on Windows `cd`) to check that you are really in the newly created directory.
* Use the command `ls` (on Windows `dir`) to check that there is a subdirectory `00` in it.

For example:

{% call sidebyside(titles=['Unix (Linux, macOS)', 'Windows']) %}
$ pwd
/home/helena/{{rootname}}

$ ls
00
---
> cd
C:\Users\Helena\{{rootname}}

> dir
 Directory of C:\Users\Helena\{{rootname}}
05/08/2014 07:28 PM <DIR>  00
{% endcall %}

## Virtual environment

Now you will create a *virtual environment* for Python.

Virtual environment is something that ensures that all computers will behave roughly the same.
Once we set it up, I won't need separate instructions for Linux, Windows, and macOS.

> [note]
> In the future, you will also benefit from the second advantage: each virtual environment is separated from the others, so when you install a library (an extension for Python), it will only affect >one virtual environment.
> If something goes wrong while working on a project, it will not endanger other projects on your computer.

How to do it? It's different on every system!

* **Linux**.

Depending on how you have Python installed, one of the following commands will work.
It will be faster to try them out than to describe which one is correct, so first try:

```console
$ python3 -m venv venv
```

And if you get the error `No module named venv`, try instead:

```console
$ virtualenv -p python3 venv
```

* ***macOS**

```console
   $ python3 -m venv venv
 ```

* **Windows**:

Depending on how you have Python installed, one of the following commands will work.
It will be faster to try them out than to describe which one is correct, so try this first:

```doscon
> py -3 -m venv venv
```

And if you get an error `'py' is not recognized`, try instead:

```doscon
> python3 -m venv venv
```

That created a directory called `venv`, which contains the virtual environment.
You can look inside, but do not save your files there and never change anything there!

Check that `00` and `venv` are nicely next to each other.

{% call sidebyside(titles=['Unix', 'Windows']) %}
$ ls
00
venv
---
> dir
 Directory of C:\Users\Helena\{{rootname}}
05/08/2014 07:28 PM <DIR>  00
05/08/2014 07:38 PM <DIR>  venv
{% endcall %}

In a graphical file browser, it looks like this, for example:

 {{ figure(
    img=static('dirs-00.png'),
    alt="(adresáře '00' a 'venv' vedle sebe)",
) }}


### Activation of the virtual environment

Finally, activate the virtual environment.

{% call sidebyside(titles=['Unix', 'Windows'], code=False) %}
```console
$ source venv/bin/activate
```
---
```doscon
> venv\Scripts\activate
```

If you use the command line in Visual Studio Code, the command for Windows is more complicated:
```doscon
> &powershell -ExecutionPolicy bypass
> venv/Scripts/Activate.ps1
```
{% endcall %}
 
After running this command, the word `(venv)` should appear at the beginning of the command line prompt (before `$` or `>`). This way you will know that the virtual environment is *active*.

Write down the activation command.

Whenever you run a command line to test your programs, you will need to switch to `{{rootname}}` using `cd` and enter this activation command.
