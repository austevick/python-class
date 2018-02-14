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
+++
Unlike Java, the '+' does not automatically convert numbers or other types to string form. The str() function converts values to a string form so they can be combined with other strings.
```
pi = 3.14
##text = 'The value of pi is ' + pi      ## NO, does not work
text = 'The value of pi is '  + str(pi)  ## yes
```
+++
### String Methods
Next you will see some of the most common string methods. A method is like a function, but it runs "on" an object. If the variable s is a string, then the code s.lower() runs the lower() method on that string object and returns the result

+++
#### s.lower() & s.upper()
returns the lowercase or uppercase version of the string
```
>>> s = 'Hello!'
>>> low = s.lower()
>>> print low
'hello!'
>>> s.upper()
'HELLO!'
```

+++
#### s.strip()
returns a string with whitespace removed from the start and end
```
>>> s = " Hello!  "
>>> print s
 Hello!  
>>> stripped = s.strip()
>>> print stripped
Hello!
>>>
```
+++
#### s.isalpha() & s.isdigit() & s.isspace()
tests if all the string chars are in the various character classes
```
>>> s = 'Hello'
>>> s.isalpha()
True
>>> s.isdigit()
False
>>> s = '12'
>>> s.isdigit()
True
>>> s.isspace()
False
>>> s = ' '
>>> s.isspace()
True
```
+++
#### s.startswith('other') &  s.endswith('other')
tests if the string starts or ends with the given other string
```
>>> s = 'Hello Austin'
>>> s.startswith('Hel')
True
>>> s.endswith('tin')
True
>>> s.startswith('h')
False
>>> s.startswith('Hi')
False
```
+++
#### s.find('other')
searches for the given other string within s, and returns the first index where it begins or -1 if not found
```
>>> s = 'Hello Austin'
>>> s.find("Hello")
0
>>> s.find("lo")
3
>>> s.find("yo")
-1
```
+++
#### s.replace('old', 'new')
returns a string where all occurrences of 'old' have been replaced by 'new'
```
>>> s = 'Hello Austin'
>>> print s
Hello Austin
>>> print s.replace("Hello","Bye")
Bye Austin
```
+++
#### s.split('delim')
returns a list of substrings separated by the given delimiter. 'aaa,bbb,ccc'.split(',') -> ['aaa', 'bbb', 'ccc']. As a convenient special case s.split() (with no arguments) splits on all whitespace chars.
```
>>> s = 'a,csv,example'
>>> print s.split(',')
['a', 'csv', 'example']
>>> s = 'Hello World!'
>>> print s.split()
['Hello', 'World!']
```
+++
#### s.join(list)
opposite of split(), joins the elements in the given list together using the string as the delimiter. e.g. '---'.join(['aaa', 'bbb', 'ccc']) -> aaa---bbb---ccc
```
>>> L = ['make','A','csv']
>>> print L
['make', 'A', 'csv']
>>> print ','.join(L)
make,A,csv
```
+++
There are several more string methods available. Check out [String Methods](https://docs.python.org/2/library/stdtypes.html#string-methods) in the python documentation!
+++
### String Slices
The "slice" syntax is a handy way to refer to sub-parts of sequences -- typically strings and lists. The slice s[start:end] is the elements beginning at start and extending up to but not including end.

+++
![Index example](https://developers.google.com/edu/python/images/hello.png)
- s[1:4] is 'ell' - chars starting at index 1 and extending up to but not including index 4
- s[1:] is 'ello' - omitting either index defaults to the start or end of the string
- s[:] is 'Hello' - omitting both always gives us a copy of the whole thing
- s[1:100] is 'ello' - an index that is too big is truncated down to the string length

+++
![Index example](https://developers.google.com/edu/python/images/hello.png)
- s[-1] is 'o' - last char (1st from the end)
- s[-4] is 'e' - 4th from the end
- s[:-3] is 'He' - going up to but not including the last 3 chars.
- s[-3:] is 'llo' - starting with the 3rd char from the end and extending to the end of the string.

+++
### String Formatting
Python has the built-in ability to create "formatted" strings. Given a format string (what you want it to look like) and a group of arguments, you can create a new string that is a combination of the format string and the arguments.
```
>>> name = 'Austin'
>>> print 'Hello {}!'.format(name)
Hello Austin!
>>> first = 'Austin'
>>> last = 'Evick'
>>> print 'Hello {} {}!'.format(first,last)
Hello Austin Evick!
>>>
```
+++
There is an older style of string formatting that uses %s and %d to act as placeholders for text/numbers
```
>>> first = 'Austin'
>>> last = "Evick"
>>> print "Hello %s!" % first
Hello Austin!
>>> print "Hello %s %s!" % (first,last)
Hello Austin Evick!
```
@[3](Separate the format string and the arguments with a "%")
@[3](When you only have one argument, you can just put the variable after the %)
@[5](When you have more than one argument, you need to surround them like so after the %)
This style has largely started to die but you you may still find it out in the wild
