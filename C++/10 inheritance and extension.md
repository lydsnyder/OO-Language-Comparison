# Inheritance / extension
The idea of inheritance in C++ implements the same "is a" relationship similar to Java. However, unlike Java, C++ supports multiple inheritance. A class can inherit from more than one base class.

When deriving a class from a base class, the base class may be inherited through public, protected or private inheritance.

```C++
// Base class
class Shape {
   public:
      void setWidth(int w) {
         width = w;
      }
      void setHeight(int h) {
         height = h;
      }

   protected:
      int width;
      int height;
};

// Derived class
class Rectangle: public Shape {
   public:
      int getArea() {
         return (width * height);
      }
};
```
Depending on the access modifier of the inheritance, members of the base class will be treated differently. For example, protected and public members of a private base class will become private members of the derived class.
