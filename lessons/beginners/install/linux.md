# Installing Python on Linux

Installing Python on Linux is usually simple.
However, there are many types of Linux and we have the most experience with it, so these instructions are a bit longer.
Don't be afraid - you will probably skip most of the sections. :)

## Installation of Python 3

Python 3 is usually already present on Linux. To check it, run the command in the command line: 

```console
$ python3 --version
```

If you see 'Python' and the version number (for example `Python 3.6.6`) and the version is 3.6 or higher, you have it installed. Proceed to the next section, [check `tkinter`](#check-tkinter).

If "Python" version 3.5 or lower appears, 
{% if var('coach-present') -%}
consult with the coach.
{%- else -%}
update the system (or consult with someone who knows how to do it) and try again.
{%- endif %}

If you encounter `bash: python3: command not found` or a similar error, install Python.
The specific command depends on the distribution.

* **Fedora**:
  {% filter markdown(inline=True) %}
  ```console
  $ sudo dnf install python3
  ```
  {% endfilter %}
* **Ubuntu**:
  {% filter markdown(inline=True) %}
  ```console
  $ sudo apt-get install python3
  ```
  {% endfilter %}

If you are using a different distribution, I hope you already know how to install programs.

{{ anchor('check-tkinter') }}
## Checking Tkinter

Some Linux distributions only include a part of the overall functionality of Python by default.
Specifically, the `tkinter` library (which allows, for example, drawing "turtle graphics") often needs to be installed separately.
To check if it is already installed, enter the command:

```console
$ python3 -m tkinter
```

If a window appears, everything is okay. Close it and proceed to [installing `virtualenv`](#install-virtualenv).

If not, install the `tkinter` module.

* **Fedora**:
  {% filter markdown(inline=True) %}
  ```console
  $ sudo dnf install python3-tkinter
  ```
  {% endfilter %}

* **Ubuntu**:
  {% filter markdown %}
  ```console
  $ sudo apt-get install python3-tk
  ```
  {% endfilter %}


If you are using a different distribution, you must find the correct package name on the Internet.

{{ anchor('install-virtualenv') }}
## Installing Virtualenv

Newer versions of Python have a built-in tool called `venv`, which we will use below.
However, older versions do not have it (and some Linux distributions even removed it from Python).
Therefore, you need to find out if you have `venv` and, if necessary, install an alternative.

Run the command in the command prompt: 

```console
$ python3 -m ensurepip --version
``` 

If you see a listing starting with "pip", you have a functional `venv` installed. You can skip the rest of this section!

However, if the message "No module named ensurepip" appears, it is necessary to install an alternative, Virtualenv.

<!-- This doesn't happen on Fedora. -->

* **Ubuntu**:
  {% filter markdown(inline=True) %}
  ```console
  $ sudo apt-get install python-virtualenv
  ```
  {% endfilter %}

If you are using a different distribution, I hope you already know how to install programs.
