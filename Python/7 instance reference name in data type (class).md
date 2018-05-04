# Instance reference name in data type (class) - [Python](https://github.com/lydsnyder/OO-Language-Comparison/blob/master/Python/contents.md)


### this? self?

Python uses self() as an instance reference name. Say we have a class as defined below:

```python
class Restaurant(object):
    bankrupt = False
    def open_branch(self):
        if not self.bankrupt:
            print("branch opened")
```

If we instantiate that class,

```python
x = Restaurant()
```

we now have a restaurant that has the boolean property bankrupt and a function open_branch.

If we were to make another restaurant and set its bankrupt to true, the original restaurant's bankrupt would still be false.

```python
x = Restaurant()
x.bankrupt
output: False

y = Restaurant()
y.bankrupt
output: False
y.bankrupt = True
y.bankrupt
output: True

x.bankrupt
output: False
```

## Sources:

[The self variable in Python - Pythontips.com](https://pythontips.com/2013/08/07/the-self-variable-in-python-explained/)
