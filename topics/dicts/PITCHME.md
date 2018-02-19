## Dictionaries
+++
More commonly known as dicts. Dicts are python's key/value hash table. The contents of a dict are written as a series of key:value pairs within {}.
```
a = {"MyKey":"The Value"}
print a['MyKey']
>>> The Value
```
An empty dict is represented by a pair of empty curly brackets
```
a = {}
```
+++
Looking up or setting a value uses square brackets. Running `a['foo']` looks up the key 'foo' in the dictionary "a". Strings, numbers and even tuples can be a key and any type can be a value. Strings and Tuples work best as keys as they are immutable and using mutable types may lead to unexpected behavior.
```
a = {}
a["foo"] = "Hello"
a["test"] = [1,2,3,4]
a["bar"] = {"myKey":"The Value"}
print a
>>> {'test': [1, 2, 3, 4], 'foo': 'Hello', 'bar': {'myKey': 'The Value'}}
```
@[1](We are creating an empty dict)
@[2](We are adding a key called foo to the dict a and setting the value to the string "hello")
@[3](We are adding a new key called test and having the value be a list)
@[4](We are adding a key called bar and having the value be ANOTHER dict with a key of MyValue and a value of "The Value")

+++
```
a = {
    "foo":"Hello",
    "test":[1,2,3,4],
    "bar":{"myKey":"The Value"}
}
print a
>>> {'test': [1, 2, 3, 4], 'foo': 'Hello', 'bar': {'myKey': 'The Value'}}
```
@[1-5](We can also define all the key/value pairs at initialization)
+++
Looking up a key that is not in the dict will lead to a KeyError. Use `if "foo" in dict` to see safely see if the key is in the dict. Alternatively, you can use the get() method on the dict object to safely get a key as it will return None if a key does not exists.
```
>>> thing = {"foo":"bar"}
>>> "foo" in thing
True
>>> if "that" in thing:
...     print "yes"
... else:
...     print "no"
...
no
>>> print thing.get('foo')
bar
>>> print thing.get('that')
None
>>> a = thing.get('foo')
>>> print a
bar
```
