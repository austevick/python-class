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
