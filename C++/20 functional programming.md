# Functional programming

### Does the language support functional programming?

* Yes but partially.

* Instead of treating functions as objects (like true functional programming), C++ renders lambdas as a class with an operate method:
```C++
auto println = [](const char  *message){ std::cout << message << std::endl;};
```
