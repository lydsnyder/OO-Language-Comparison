# Interfaces / protocols

### What does the language support?
The C++ interface is implemented by the use of abstract class.
### What abilities does it have?
The purpose of an abstract class is to provide an appropriate base class from which other classes can inherit. They cannot be used to instantiate objects and serves only as an interface.
### How is it used?
A class is made abstract by declaring at least one of its functions as pure virtual function.
```C++
class Rectangle {
  public:
    // pure virtual function
    virtual double getArea() = 0;
  private:
    double width;
    double height;
};
```
