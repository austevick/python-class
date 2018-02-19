## Booleans
+++
Booleans are used to represent truth values. The values are represented as True and False. Python also allows other values to be considered "truethy" such as the integers 0 and 1 the presence of a value and the absence of a value. You can use the built-in function bool() to cast these truethy values to an actual boolean.
+++
```
>>> a = True
>>> a
True
>>> b = 1
>>> bool(b)
True
>>> c = None
>>> bool(c)
False
```
@[1](We are setting a to True)
@[4](Here we set b to 1)
@[5](But when we cast using bool it is evaluated to True because 1 is truethy)
@[7](Here we set c to None to represent nothing)
@[8](It is evaluated to False because None is considered Falsesy)
