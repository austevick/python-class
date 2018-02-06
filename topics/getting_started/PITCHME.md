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

+++
The with statement encloses a code block within a context manager (for example opening a file and then closing it).
```
with open("x.txt") as f:
    data = f.read()
    print data
```
@[1-3](This will automatically close the file when done)
