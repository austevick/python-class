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
Python uses dynamic typing, and a combination of reference counting and a cycle-detecting garbage collector for memory management (i.e. deletes a variable when a value no longer has any references to it). It also features dynamic name resolution (late binding), which binds method and variable names during program execution.

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
Assigning values is different than in traditional languages. In C `x = 2` translates to "typed variable name x receives a copy of numeric value 2". In Python, `x = 2` translates to "(generic) name x receives a reference to a separate object of numeric type of value 2." Names may be reassigned at any time to objects of varying types. Since a name is a generic reference holder it is unreasonable to associate a fixed data type with it.

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
@[1](Assign x to 3)
@[4](We can also reassign x to "hello" which is a different type than the previous value 3)
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
@[3](Inside of the forloop, we have access to the variable thing which is declared in the loop)
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
@[1](We declare the class here)
@[2](The __init__ function is used to setup the class during the class's initialization)
@[3](Here we assign the class property sound to the parameter sound. Class properties begin with self)
@[4](We create a class method called drive)
@[6](We create a new car and pass in the sound we want it to make)
@[7](We call the drive method on car)
@[7](We don't need to pass in self on this call because self gets automatically added into all class methods)
+++
The def statement, which defines a function or method.
```
def hello(name):
    print "Hello " + name
hello("Austin")
>>> Hello Austin
```
@[1](Define the method here)
@[3](Call it here)
@[4](Which will print Hello Austin)
+++
The with statement encloses a code block within a context manager (for example opening a file and then closing it).
```
with open("x.txt") as f:
    data = f.read()
    print data
```
@[1-3](This will automatically close the file when done because it runs inside the with statement)

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
Addition, subtraction, and multiplication are the same, but the behavior of division differs. There are two types of divisions in Python. They are floor division and integer division. Python also added the ** operator for exponentiation.
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
With a file called hello.py, the easiest way to run it is with the shell command *python hello.py Alice* which calls the Python interpreter to execute the code in hello.py, passing it the command line argument "Alice"
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

+++
The outermost statements in a Python file do the one-time setup — those statements run from top to bottom the first time the module is imported somewhere. A Python module can be run directly — as above "python hello.py Bob" — or it can be imported and used by some other module. When a Python file is run directly, the special variable "__name__" is set to "__main__". Therefore, it's common to have the boilerplate if __name__ ==... shown above to call a main() function when the module is run directly, but not when the module is imported by some other module.

+++
In a standard Python program, the list sys.argv contains the command-line arguments with sys.argv[0] being the program itself, sys.argv[1] the first argument, and so on. You can find the number of arguments by using len(sys.argv). In general, len() can tell you how long a string is, the number of elements in lists and tuples (another array-like data structure), and the number of key-value pairs in a dictionary.
