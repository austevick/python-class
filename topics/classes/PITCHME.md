## Classes
+++
In Python, everything is an object and since an object is a class, everything in python is also a class.
+++
A class is a template for creating objects. Objects have member variables (attributes) and behavior associated with them (methods).
<!--  https://www.hackerearth.com/practice/python/object-oriented-programming/classes-and-objects-i/tutorial/ -->

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
