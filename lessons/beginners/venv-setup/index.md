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

# Environment setup

In this section, you will:
* prepare a directory for this workshop, and
* activate a virtual environment.

## Preparing a directory

Programmers create a lot of files. And they care where those files are stored.

The procedure below is by no means the only way to organize files,
but if everyone in the workshop uses it, it'll be easier for us to help you with any problems.

### A directory for the workshop

{% set rootname = 'learn-python' %}

First, create a directory (folder) for the workshop.
It can be, for example, `{{ rootname }}` in your home directory.
(You can name it differently, but `{{ rootname }}` is used in the examples below.)

You must not move this directory after creating it.
Therefore, I do not recommend creating it on the Desktop.

> [note]
> If you ever do move the directory to another location, the *virtual environment* we will create in a moment will stop working.
> In that case you will have to delete the environment and create a new one.

At the workshop, you will need to know where this directory is.
Note down its full name, which you can then paste into a graphical file browser or into `cd` in the command line.

We could use the directory directly, but let's organize things a bit more.
Create an additional directory inside `{{ rootname }}`, and name it `snake-workshop`.

### Switching to the directory

Then open the command line and use the `cd` command to switch to the directory `{{ rootname }}` (i.e. not all the way into `snake-workshop`).
For example:

 ```console
$ cd {{ rootname }}
```

Then check that you are in the right place:
* Use the command `pwd` (on Windows `cd`) to check that you are really in the newly created directory.
* Use the command `ls` (on Windows `dir`) to check that there is a subdirectory `snake-workshop` in it.

For example:

{% call sidebyside(titles=['Unix (Linux, macOS)', 'Windows']) %}
$ pwd
/home/helena/{{rootname}}

$ ls
snake-workshop
---
> cd
C:\Users\Helena\{{rootname}}

> dir
 Directory of C:\Users\Helena\{{rootname}}
05/08/2014 07:28 PM <DIR>  snake-workshop
{% endcall %}

## Virtual environment

Now you will create a *virtual environment* for Python.

A virtual environment is something that ensures that all computers on the workshop will behave roughly the same.
Once we set it up, we won't need separate instructions for Linux, Windows, and macOS.

> [note]
> In the future, you will also benefit from the second advantage: each virtual environment is separated from the others, so when you install a library (an extension for Python), it will only affect one virtual environment.
> If something goes wrong while working on one project, it will not endanger other projects on your computer.

How to do it? It's different on every system!

### Linux:

Depending on how you have Python installed, one of the following commands will work.
It will be faster to try them out than to describe which one is correct, so first try:

```console
$ python3 -m venv venv
```

And if you get the error `No module named venv`, try instead:

```console
$ virtualenv -p python3 venv
```

### macOS:

```console
   $ python3 -m venv venv
 ```

### Windows:

Depending on how you have Python installed, one of the following commands will work.
It will be faster to try them out than to describe which one is correct, so try this first:

```doscon
> py -3 -m venv venv
```

And if you get an error like `'py' is not recognized`, try instead:

```doscon
> python3 -m venv venv
```

That created a directory called `venv`, which contains the virtual environment.
You can look inside, but do not save your files there and never change anything there!

Check that `snake-workshop` and `venv` are nicely next to each other.

{% call sidebyside(titles=['Unix', 'Windows']) %}
$ ls
snake-workshop
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

Finally, *activate* the new virtual environment:

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

When you open the command line at the workshop, you will need to switch to `{{rootname}}` using `cd` and enter this activation command.
