# Errors and exception handling
The only exceptions in C++ are exceptions explicitly thrown by throw expressions. There are no other exceptions in C++. Dereferencing null pointers, division by zero etc, does not generate exceptions rather it produces undefined behavior.

You can define your own exceptions by inheriting and overriding exception class functionality.
C++ exception handling is built upon three keywords: try, catch, and throw.
```C++
#include <iostream>
#include <exception>
using namespace std;

struct MyException : public exception {
   const char * what () const throw () {
      return "C++ Exception";
   }
};

int main() {
   try {
      throw MyException();
   } catch(MyException& e) {
      std::cout << "MyException caught" << std::endl;
      std::cout << e.what() << std::endl;
   } catch(std::exception& e) {
      //Other errors
   }
}
```
