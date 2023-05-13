# Installing Python for macOS

Install the tool [Homebrew](http://brew.sh), which solves and simplifies the installation of applications and libraries that we will need for programming. How to do it?

"Run the command in the command line: "

This is a command to install Homebrew on a macOS system. Here's the translation: 

```console
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Translated: 

```console
Execute the following command to install Homebrew on macOS:
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

"Then enter the following command and Python will be installed:"

```console
$ brew install python3
``` 

This command installs Python 3 using Homebrew package manager on a Mac computer.

"Check that you have version 3.6 or higher."

The translation of the Czech text is: ```console
$ python3 --version
``` 

Note that this is a command line instruction to check the version of Python 3 installed on the system.

"If "Python" and the version number appear (e.g. `Python 3.6.6`) and the version is 3.6 or higher, you have it installed. Otherwise, something is wrong; {% if var('coach-present') -%} consult with the coach. {%- else -%} try installing it again. If it doesn't work, consult with someone more experienced. {%- endif %}"