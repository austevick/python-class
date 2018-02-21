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
++
