# Memory management - [Python](https://github.com/lydsnyder/OO-Language-Comparison/blob/master/Python/contents.md)


### How is it handled?

Python's memory allocation and deallocation method is automatic. The Python memory manager manages the memory. It is a private heap containing all Python objects and data structures.

### How does it work?

There is a memory allocator that ensures that there is enough room in the private heap for storing.
There are also object-specific allocators that operate on the same private heap and implement policies adapted to every object type. This means that types are treated differently on the heap. An integer would be handled differently than a tuple because they have different storage requirements. The Python memory manager delegates tasks to these allocators but ensures that they remain within the bounds of the heap.

### Garbage collection?

Python schedules garbage collection based upon a threshold of object allocations and object deallocations. When the number of allocations minus the number of deallocations are greater than the threshold number, the garbage collector is run. One can inspect the threshold for new objects (objects in Python known as generation 0 objects) by loading the gc module and asking for garbage collection thresholds:

```python
import gc
print "Garbage collection thresholds: %r" % gc.get_threshold()
```

### Automatic reference counting?

Previously, Python only used reference counting for memory management. Every object is a descendent of Object, and Object has a value in it that keeps track of the number of times an object is referenced by other objects in the system. When the number of references drops to zero, the object is deallocated. Currently, this works in tandem with the garbage collection.

## Sources

[Python Garbage Collection](https://www.geeksforgeeks.org/garbage-collection-python/)
