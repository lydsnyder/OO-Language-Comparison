# Multithreading

### Threads or thread-like abilities
C++ does not provide built-in support for multithreading, instead it relies entirely upon the operating system to provide this feature.
### How is multitasking accomplished?
However, if you are working on Linux OS, then you can write multi-threaded C++ program using POSIX, or Pthreads.

```C++
#include <pthread.h>
pthread_create (thread, attr, start_routine, arg)

pthread_exit (status)
```
