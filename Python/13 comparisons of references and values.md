# Comparisons of references and values - [Python](https://github.com/lydsnyder/OO-Language-Comparison/blob/master/Python/contents.md)


### How are values compared? (i.e. comparing two strings)

"is" will return True if two variables point to the same object, == if the objects referred to by the variables are equal.

The == operator compares by checking for equality: If these cats were Python objects and we’d compare them with the == operator, we’d get “both cats are equal” as an answer.

The is operator, however, compares identities: If we compared our cats with the is operator, we’d get “these are two different cats” as an answer.

Say we have lists a, b, and c

```python

a = [1, 2, 3]
b = a
a == b
outputs: True

a is b
outputs: False

c = [1, 2, 3]
a == c
outputs: True

a is c
outputs: False
```

## Sources

[The difference between is and equals in python](https://dbader.org/blog/difference-between-is-and-equals-in-python)
