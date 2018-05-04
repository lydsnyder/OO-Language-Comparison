# Properties - [Python](https://github.com/lydsnyder/OO-Language-Comparison/blob/master/Python/contents.md)


### Getters and setters…write your own or built in?

The Pythonic way to introduce attributes is to make them public.

It is the difference between

```python
p1.x = p1.x + p2.x
```

and

```python
p1.set_x(p1.get_x() + p2.get_x())
```
Python, instead of using getters and setters, has properties. Properties are essentially getters and setters that you must write yourself, but they are private and only usable within the class. This means that users of the class will use the p1.x notation.

```python
class Robot:

    def __init__(self, name, build_year, lk = 0.5, lp = 0.5 ):
        self.name = name
        self.build_year = build_year
        self.__potential_physical = lk
        self.__potential_psychic = lp

    @property
    def condition(self):
        s = self.__potential_physical + self.__potential_psychic
        if s <= -1:
           return "I feel miserable!"
        elif s <= 0:
           return "I feel bad!"
        elif s <= 0.5:
           return "Could be worse!"
        elif s <= 1:
           return "Seems to be okay!"
        else:
           return "Great!"

if __name__ == "__main__":
    x = Robot("Marvin", 1979, 0.2, 0.4 )
    y = Robot("Caliban", 1993, -0.4, 0.3)
    print(x.condition)
    print(y.condition)
```

### Backing variables?

In C# there's a method where you have variables "Age" and "age" within a class. "Age" is public whereas "age" is private. Getters and setters are written for Age, and then conditions and code are run before the value to be set to Age is set to age. This is an example of a backing variable.

As shown above, running code before setting the actual value is possible. In a sense, this is a backing variable.

### Computed properties?

Python has a mechanism called computed attribute. A computed attribute looks like it directly accesses storage (dot notation) but works like a function. You write the code for an attribute without parentheses or arguments, but accessing it causes a function to be executed.

## Sources
[Properties vs getters and setters](https://www.python-course.eu/python3_properties.php)

[Computed Attributes Using Property Objects](https://wiki.python.org/moin/ComputedAttributesUsingPropertyObjects)
