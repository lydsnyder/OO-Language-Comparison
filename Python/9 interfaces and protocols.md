#Interfaces / protocols - [Python](https://github.com/lydsnyder/OO-Language-Comparison/blob/master/Python/contents.md)

### What does the language support?

Python supports protocols. Protocols are informal and unenforceable.

The closest thing to a formal interface is an Abstract Base Class.

### What abilities does it have? & How is it used?

Python's protocol is implicit. If an object behaves like a class, it is treated as one. Say, for example, an object barks and wags its tail like a dog, Python considers it a dog. In runtime, instead of checking the type of an object, we try to invoke a method we expect the object to have. If it behaves the way we expected, we’re fine and move along. But if it doesn’t, things might blow up.

While protocols work fine in many cases, there are situations where informal interfaces or duck typing in general can cause confusion. Perhaps two classes, maybe a dog and a cat, can both bePet(). They are not the same thing even if they implement the same protocols. This is where Abstract Base Classes come in.

The following defines an abstract class:

```python
from abc import ABC, abstractmethod

class AbstractClassExample(ABC):

    def __init__(self, value):
        self.value = value
        super().__init__()

    @abstractmethod
    def do_something(self):
        pass
```

This is a subclass using the previous defined abstract class:

```python
class DoAdd42(AbstractClassExample):
    pass
x = DoAdd42(4)
```

This does not implement do_something, which throws an error. We are required to implement it because it is defined as an abstract method.

```python
TypeError: Can't instantiate abstract class DoAdd42 with abstract methods do_something
```

The correct definition is:

```python
class DoAdd42(AbstractClassExample):
    def do_something(self):
        return self.value + 42

class DoMul42(AbstractClassExample):

    def do_something(self):
        return self.value * 42

x = DoAdd42(10)
y = DoMul42(10)
print(x.do_something())
print(y.do_something())
```

This outputs no error.

Abstract methods in abstract classes can be implemented. The subclass will still have to override the method, but! the implementation in the abstract class can be called using super().

```python
super().do_something()
        ```
## Sources
[Protocols and ABCs](http://masnun.rocks/2017/04/15/interfaces-in-python-protocols-and-abcs/)
[Abstract Classes](https://www.python-course.eu/python3_abstract_classes.php)
