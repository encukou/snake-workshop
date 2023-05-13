This is a code in a programming language called Jinja. It defines a macro that creates two columns with titles 'Unix' and 'Windows'. Each column contains a code block that starts with either 'dosvenv' or 'console', depending on the title. The code block is followed by a call to another function that extracts a part of the code and dedents it.

"Environment settings"

In this section, you will:
* prepare a directory to save files for Python beginner courses, and
* activate a virtual environment.

"Preparing directory"

"Programmers create a lot of files and, more than with many other computer users, it matters to them where the files are stored."

The procedure below is by no means the only way to organize files. However, if you use this tried and tested method, it can greatly simplify the lives of those who will help you with any problems.

This is not a complete sentence, but rather a code snippet written in the programming language called "Jinja". However, here's a rough translation of what it does:

"If the variable 'pyladies' exists, set the variable 'rootname' to 'pyladies'. Otherwise, set the variable 'rootname' to 'naucse-python'."

"First, create a directory (folder) where you will have files for the Python course. It can be, for example, `{{ rootname }}` in your home directory. (You can also name it something else, but `{{ rootname }}` is used in the examples below.)"

"You must not move the selected directory after creating it. Therefore, I do not recommend creating it on the Desktop."

[note]
If you ever move the directory to another location, the *virtual environment* we will create in a moment will stop working. You would have to delete it and create a new one.

"You will need this directory for the rest of the course and for any subsequent courses. Therefore, note where it is exactly - copy its entire name, which you can then paste into `cd` in the command line or into a graphical file browser."

"Directory for every lesson."

"The new directory is currently empty. However, this will soon change and the more things there are in it, the more important it will be to have the content organized."

"To start, we will create a new subdirectory for each lesson of this course. To keep these directories nicely organized, we will number them: this first lesson will have the number '00', next you will create directory '01', and so on."

"All of them will be in your new directory that you created{{a}} a moment ago."

"Create the directory '00' now. You may not put anything in it today, but it will be useful to have it as an example for next time."

"Switching"

"Then open the command line and use the `cd` command to switch to the directory where you just created `00` (i.e. not directly into `00`). For example:"

The English translation of the Czech text ```console
$ cd {{ rootname }}
``` is: 

```console
$ cd {{ rootname }}
```

This is a command used in the terminal to change the current working directory to the directory specified by the variable "rootname".

Then check that you are in the right place:
* Use the command `pwd` (on Windows `cd`) to check that you are really in the newly created directory.
* Use the command `ls` (on Windows `dir`) to check that there is a subdirectory `00` in it.

"For example:"

{% first %}
Unix (Linux, macOS):
The command "pwd" prints the current working directory, which in this case is "/home/helena/{{rootname}}".

{% second %}
Windows:
N/A (This command is specific to Unix-based operating systems and does not work on Windows.)

The text is a command prompt output in Czech language. Here's the translation:

$ ls - This command lists the files and directories in the current directory.
00 - This is likely a directory name.
---
> cd - This command changes the current directory.
C:\Users\Helena\{{rootname}} - This is the new directory path that the user wants to navigate to.

The text appears to be a command prompt output in Czech language. Here is the translation:

"Directory of C:\Users\Helena\{{rootname}}"
This line shows the current directory path.

"05/08/2014 07:28 PM <DIR>  00"
This line shows the details of a directory named "00" which is located in the current directory. The date and time of creation/modification are also mentioned. The "<DIR>" indicates that it is a directory and not a file.

Virtual environment

"Now you will create a *virtual environment* for Python."

"Virtual environment is something that ensures that all computers will behave roughly the same. Once we set it up, I won't need separate instructions for Linux, Windows, and macOS."

[note]
In the future, you will also benefit from the second advantage: each virtual environment is separated from the others, so when you install a library (an extension for Python), it will only affect one virtual environment. If something goes wrong while working on a project, it will not endanger other projects on your computer.

"How to do it? It's different on every system!"

Linux.

Depending on how you have Python installed, one of the following commands will work. It will be faster to try them out than to describe which one is correct, so first try:

```console
$ python3 -m venv venv
```

This is a command used in the terminal to create a virtual environment for a Python project.

"And if you get the error `No module named venv`, try instead:"

The translation of the Czech text is: 

```console
$ virtualenv -p python3 venv
```

This text is a command in the terminal to create a virtual environment named "venv" using Python 3.

"macOS" is already in English and does not require translation. It is the name of the operating system developed by Apple Inc. for their Macintosh line of computers.

"python3 -m venv venv" is the same in both Czech and English. It is a command used in the terminal to create a virtual environment for a Python project.

* **Windows**:

"Depending on how you have Python installed, one of the following commands will work. It will be faster to try them out than to describe which one is correct, so try this first:"

This Czech text appears to be a code snippet written in the command line interface. Here is the translation to English:

```
> py -3 -m venv venv
```

This command creates a new virtual environment named "venv" using Python 3.

"And if you get an error `'py' is not recognized`, try instead:"

```doscon
> python3 -m venv venv
```

This command creates a new Python virtual environment named "venv".

"That created a directory called `venv`, which contains the virtual environment. You can look inside, but do not save your files there and never change anything there!"

Check that `00` and `venv` are nicely next to each other.

{% call sidebyside(titles=['Unix', 'Windows']) %}
$ ls
01
venv
---
> dir
 Directory of C:\Users\Helena\{{rootname}}
05/08/2014 07:28 PM <DIR>  00
05/08/2014 07:38 PM <DIR>  venv
{% endcall %}

The text shows a comparison between Unix and Windows commands for listing the contents of a directory. In Unix, the "ls" command is used, while in Windows, the "dir" command is used. The output shows the contents of the directory, which includes two subdirectories named "01" and "venv".

"In a graphical file browser, it looks like this, for example:"

The Czech text in the image reads "Directories '00' and 'venv' next to each other".

### Activation of the virtual environment

Finally, activate the virtual environment.

"Unix" and "Windows" are the titles of two sections. The text in the first section is a command that activates a virtual environment in Unix-based systems. The text in the second section is a command that activates a virtual environment in Windows-based systems.

If you use the command line in Visual Studio Code, the command for Windows is more complicated:
```doscon
> &powershell -ExecutionPolicy bypass
> venv/Scripts/Activate.ps1
```

After running this command, the word `(venv)` should appear at the beginning of the command line prompt (before `$` or `>`). This way you will know that the virtual environment is *active*.

"Write down the activation command."

"Whenever you run a command line to test your programs, you will need to switch to `{{rootname}}` using `cd` and enter this activation command."