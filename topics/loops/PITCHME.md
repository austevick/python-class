## Loops
+++
There are two different types of loops in Python, for loops and while loops
```
list = [1,2,3,4]
for num in list:
    print num

x = True
while x:
    print 'Yay!'
```
@[2](A for loop is essentially a for each loop in other languages)
@[2](It will go through each element in the sequence and assign the current item to the local scoped variable..i.e. num in this case)
@[6](a while loop will continue to loop till the condition is false)
@[7](Since we hardcode x as True, the loop will continue for ever)
+++
Python also supports nested loops
```
list = [{'name':'Austin'},{'name':'Not Austin'}]
for person in list:
    for item in person:
        print person[item]
```
@[3](Since the dict in this index is iterable, we can use it in a loop)
@[4](Variables in a nested loop have access to variables declared in the parent loop..in this case person)
+++
### Loop control
Python has several keywords to control the flow of a loop. The two most common ones you will see are `break` and `continue`.
- `break` is used when you need to stop the whole loop and skip to the next block of code below it
- `continue` is used when you need to skip the current iteration of the loop and go back to the beginning of the loop
+++
#### Break Example
```
for letter in 'Python':
   if letter == 'h':
      break
   print 'Current Letter :', letter
print 'done'
>>> Current Letter : P
>>> Current Letter : y
>>> Current Letter : t
>>> done
```
<!-- http://www.tutorialspoint.com/python/python_loop_control.htm -->
+++
#### Continue Example
```
for letter in 'Python':
   if letter == 'h':
      continue
   print 'Current Letter :', letter
print 'done'
>>> Current Letter : P
>>> Current Letter : y
>>> Current Letter : t
>>> Current Letter : o
>>> Current Letter : n
>>> done
```
+++
Python also supports using the `else` keyword in a loop as well. The else statement will be executed when the loop finishes iterating.
```
for num in range(10,20):
   for i in range(2,num):
      if num%i == 0:
         j=num/i
         print '%d equals %d * %d' % (num,i,j)
         break
   else:
      print num, 'is a prime number'
```
@[1](We iterate between 1 and 20)
@[2](We loop on the factors of the number)
@[3](We determine the first factor)
@[4](We calculate the second factor)
@[6](used to move onto the next iteration in the parent loop)
@[7](Else it is a prime number)
+++
The last keyword we often see in loops is the `pass` keyword. As we discussed before, the `pass` keyword is used to have a indented block with no code be syntactically correct.
```
for letter in 'Python':
   if letter == 'h':
      pass
   print 'Current Letter :', letter
print 'done'
>>> Current Letter : P
>>> Current Letter : y
>>> Current Letter : t
>>> Current Letter : o
>>> Current Letter : n
>>> done
```
@[2-3](In this example, we don't want to do anything when the letter is h)
+++
### How looping works behind the scenes
Objects that can be looped over have a method called `__iter__` on them. This method returns an iterator object and does any needed initialization (like setting a counter to 0). The iterator object has a method on it called `next()` that the loop calls to get the next value.
+++
```
>>> thing = [1,2]
>>> thing.__iter__()
<listiterator object at 0x10ff96a90>
>>> dir(thing.__iter__())
['__class__', '__delattr__', '__doc__', '__format__', '__getattribute__', '__hash__', '__init__', '__iter__', '__length_hint__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'next']
>>> thing.__iter__().next()
1
>>>
```
@[1](Our object that can be looped over)
@[2](Any object that can be used in a loop must have a __iter__ method. This method returns an iterator object)
@[4](The dir method can be used to see properties of an object)
@[5](We can see that the iterator object on thing has a method called next)
@[6](Calling the next method on the iterator object gets the next value from the object)
