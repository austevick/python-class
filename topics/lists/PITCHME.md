## Lists
+++
Python has a built-in list type called "list". Lists are written within square brackets "[]". Lists and strings work similarly in the sense they both use the len() function and square brackets [ ] to access data, with the first element at index 0.
```
colors = ['red', 'blue', 'green']
print colors[0]
>>> red
print colors[2]
>>> green
print len(colors)
>>> 3
```
+++
![a list](https://developers.google.com/edu/python/images/list1.png)
+++
Assignment with an = on lists does not make a copy. Instead, assignment makes the two variables point to the one list in memory.
![list memory allocation](https://developers.google.com/edu/python/images/list2.png)
+++
An empty list is denoted with an empty pair of brackets []. The '+' works to append two lists, so [1, 2] + [3, 4] yields [1, 2, 3, 4] (this is just like + with strings).
```
a = [1,2]
b = [3,4]
print a + b
[1,2,3,4]
```
+++
A list can be looped over in a for loop using the `in` keyword
```
my_list = [1,2,3,4,5]
for number in my_list:
    print number
>>> 1
>>> 2
...
```
+++
The `in` keyword on its own is an easy way to test if a value appears in a list. Using `in` in an if statement returns True or False
```
colors = ['red', 'blue', 'green']
blue = 'blue' in colors
print blue
>>> True
if 'blue' in colors:
    print 'yep, it\'s blue'
>>> yep, it's blue
```
@[6](Notice in this print statement we have to escape the ' in it's. We escape it because otherwise the interpreter will think the string ends there)
+++
### List Methods
Since a list is also an object, a list type has several methods you can use on it
- list.append(item) - modifies list by adding a single item to the end
- list.insert(index, item) - inserts the item at the given index, shifting elements to the right.
+++
- list.extend(list2) -  adds the elements in list2 to the end of the list. Using + or += on a list is similar to using extend().
- list.index(item) - searches for the given item from the start of the list and returns its index. Throws a ValueError if the element does not appear (use "in" to check without a ValueError).
- list.remove(item) - searches for the first instance of the given item and removes it (throws ValueError if not present)
+++
- list.sort() - sorts the list in place (does not return it).
- list.reverse() - reverses the list in place (does not return it)
- list.pop(index) - removes and returns the element at the given index. Returns the rightmost element if index is omitted (roughly the opposite of append()).
+++
```
list = ['larry', 'curly', 'moe']
list.append('shemp')         ## append elem at end
list.insert(0, 'xxx')        ## insert elem at index 0
list.extend(['yyy', 'zzz'])  ## add list of elems at end
print list  ## ['xxx', 'larry', 'curly', 'moe', 'shemp', 'yyy', 'zzz']
print list.index('curly')    ## 2

list.remove('curly')         ## search and remove that element
list.pop(1)                  ## removes and returns 'larry'
print list  ## ['xxx', 'moe', 'shemp', 'yyy', 'zzz']
```
+++
### Building a list
One common pattern wen creating a list is to create a empty list and add to it
```
list = []
list.append('a')
list.append('b')
print list
>>> ['a','b']
```
+++
### List Slices
Slices work on lists just as with strings, and can also be used to change sub-parts of the list.
```
list = ['a', 'b', 'c', 'd']
print list[1:-1]
>>> ['b','c']
list[0:2] = 'z'
print list
>>> ['z', 'c', 'd']
```
@[4](replace ['a', 'b'] with ['z'])
