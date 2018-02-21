## Flow Control
+++
The most common flow control in python are the if statements.
+++
```
name = 'Austin'
if name = 'Austin':
    print 'Hi Austin'
```
+++
The if statement can also be optionally followed by an else statement:
```
name = 'Austin'
if name = 'Austin':
    print 'Hi Austin'
else:
    print 'You\'r not Austin....'
```
+++
Lastly, python can also use elif in a if statement:
```
name = 'Austin'
if name = 'Austin':
    print 'Hi Austin'
elif:
    print 'Hi Janet'
else:
    print 'I have no idea who you are....'
```
+++
Python doesn't have a switch statement but the common workaround it to have multiple elif statements:
```
name = 'Austin'
if name == 'Austin':
    print 'Hi Austin'
elif name == 'Janet':
    print 'Hi Janet'
elif name == 'Christian'
    print 'Hi Christian'
else:
    print 'I have no idea who you are....'
```
+++
You can negate if statements:
```
name = 'Austin'
if name is not 'Austin':
    print 'I don't want to talk to anyone who is not Austin....
```
+++
You can use the `is` keyword for equality instead of `==`
```
name = 'Austin'
if name is 'Austin':
    print 'Hi Austin'
```
