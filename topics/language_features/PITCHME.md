## Handy Language Features
+++
### List Comprehension
List comprehensions is a concise way to create lists in python.
```
string = "Hello 12345 World"
numbers = [x for x in string if x.isdigit()]
print numbers
>>> ['1', '2', '3', '4', '5']
```
<!--  http://www.pythonforbeginners.com/basics/list-comprehensions-in-python -->
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
