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
+++
### Lambdas
Also knows as anonymous functions (functions with out a name).  These functions are considered throw-away functions as they are just needed when they are created. Lambda functions are mainly used in combination with the filter(), map() and reduce().
+++
The general syntax looks like:
```
lambda arguments: an_expression
```
+++
A simple example:
```
f = lambda x, y : x + y
f(1,1)
>>> 2
```
<!-- https://www.python-course.eu/lambda.php -->
+++
A complex example, assuming a csv file called test.csv with the following content
```
192.168.1.1,1111111,hello
192.168.1.2,2222222,hi
192.168.1.3,5555555,bye
```
```
with open('test.csv') as f:
    lines = f.readlines()
    print sorted(lines,key=lambda line: line.split(',')[1],reverse=True)
>>> ['192.168.1.3,5555555,bye', '192.168.1.2,2222222,hi\n', '192.168.1.1,1111111,hello\n']
```
@[6](We are using a lambda function inside of the sorted function)
@[6](The sorted function takes a list and a special sort key)
@[6](For the sort key, we are using a lambda function)
@[6](sorted is automatically passing in the current line as the argument to lambda)
@[6](We then split the line on commas and fetch the item at index 1)
@[6](Since this is a single line function, the value of line.split index 1 is considered to be implicitly returned)
+++
### Generators
<!--  https://www.learnpython.org/en/Generators -->
Generators are used to create iterators. Generators are simple functions which return an iterable set of items, one at a time using the yield keyword.
+++
The generator gets called by the for statement. Once the generator's function code reaches a `yield` statement, the generator yields its execution back to the for loop, returning a new value from the set. The generator function can generate as many values as it wants, yielding each one in its turn.
+++
As seen in https://www.learnpython.org/en/Generators
```
import random
  def lottery():
      for i in range(6):
          yield random.randint(1, 40)
  for random_number in lottery():
         print("And the next number is... %d!" %(random_number))
```
@[1](For this example, we will need to import the random package to make random numbers)
@[5](The forloop is going to call our lottery function)
@[3](We loop 6 times here)
@[4](We are generating a random number between 1 and 40 and returning it to the loop that called the lottery method)
@[6](We take the number that was yielded to us in the lottery method and print it)
@[5-6](After the current iteration of the loop finishes, the lottery function is resumed)
@[3-4](Allowing it's own loop to contiue to the next number)
@[2-6](The cycle will continue until lottery's loop finishes...so 6 iterations total)
