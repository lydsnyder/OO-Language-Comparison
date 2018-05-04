# Inheritance / extension - [Python](https://github.com/lydsnyder/OO-Language-Comparison/blob/master/Python/contents.md)

Python supports multiple inheritance. A class definition with multiple base classes is show below.

```python
class DerivedClassName(Base1, Base2, Base3):
    <statement-1>
    .
    .
    .
    <statement-N>
    ```

Python has two function built-in to work with inheritance:

isinstance() checks an instance's type.
issubclass() checks inheritance.

For old-style classes, Python searches depth-first, left-to-right for inherited attributes. If an attribute is not found in DerivedClassName, Python searches Base1. If an attribute is not there, it recursively searches the parent classes of Base1 and so on. If the attribute is not found there, Python searches Base2.

With new-style classes, the order to search for an attribute changes dynamically. This is because with multiple inheritance, there is more than one path to get to higher classes. For example, the definition of a new-style class is that it is inherited from object.  If so, any case of multiple inheritance provides more than one path to reach object.

To keep the base classes from being accessed more than once, the dynamic algorithm linearizes the search order in a way that preserves the left-to-right ordering specified in each class, that calls each parent only once, and that is monotonic (meaning that a class can be subclassed without affecting the precedence order of its parents). Taken together, these properties make it possible to design reliable and extensible classes with multiple inheritance.

## Sources

[New-style and classic classes](https://docs.python.org/2/reference/datamodel.html#newstyle)
[Multiple Inheritance](https://docs.python.org/3.4/tutorial/classes.html#multiple-inheritance)
