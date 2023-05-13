# Installing Python on Linux

"Installing Python on Linux is usually simple. However, there are many types of Linux and we have the most experience with it, so these instructions are a bit longer. Don't be afraid - you will probably skip most of the sections. :)"

Translation: Installation of Python 3

"Python 3 is usually already present on Linux. To check it, run the command in the command line: "

The English translation of the Czech text is:

```console
$ python3 --version
```

Note: This is a command used in a terminal to check the version of the Python 3 programming language installed on the system.

"If you see 'Python' and the version number (for example `Python 3.6.6`) and the version is 3.6 or higher, you have it installed. Proceed to the next section, [check `tkinter`](#check-tkinter)."

If "Python" version 3.5 or lower appears, 
{% if var('coach-present') -%}
consult with the coach.
{%- else -%}
update the system (or consult with someone who knows how to do it) and try again.
{%- endif %}

If you encounter `bash: python3: command not found` or a similar error, install Python.
The specific command depends on the distribution.

* **Fedora**:
  ```
  $ sudo dnf install python3
  ```
  
* **Ubuntu**:
  ```
  $ sudo apt-get install python3
  ```

"If you are using a different distribution, I hope you already know how to install programs."

## Checking Tkinter

"Some Linux distributions only include a part of the overall functionality of Python by default. Specifically, the `tkinter` library (which allows, for example, drawing "turtle graphics") often needs to be installed separately. To check if it is already installed, enter the command:"

```console
$ python3 -m tkinter
```

This is a command used in the terminal to run the tkinter module in Python 3.

"If a window appears, everything is okay. Close it and proceed to [installing `virtualenv`](#install-virtualenv)."

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

The text provides instructions on how to install the `python3-tk` package on Fedora and Ubuntu operating systems using the command line.

"If you are using a different distribution, you must find the correct package name on the Internet."

## Installing Virtualenv

"Newer versions of Python have a built-in tool called `venv`, which we will use below. However, older versions do not have it (and some Linux distributions even removed it from Python). Therefore, you need to find out if you have `venv` and, if necessary, install an alternative."

"Run the command in the command prompt: "

The English translation of the Czech text is: 

```console
$ python3 -m ensurepip --version
``` 

There is no need to translate this text as it is a command written in English and used in a terminal or command prompt.

If you see a listing starting with "pip", you have a functional `venv` installed. You can skip the rest of this section!

However, if the message "No module named ensurepip" appears, it is necessary to install an alternative, Virtualenv.

"<!-- na Fedoře se tohle nestává -->" translates to "This doesn't happen on Fedora."

* **Ubuntu**:
  {% filter markdown(inline=True) %}
  ```console
  $ sudo apt-get install python-virtualenv
  ```
  {% endfilter %}

This is a command to install `python-virtualenv` on Ubuntu operating system using the `apt-get` package manager with superuser privileges.

"If you are using a different distribution, I hope you already know how to install programs."