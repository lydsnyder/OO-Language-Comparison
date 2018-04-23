# Classes

### Defining
Classes are an expansion of data structures that can contain data members as well as functions as members. When you define a class, you define a blueprint for a data type.
```C++
class className {
   access_specifier_1:
      member1;
   access_specifier_2:
      member2;
   ...         
} object_names;
```
### Creating new instances and Constructing/initializing
* Classes can be instantiated by calling the class's constructors. Constructors are often used to set up initial values for data in the new object and to
allocate space for sub-objects.

* A constructor will have exact same name as the class and it does not have any return type at all, not even void.

```C++
class Line {
   public:
      Line();           // Default constructor
      Line(double len); // parameterized constructor
   private:
      double length;
};
// Constructor definitions
Line::Line(){
  cout << "Object is being created";
}
Line::Line(double len){
  cout << "Object is being created, length = " << len << endl;
  length = len;
}
```

* There are two ways to create an object in C++:

```C++
MyClass myclass; // if you only need to call the default constructor
MyClass myclass(10); // if you need to call constructor with parameters

// Second method
MyClass *myclass = new MyClass(); // if you only need to call the default constructor
MyClass *myclass = new MyClass(12); // if you need to call constructor with parameters
```
with the use of 'new' keyboard, the object is stored in the heap rather than the stack, thus the scope of the use of the object will be longer.
### Destructing/de-initializing
When delete is called on an object, C++ calls its destructor function
which deallocates storage within the object.

A class cannot have more than one destructor.
```C++
delete myclass;
```
