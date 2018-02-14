## Strings
+++
Strings are among the most popular types in Python. In python, the built-in string class is called `str`. You can create a string simply by enclosing characters in quotes. Python treats single quotes the same as double quotes. Creating strings is as simple as assigning a value to a variable

```
var1 = 'Hello World!'
var2 = "Python Programming"
```
+++
Python strings are "immutable" which means they cannot be changed after they are created. Since strings can't be changed, python creates new strings under the hood to handle changes in value and computing values. So for example the expression ('hello' + 'there') takes in the 2 strings 'hello' and 'there' and builds a new string 'hellothere'.
```
a = 'hi'
b = "Austin"
print a + " " + b
a = "hey"
print a
```
