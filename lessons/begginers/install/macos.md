# Installing Python for macOS

Install the tool [Homebrew](http://brew.sh), which solves and simplifies the installation of applications and libraries that we will need for programming. How to do it?

Run the command in the command line: 

```console
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Then enter the following command and Python will be installed:

```console
$ brew install python3
``` 

Check that you have version 3.6 or higher.

```console
$ python3 --version
``` 


If "Python" and the version number appear (e.g. `Python 3.6.6`) and the version is 3.6 or higher, you have it installed. Otherwise, something is wrong; {% if var('coach-present') -%} consult with the coach. {%- else -%} try installing it again. If it doesn't work, consult with someone more experienced. {%- endif %}
