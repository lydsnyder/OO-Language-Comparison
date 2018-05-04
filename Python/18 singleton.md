# Singleton - [Python](https://github.com/lydsnyder/OO-Language-Comparison/blob/master/Python/contents.md)


### How is a singleton implemented?

Apparently in Python there is no single way to implement a singleton. It appears to be much debated what the best way to implement it is [per this discussion](https://stackoverflow.com/questions/6760685/creating-a-singleton-in-python).

I've gathered that the "best" way, according to the limited sample size of stackoverflow, is by using metaclasses.

```python
class Singleton(type):
    _instances = {}
    def __call__(cls, *args, **kwargs):
        if cls not in cls._instances:
            cls._instances[cls] = super(Singleton, cls).__call__(*args, **kwargs)
        return cls._instances[cls]

class Logger(object):
    __metaclass__ = Singleton
```

Another example of a singleton is found [here](http://python-3-patterns-idioms-test.readthedocs.io/en/latest/Singleton.html).

```python
# Singleton/SingletonMetaClass.py
class SingletonMetaClass(type):
    def __init__(cls,name,bases,dict):
        super(SingletonMetaClass,cls)\
          .__init__(name,bases,dict)
        original_new = cls.__new__
        def my_new(cls,*args,**kwds):
            if cls.instance == None:
                cls.instance = \
                  original_new(cls,*args,**kwds)
            return cls.instance
        cls.instance = None
        cls.__new__ = staticmethod(my_new)

class bar(object):
    __metaclass__ = SingletonMetaClass
    def __init__(self,val):
        self.val = val
    def __str__(self):
        return `self` + self.val

x=bar('sausage')
y=bar('eggs')
z=bar('spam')
print(x)
print(y)
print(z)
print(x is y is z)
```
### Can it be made thread-safe?

Yes, it can be made thread safe. It does seem to be fairly involved, though, as shown in this github example by [werediver](https://gist.github.com/werediver/4396488).

### Can the singleton instance be lazily instantiated?

Yes, it can!

An example of how it can is shown on the wikipedia for lazy initialization:

```python
class Fruit:
    def __init__(self, item):
        self.item = item

class Fruits:
    def __init__(self):
        self.items = {}

    def get_fruit(self, item):
        if item not in self.items:
            self.items[item] = Fruit(item)

        return self.items[item]

if __name__ == '__main__':
    fruits = Fruits()
    print(fruits.get_fruit('Apple'))
    print(fruits.get_fruit('Lime'))
```

## Sources

[Singleton](http://python-3-patterns-idioms-test.readthedocs.io/en/latest/Singleton.html)
[Lazy Initialization](https://en.wikipedia.org/wiki/Lazy_initialization#Python)
