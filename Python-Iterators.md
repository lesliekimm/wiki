# Python Iterators

Python supports a concept of iteration over containers. This is implemented using two distinct methods; these are used to allow user-defined classes to support iteration.

[Python Docs - Iterator Types](https://docs.python.org/3/library/stdtypes.html#iterator-types)

## More

**TODO: Clarify what iteration means and what iterators can be used for.**

- Objects can implement a `__iter__()` method that returns an iterator object to support iteration.
- Iterator objects must implement:

  - `__iter__()`: returns the iterator object.
  - `__next__()`: returns the next object of the container.

```python
iterator_object = 'abc'.__iter__()
print(iterator_object)
print(id(iterator_object))
print(id(iterator_object.__iter__())) # Returns the iterator itself.
print(iterator_object.__next__())     # Returns 1st object and advances iterator.
print(iterator_object.__next__())     # Returns 2nd object and advances iterator.
print(iterator_object.__next__())     # Returns 3rd object and advances iterator.
print(iterator_object.__next__())     # Raises StopIteration Exception.
```

Output :

```asciidoc
<str_iterator object at 0x102e196a0>
4343305888
4343305888
a
b
c
---------------------------------------------------------------------------
StopIteration                             Traceback (most recent call last)
<ipython-input-1-d466eea8c1b0> in <module>()
      6 print(iterator_object.__next__())     # Returns 2nd object and advances iterator.
      7 print(iterator_object.__next__())     # Returns 3rd object and advances iterator.
----> 8 print(iterator_object.__next__())     # Raises StopIteration Exception.

StopIteration:
```

[Previous](Python-More-Builtin-Types)
