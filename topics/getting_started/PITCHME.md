## Getting Started
+++

Python is a dynamic language. There are no type declarations of variables, parameters, functions, or methods in the source code.

The language's core philosophy is summarized in the document The [Zen of Python](https://en.wikipedia.org/wiki/Zen_of_Python) (PEP 20), which includes aphorisms such as:
- Beautiful is better than ugly
- Explicit is better than implicit |
- Simple is better than complex |
- Complex is better than complicated |
- Readability counts |

+++
Python uses dynamic typing, and a combination of reference counting and a cycle-detecting garbage collector for memory management. It also features dynamic name resolution (late binding), which binds method and variable names during program execution.

+++
Python's design offers some support for functional programming. It has filter(), map(), and reduce() functions; list comprehensions, dictionaries, and sets; and generator expressions. The standard library has two modules (itertools and functools) that implement functional tools borrowed from Haskell and Standard ML.

---
## Syntax and semantics
Python is meant to be an easily readable language. Its formatting is uncluttered, and it often uses English keywords where other languages use punctuation. Unlike many other languages, it does not use curly brackets to delimit blocks, and semicolons after statements are optional.

+++
### Indentation
Python uses whitespace indentation, rather than curly brackets or keywords, to delimit blocks. An increase in indentation comes after certain statements; a decrease in indentation signifies the end of the current block.
```
def hello():
    print 'Hello'

for thing in things:
    print thing
```

+++
### Statements
Assigning values is different than in traditional languages. In C `x = 2` translates to "typed variable name x receives a copy of numeric value 2". In Python, `x = 2` translates to "(generic) name x receives a reference to a separate object of numeric type of value 2." Names may be rebound at any time to objects of varying types. Since a name is a generic reference holder it is unreasonable to associate a fixed data type with it.

+++
```
>>> x=3
>>> print x
3
>>> x="hello"
>>> print x
hello
>>>
```
+++
The if statement, which conditionally executes a block of code, along with else and elif.
```
x = True
if x:
    print "true"
elif:
    print "false"
else:
    print "What the hell is x then?!"
```
+++
The for statement, which loops over an iterable object, capturing each element to a local variable for use by the attached block.
```
things = [1,2,3,4]
for thing in things:
    print thing
```
+++
The while statement, which executes a block of code as long as its condition is true.
```
x = True
while x:
    print "This will for forever!!!!"
```
+++
The try statement, which allows exceptions raised in its attached code block to be caught and handled by except clauses; it also ensures that clean-up code in a finally block will always be run regardless of how the block exits.
```
try:
    thisWillBreak()
except:
    print 'It broke...'
```

+++
The class statement, which executes a block of code and attaches its local namespace to a class, for use in object-oriented programming.
```
class Car:
    def __init__(self,sound):
        self.sound = sound
    def drive(self):
        print sound
car = Car('Vroooommmmm')
car.drive()
>>> Vroooommmmm
```
+++
The def statement, which defines a function or method.
```
def hello(name):
    print "Hello " + name
hello("Austin")
>>> Hello Austin
```
@[1]
@[3]
@[4](Which will print Hello Austin)
+++
The with statement encloses a code block within a context manager (for example opening a file and then closing it).
```
with open("x.txt") as f:
    data = f.read()
    print data
```
@[1-3](This will automatically close the file when done)

+++
The pass statement is needed to create an empty code block.
```
def doNothing():
    pass
```
@[2](Putting pass here will allow the program to run without breaking)

+++
The import statement, which is used to import modules. There are two ways of using import:
```
import datetime
date = datetime.datetime.now()
# or
from datetime import *
date = datetime.now()
```
@[1-2](We would need to call the function we want by running datetime.datetime.now())
@[4-5](We would call the function we want running datetime.now())

+++
The print statement which prints to Standard Out
```
print "Hello"
>>> Hello
thing = [1,2,3,4]
print thing
>>> [1, 2, 3, 4]
```
@[1](Calling print "Hello")
@[2](Prints "Hello" to the console)
@[3-4](We can use the print statement to print objects as well)
@[5]

---
## Expressions
Some Python expressions are similar to languages such as C and Java, while some are not
+++
Addition, subtraction, and multiplication are the same, but the behavior of division differs. There are two types of divisions in Python. They are floor division and integer division.[63] Python also added the ** operator for exponentiation.
+++
In Python, == compares by value, versus Java, which compares numerics by value and objects by reference. Python's `is` operator may be used to compare object identities (comparison by reference).
```
a = '4'
b = '4'
print a == b
>>> True
a = [1,2,3,4]
b = [1,2,3,4]
print a is b
>>> False
c = a
print c is a
>>> True
```
@[1-2](Assigning 2 variables to the same value)
@[3](Means they are the same)
@[5-6](Assigning 2 variables to the same object)
@[8](Is not the same because the objects are separate references)
@[9](But assigning c to a means we are making c to be a)

+++
Python uses the words *and*, *or*, *not* for its boolean operators rather than the symbolic &&, ||, ! used in Java and C.
```
a = True
b = False
if a and not b:
    print "a is True AND b is False"
if a or b:
    print "If a is True OR b is True"
if not a:
    print "Not a"
```
@[3](If a is True AND b is NOT True)
@[5](If a or b are true)
@[7](If a is not True)

+++

### Math
Python has the usual C arithmetic operators (+, -, *, /, %). It also has ** for exponentiation, e.g. 5**3 == 125 and 9**0.5 == 3.0

---
### Python Interpreter
```
$ python        ## Run the Python interpreter
Python 2.7.9 (default, Dec 30 2014, 03:41:42)
[GCC 4.1.2 20080704 (Red Hat 4.1.2-55)] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> a = 6
>>> a
6
>>> a + 2
8
>>> a = 'hi'
>>> a
'hi'
>>> len(a)
2
>>> a + len(a)
Traceback (most recent call last):
  File "", line 1, in
TypeError: cannot concatenate 'str' and 'int' objects
>>> a + str(len(a))
'hi2'
>>> ^D
```
@[5](set a variable in this interpreter session)
@[6](entering an expression prints its value)
@[10]('a' can hold a string just as well)
@[13](call the len function on a string)
@[15-18](try something that doesn't work)
@[19-20](probably what you really wanted)
@[21](type CTRL-d to exit (CTRL-z in Windows/DOS terminal))

+++
### A Python File
Python source files use the ".py" extension and are called "modules." With a Python module hello.py, the easiest way to run it is with the shell command *python hello.py Alice* which calls the Python interpreter to execute the code in hello.py, passing it the command line argument "Alice"
```
#!/usr/bin/env python
import sys
# Gather our code in a main() function

def main():
    print 'Hello there', sys.argv[1]

if __name__ == '__main__':
    main()
```
@[1](This tells bash to run the file with the python interpreter)
@[2](import modules used here -- sys is a very standard one)
@[6](Command line args are in sys.argv[1], sys.argv[2] etc.)
@[6](sys.argv[0] is the script name itself and can be ignored)
@[8-9](Standard boilerplate to call the main function)
