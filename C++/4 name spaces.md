# Namespaces

### How are name spaces implemented?
* Namespaces allow us to group named entities that otherwise would have global scope into narrow scopes.

* Using namespaces, we can create two variables or member functions having the same name.

* Namespace is a feature added in C++ and not present in C.

* Multiple namespace blocks with the same name are allowed.

* Namespace declarations don't have access specifiers like public or private.

### How are name spaces used?

* Namespaces are used to differentiate between variables, functions that share the same name but belong to different and same libraries.

```C++
#include <iostream>
using namespace std;
namespace ns1{
  int val = 5;
  int value() {
    return val;
  }
}
namespace ns2{
  double val = 5;
  double value(){
    return 2*val;
  }
}
int val = 100;

int main(){
  cout << ns1::value() << "\n";
  cout << ns2::value() << "\n";
  cout << val << "\n";
}
```
outputs: 5, 10, 100
