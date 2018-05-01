# Memory management

### How is it handled?
 C++ supports malloc(),calloc() and free() functions to allocate and deallocate memory dynamically but it also has two operators new and delete that perform the task of allocating and freeing the memory in a better and easier way.
### How does it work?
The main advantage of new over calloc() is that new doesn't just allocate memory, it constructs object which is prime purpose of C++.

Also, unlike malloc, C++ is type-aware, meaning no casting is required.

```C++
pointer-variable = new data-type;

delete pointer-variable;
```
### Garbage collection?
Garbage collection is an optional support for C++.
C++ supports a powerful idiom called RAII (resource acquisition is initialization) that can be used to safely and automatically manage resources including memory.
### Automatic reference counting?
C++ offers reference counting with the std::shared_ptr class
