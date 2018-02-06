## Getting Started
+++

Python is a dynamic language. There are no type declarations of variables, parameters, functions, or methods in the source code.

The language's core philosophy is summarized in the document The [Zen of Python](https://en.wikipedia.org/wiki/Zen_of_Python) (PEP 20), which includes aphorisms such as:
- Beautiful is better than ugly
- Explicit is better than implicit |
- Simple is better than complex |
- Complex is better than complicated |
- Readability counts |

+++
Python uses dynamic typing, and a combination of reference counting and a cycle-detecting garbage collector for memory management. It also features dynamic name resolution (late binding), which binds method and variable names during program execution.

+++
Python's design offers some support for functional programming. It has filter(), map(), and reduce() functions; list comprehensions, dictionaries, and sets; and generator expressions. The standard library has two modules (itertools and functools) that implement functional tools borrowed from Haskell and Standard ML.

---
## Syntax and semantics
Python is meant to be an easily readable language. Its formatting is uncluttered, and it often uses English keywords where other languages use punctuation. Unlike many other languages, it does not use curly brackets to delimit blocks, and semicolons after statements are optional.

+++
### Indentation
Python uses whitespace indentation, rather than curly brackets or keywords, to delimit blocks. An increase in indentation comes after certain statements; a decrease in indentation signifies the end of the current block.
```
def hello():
    print 'Hello'

for thing in things:
    print thing
```

+++
### Statements
Assigning values operates differently than in traditional languages. An assignment in C `x = 2`, translates to "typed variable name x receives a copy of numeric value 2". The right-hand value (2) is copied into an allocated storage location for which the (left-hand) variable name (x) is the symbolic address. In the simplest case of Python assignment, x = 2 translates to "(generic) name x receives a reference to a separate, object of numeric type of value 2." Names may be rebound at any time to objects of varying types, including strings, lists, etc. Successive assignments of a common value to multiple names, e.g., x = 2; y = 2; z = 2 result in allocating storage to three names and one numeric object, to which all three names are bound. Since a name is a generic reference holder it is unreasonable to associate a fixed data type with it.
