# Instance reference name in data type (class)


### this? self?
Every object in C++ has access to its own address through the pointer "this". "This" pointer is not available in static member functions as static member functions can be called without any object.
```C++
class MyClass
{
private:
   int x;
public:
   void setX (int x)
   {
       // The 'this' pointer is used to retrieve the object's x
       // hidden by the local variable 'x'
       this->x = x;
   }
};
```
