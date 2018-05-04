# Name spaces - [Python](https://github.com/lydsnyder/OO-Language-Comparison/blob/master/Python/contents.md)


### How are name spaces implemented?

A namespace (or sometimes called context) is a system for ensuring that there is not ambiguity for names. Namespaces in Python are implemented as Python dictionaries, this means it is a mapping from names (keys) to objects (values).

### How are name spaces used?

The abovementioned Python dictionaries lends to explaining Python namespaces as such.

Think of a dictionary key-- the key represents the name. The actual content or dictionary values are an object. Everything in Python is an object, so the namespaces just map the names to the objects.

These namespaces have a hierarchy or scope.
The different scopes are local, enclosed, global, built-in.

    Local  can be inside a function or class method, for example.
    Enclosed can be its enclosing function, e.g., if a function is wrapped inside another function.
    Global refers to the uppermost level of the executing script itself, and
    Built-in are special names that Python reserves for itself.

They can exist independently from each other. The hierarchy is displayed in the below picture.

![  Scope Hierarchy](https://sebastianraschka.com/images/blog/2014/scope_resolution_legb_rule/scope_resolution_1.png)

## Sources:

[Python Course](https://www.python-course.eu/namespaces.php)

[A Beginner's Guide to Python's ...](http://sebastianraschka.com/Articles/2014_python_scope_and_namespaces.html)
