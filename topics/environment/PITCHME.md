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
For macs, you also have the option of installing it through homebrew

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
You can now install Python 2.7 by:
```
my-laptop:~ austevick$ brew install python
```
