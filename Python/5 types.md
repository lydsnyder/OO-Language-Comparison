# Types - [Python](https://github.com/lydsnyder/OO-Language-Comparison/blob/master/Python/contents.md)


### What types does the language support?

Python's built-in data types have fall into classes: numeric types, sequences, sets, and mappings.

boolean: true or false

##### Numeric types:

int: integers, non-limited length from Python 3.x
long: long integers, only exist before Python 3.x
float: floating-point numbers, decimals
complex: complex numbers

##### Sequences

str: string; represented as a sequence of 8-bit characters in Python 2.x, but as a sequence of Unicode characters (in the range of U+0000 - U+10FFFF) in Python 3.x
bytes: a sequence of integers in the range of 0-255; only available in Python 3.x
byte array: like bytes, but mutable (see below); only available in Python 3.x
list
tuple

##### Sets

set: an unordered collection of unique objects; available as a standard type since Python 2.6
frozen set: like set, but immutable (see below); available as a standard type since Python 2.6

##### Mappings

dict: Python dictionaries, also called hashmaps or associative arrays, which means that an element of the list is associated with a definition, rather like a Map in Java

---

There are immutable and mutable types in Python. An object’s mutability is determined by its type. Some of these objects like lists and dictionaries are mutable , meaning you can change their content without changing their identity. Other objects like integers, floats, strings and tuples are objects that can not be changed.


### Are both reference and value types supported?

Python uses something called "call by object" or "call by object reference."

If you pass immutable types such as integers, strings, or tuples to a function, they are treated as value.

If you pass mutable types, such as sets and lists, they are call-by-reference.

Immutable are quicker to access than mutable objects. Also, immutable objects are fundamentally expensive to "change", because doing so involves creating a copy. Changing mutable objects is cheap.

### Can new value types be created?

Yes, they can! At runtime, Python sees all objects as variables of type PyObject, which serves as a "base type." PyObject essentially keeps track of how many times an object is referenced and points to the object's "type object." If you want to define a new type, you need to create a new type object.

## Sources:

[Python Type Wiki](https://en.wikibooks.org/wiki/Python_Programming/Data_Types)

[Difference between Mutable and Immutable](http://net-informations.com/python/iq/immutable.htm)
