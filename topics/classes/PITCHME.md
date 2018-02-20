## Classes
+++
In Python, everything is an object and since an object is a class, everything in python is also a class.
+++
A class is a template for creating objects. Objects have member variables (attributes) and behavior associated with them (methods).
<!--  
https://www.hackerearth.com/practice/python/object-oriented-programming/classes-and-objects-i/tutorial/
http://python-textbok.readthedocs.io/en/1.0/Classes.html
 -->

+++
```
class Snake:
    pass
snake = Snake()
print snake
>>> <__main__.Snake object at 0x7f315c573550>
```
@[1-2](We are creating an empty class with no extra variables/methods beyond the default ones already implemented by the object class)
@[5](Since our class has no string representation, it defaults to the class name and the memory address this instance is in)
+++
A class by itself is of no use unless there is some functionality associated with it. Functionalities are defined by setting attributes, which act as containers for data and functions related to those attributes. Those functions are called methods.
```
class Snake:
    name = "python"
snake = Snake()
print snake.name
>>> python
```
@[2](We create an attribute called snake on the class)
@[4](We can access the name attribute of the snake class by using "dot notation")
+++
You can also define functions that will access the class attributes. These functions are called methods. When you define methods, you will need to always provide the first argument to the method with a self keyword.
+++
```
class Snake:
    name = "python"
    def change_name(self, new_name):
        self.name = new_name
snake = Snake()
print snake.name
>>> python
snake.change_name("anaconda")
print snake.name
>>>anaconda
```
@[3](Note the first argument is the self keyword)
@[4](We access the class attribute using the self keyword)
@[8](change the name using the change_name method)
+++
You can also provide the values for the attributes at runtime (called instance attributes). This is done by defining the attributes inside the init method.
```
class Snake:
    def __init__(self, name):
        self.name = name
    def change_name(self, new_name):
        self.name = new_name
python = Snake("python")
print python.name
>>> "python"
anaconda = Snake("anaconda")
print python.name
>>> "anaconda"
```
@[2](Think of the __init__ method as a constructor)
@[3](The init method gets passed self as the first argument which is followed by other arguments)
@[6](Now when we create the class, we pass in the name of the snake)
+++
There is a difference between class attributes and instance attributes in classes. Attributes that are defined in an __init__ method are instance attributes as they are added to the instance when the __init__ method is called. Attributes that are set on the class are called instance attributes. These attributes will be shared by all instances of that class. Class attributes are often used to define constants which are closely associated with a particular class.
+++
```
class Person:
    Titles = ['Mr','Mrs','Ms']
    def __init__(self,name):
        self.name = name
```
@[2](This is a class attribute)
@[4](This is a instance attribute)
+++
### @staticmethod
A static method doesn’t have the calling object passed into it as the first parameter. This means that it doesn’t have access to the rest of the class or instance at all. This is a common technique when grouping together related methods which don't need access to each other.
```
class Test:
    @staticmethod
    def thing1():
        print 'thing 1'
    @staticmethod
    def thing2():
        print 'thing 2'
Test.thing2()
```
+++
### @property
This is used to generate a property dynamically.
```
class Person:
    def __init__(self,first,last):
        self.first = first
        self.last = last
    @property
    def full_name(self):
        print '{} {}'.format(self.first,self.last)
person = Person(first='Austin',last='Evick')
person.full_name
```
@[9](Notice we don't need parenthesis when calling full_name since it is considered a property)
