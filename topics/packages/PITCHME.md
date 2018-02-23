## Modules and Packages
+++
Modules in Python are simply Python files with a .py extension. The name of the module will be the name of the file. A Python module can have a set of functions, classes or variables defined and implemented.
<!-- https://www.learnpython.org/en/Modules_and_Packages -->
+++
Given 2 files such as
```
.
├── app.py
└── utils.py
```
+++
utils.py contains
```
def hello():
    print 'Hi Austin'
```
+++
app.py contains
```
import utils
utils.hello
```
When we run
```
python app.py
```
we get
```
>>> Hi Austin
```
+++
Instead of importing the whole module utils, we can just import the `hello()` as well
```
from utils import hello
hello()
```
+++
When the import keyword runs, the Python interpreter will look for a file in the directory which the script was executed from, by the name of the module with a .py prefix, so in our case it will try to look for utils.py. If it finds one, it will import it. If not, he will continue to look for built-in modules.
+++
You may have noticed that when importing a module, a .pyc file appears, which is a compiled Python file. Python compiles files into Python bytecode so that it won't have to parse the files each time modules are loaded. If a .pyc file exists, it gets loaded instead of the .py file, but this process is transparent to the user.
+++
### Packages
Packages are namespaces which contain multiple packages and modules themselves. They are simply directories, but with a twist.
Each package in Python is a directory which MUST contain a special file called __init__.py. This file can be empty, and it indicates that the directory it contains is a Python package, so it can be imported the same way a module can be imported.
+++
If we create a directory called utils, which marks the package name, we can then create a module inside that package called say. We also must not forget to add the __init__.py file inside the utils directory.

To use the say module in the utils package, we can import it in two ways
+++
```
.
├── app.py
└── utils
    ├── __init__.py
    └── say.py
```

The utils/say.py file has
```
def hello():
    print 'Hi Austin'
def bye():
    print 'Bye Austin'
```

The utils/__init__.py file is empty.

The app.py file looks like
```
import utils
utils.say.hello()
utils.say.bye()
```
When we run app.py
```
python app.py
```
We get
```
>>> Hi Austin
>>> Bye Austin
```
+++
We can also write the app.py file like
```
from utils import say
say.hello()
say.bye()
```
or like
```
from utils.say import hello, bye
hello()
bye()
```
