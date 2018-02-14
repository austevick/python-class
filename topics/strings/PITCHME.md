## Strings
+++
Strings are among the most popular types in Python. In python, the built-in string class is called `str`. You can create a string simply by enclosing characters in quotes. Python treats single quotes the same as double quotes. Creating strings is as simple as assigning a value to a variable

```
var1 = 'Hello World!'
var2 = "Python Programming"
```
+++
Python strings are "immutable" which means they cannot be changed after they are created. Since strings can't be changed, python creates new strings under the hood to handle changes in value and computing values. So for example the expression ('hi' + 'Austin') takes in the 2 strings 'hi' and 'Austin' and builds a new string 'hiAustin'.
```
a = 'hi'
b = "Austin"
print a + " " + b
a = "hey"
print a
```
+++
Characters in a string can be accessed with the usual [] syntax. Python uses zero-based indexing, so given the string 'hello', [1] would give you 'e' . If the index is out of bounds for the string, Python raises an error.
```
>>> myString = 'hello'
>>> print myString[1]
e
```
+++
 The len(string) function returns the length of a string. The [ ] syntax and the len() function actually work on any sequence type -- strings, lists, etc.
 ```
>>> myString = "Hello!"
>>> print len(myString)
6
print myString[5]
 ```
@[3](Notice how the length of the string is 6)
@[4](But we get the last character with myString[5]?)
@[1-4](This is because len does NOT return a 0 based count. It is 1 based)
