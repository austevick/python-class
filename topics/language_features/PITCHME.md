## Handy Language Features
+++
### List Comprehension
List comprehensions provide a concise way to create lists. Common applications are to make new lists where each element is the result of some operations applied to each member of another sequence/iterable, or to create a subsequence of those elements that satisfy a certain condition.
+++
```
string = "Hello 12345 World"
numbers = [x for x in string if x.isdigit()]
print numbers
>>> ['1', '2', '3', '4', '5']
```
@[2](We are generating a list where the elements are just numbers found in the string)
@[2](Notice the optional if statement we included which filters for just numbers )
+++
```
squares = [x**2 for x in range(10)]
>>> [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```
@[1](We are generating a list of square numbers)
@[1](Notice there is no if statement in this list comprehension)
+++
<!--  
    http://www.pythonforbeginners.com/basics/list-comprehensions-in-python
    https://docs.python.org/2/tutorial/datastructures.html
 -->
+++
Given a list comprehension such as:
```
[x for x in string if x.isdigit()]
```
Think of this as generating a new list inside of the square brackets.
+++
Breaking up the syntax of the list comprehension, we can see that it is structured roughly like:
```
[a_variable_going_into_the_list for a_variable_going_into_the_list in the_sequence optional_if_statement]
```
+++
### Dict Comprehension
Just like list comprehensions, we can also generate dictionaries with dict comprehensions
```
squares = {x: x**2 for x in (2, 4, 6)}
>>> {2: 4, 4: 16, 6: 36}
```
@[1](In this example, we are going through a loop and using the number as the key and the square as the value)
