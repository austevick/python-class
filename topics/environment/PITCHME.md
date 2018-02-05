## Environment Setup
+++
### Setting Up Python
Setting up python will be different depending on your operating system

+++
To have a good development environment, we will need 3 things:
- An installed version of python
- An installed version of pip |
- An installed version of virtualenv |
- An installed Text Editor or IDE |

+++
For Mac and Linux, you should already have python installed. You can verify this by running:
```
my-laptop:~ austevick$ python -V
Python 2.7.13
my-laptop:~ austevick$
```

+++
Next, install virtualenv:
```
my-laptop:~ austevick$ sudo pip install virtualenv
```

+++
For macs, I suggest you setup homebrew. Homebrew is a package manager for Mac.

+++

First, make sure you have a C compiler installed. This will be used by python to install any C dependencies. If you already have it, you should see an error saying the tools are already installed
```
my-laptop:~ austevick$ xcode-select --install
xcode-select: error: command line tools are already installed, use "Software Update" to install updates
my-laptop:~ austevick$
```
+++

Next we need to install homebrew, a package manager for Mac
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
The script will explain what changes it will make and prompt you before the installation begins.

+++
Now we need to update our `PATH` to point to the directory homebrew will be installing things. You can do this by editing your .bash_profile (Create this file if it does not exist.)
```
my-laptop:~ austevick$ nano ~/.bash_profile
```
Now add in following line and save the file
```
export PATH=/usr/local/bin:/usr/local/sbin:$PATH
```

+++
For Windows users, I suggest you go through this walk through:
[Installing Python 2 on Windows](http://docs.python-guide.org/en/latest/starting/install/win/)

+++
First, download the [latest version](https://www.python.org/ftp/python/2.7.14/python-2.7.14.msi) of Python 2.7 from the official website. If you want to be sure you are installing a fully up-to-date version, click the Downloads > Windows link from the home page of the Python.org web site .

The Windows version is provided as an MSI package. To install it manually, just double-click the file. The MSI package format allows Windows administrators to automate installation with their standard tools.

By design, Python installs to a directory with the version number embedded, e.g. Python version 2.7 will install at C:\Python27\, so that you can have multiple versions of Python on the same system without conflicts. Of course, only one interpreter can be the default application for Python file types. It also does not automatically modify the PATH environment variable, so that you always have control over which copy of Python is run.

+++
Typing the full path name for a Python interpreter each time quickly gets tedious, so add the directories for your default Python version to the PATH. Assuming that your Python installation is in C:\Python27\, add this to your PATH:
```
C:\Python27\;C:\Python27\Scripts\
```
You can do this easily by running the following in powershell:
```
[Environment]::SetEnvironmentVariable("Path", "$env:Path;C:\Python27\;C:\Python27\Scripts\", "User")
```
+++
Next, verify if python is installed:
```
command -v pip
```
If it is not installed, [follow the steps in this guide](https://pip.pypa.io/en/latest/installing/)

+++
Lastly, install virtualenv:
```
$ pip install virtualenv
```
