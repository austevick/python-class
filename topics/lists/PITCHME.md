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
