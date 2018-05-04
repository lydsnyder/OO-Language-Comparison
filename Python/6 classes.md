# Classes - [Python](https://github.com/lydsnyder/OO-Language-Comparison/blob/master/Python/contents.md)


### Defining

In Python, simple class definitions look like this:

```python
class ClassName:
    <statement-1>
    ...
    ...
    <statement-N>
```

### Creating new instances

Class instantiation uses function notation. Pretend the class is a parameterless function that returns a new instance of the class.
With the above class, an instantiation would be:

```python
x = ClassName()
```

This creates a new instance of the class and assigns this object to the local variable x.

### Constructing/initializing

_init_() is a special method, which is called class constructor or initialization method that Python calls when you create a new instance of this class.

For example, if inside ClassName() there was

```python
def __init__(self):
    self.data = []
    ```

then upon calling

```python
x = ClassName()
```

x is assigned a new, initalized instance.

### Destructing/de-initializing

_del_() is the destructor in Python, but it seems that the use of it is not recommended. It runs when the reference count to an object, but it is possible for an object to not be properly cleaned up or memory to be freed. The garbage collector can lose the last reference to a linked list. It appears that there is no real counterpart in Python to init().

## Sources:

[Classes - Python.org](https://docs.python.org/3/tutorial/classes.html)

[Python Gotchas](http://www.algorithm.co.il/blogs/programming/python-gotchas-1-__del__-is-not-the-opposite-of-__init__/)
