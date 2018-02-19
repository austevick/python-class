## Numbers
There are four distinct numeric types in python: plain integers, long integers, floating point numbers, and complex numbers. In addition to these built-in types, The standard library includes additional numeric types, `fractions` that hold rationals, and `decimal` that hold floating-point numbers with user-definable precision.
+++
- int (signed integers) − They are often called just integers or ints, are positive or negative whole numbers with no decimal point.
- long (long integers ) − Also called longs, they are integers of unlimited size, written like integers and followed by an uppercase or lowercase L.
+++
- float (floating point real values) − Also called floats, they represent real numbers and are written with a decimal point dividing the integer and fractional parts. Floats may also be in scientific notation, with E or e indicating the power of 10 (2.5e2 = 2.5 x 102 = 250).
- complex (complex numbers) − are of the form a + bJ, where a and b are floats and J (or j) represents the square root of -1 (which is an imaginary number). The real part of the number is a, and the imaginary part is b. Complex numbers are not used much in Python programming.

+++
Another common numeric type we see in python is Decimal. Decimal is included in the python standard library but is not Built-In (meaning you need to import Decimal from the decimal package first). Many people use this package to have control over the precision of the number (i.e number of decimal places).
```
from decimal import getcontext, Decimal
getcontext().prec = 3
output = Decimal(16.0)/Decimal(7)
print output
>>> 2.29
```
@[1](Import the Decimal class from the decimal module)
@[1](If you want to control the number of decimal places, you will also need to import getcontext)
@[2](Setting precision to 3)
@[3](Dividing 16.0 by 7)
