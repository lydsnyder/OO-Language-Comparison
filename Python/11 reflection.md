# Reflection - [Python](https://github.com/lydsnyder/OO-Language-Comparison/blob/master/Python/contents.md)

### What reflection abilities are supported?

As per the Python documentation, the reflection abilities supported are:

```python
PyObject* PyEval_GetBuiltins()
```
* Return value: Borrowed reference.
* Return a dictionary of the builtins in the current execution frame, or the interpreter of the thread state if no frame is currently executing.

```python
PyObject* PyEval_GetLocals()
```
* Return value: Borrowed reference.
* Return a dictionary of the local variables in the current execution frame, or NULL if no frame is currently executing.

```python
PyObject* PyEval_GetGlobals()
```
* Return value: Borrowed reference.
* Return a dictionary of the global variables in the current execution frame, or NULL if no frame is currently executing.

```python
PyFrameObject* PyEval_GetFrame()
```
* Return value: Borrowed reference.
* Return the current thread state’s frame, which is NULL if no frame is currently executing.

```python
int PyFrame_GetLineNumber(PyFrameObject *frame)
```
* Return the line number that frame is currently executing.

```python
int PyEval_GetRestricted()
```
* If there is a current frame and it is executing in restricted mode, return true, otherwise false.

```python
const char* PyEval_GetFuncName(PyObject *func)
```
* Return the name of func if it is a function, class or instance object, else the name of funcs type.

```python
const char* PyEval_GetFuncDesc(PyObject *func)
```
* Return a description string, depending on the type of func. Return values include “()” for functions and methods, ” constructor”, ” instance”, and ” object”. Concatenated with the result of PyEval_GetFuncName(), the result will be a description of func.

### How is reflection used?

A language that has reflection is able to, during runtime, examine, modify and maintain its inner structure. This example shows how one might print names of attributes, methods, and doc strings at runtime.

```python
class Obj:
 """ An object that use reflection """

 def __init__(self,name):
  """ the constructor of this object """
  self.name = name

 def print_methods(self):
  """ print all the methods of this object and their doc string"""
  print '\n* Methods *'
  for names in dir(self):
   attr = getattr(self,names)
   if callable(attr):
    print names,':',attr.__doc__

 def print_attributes(self):
  """ print all the attributes of this object and their value """
  print '* Attributes *'
  for names in dir(self):
   attr = getattr(self,names)
   if not callable(attr):
    print names,':',attr

 def print_all(self):
  """ calls all the methods of this object """
  for names in dir(self):
   attr = getattr(self,names)
   if callable(attr) and names != 'print_all' and names != '__init__':
    attr() # calling the method

o = Obj('the my object')
o.print_all()
```

This outputs:

```python
* Attributes *
__doc__ :  An object that use reflection
__module__ : __main__
name : the my object

* Methods *
__init__ :  the constructor of this object
print_all :  calls all the methods of this object
print_my_attributes :  print all the attributes of this object
print_my_methods :  print all the methods of this object

```

## Sources
[Reflection](https://docs.python.org/2/c-api/reflection.html)
[Reflection in Python](http://www.assembleforce.com/2012-08/reflection-in-python.h)
[How to use reflection](https://glowingpython.blogspot.com/2011/07/how-to-use-reflection.html)
