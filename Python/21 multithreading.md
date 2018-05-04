# Multithreading - [Python](https://github.com/lydsnyder/OO-Language-Comparison/blob/master/Python/contents.md)


### Threads or thread-like abilities

Python does have thread-like abilities!

### How is multitasking accomplished?

To spawn a thread, you have to import one of the thread modules. The following code is how you would create a thread using the "thread" module:

```python
thread.start_new_thread ( function, args[, kwargs] )
```

There is a more recent module called "threading" that provides more control.

```python
#!/usr/bin/python

import threading
import time

exitFlag = 0

class myThread (threading.Thread):
   def __init__(self, threadID, name, counter):
      threading.Thread.__init__(self)
      self.threadID = threadID
      self.name = name
      self.counter = counter
   def run(self):
      print "Starting " + self.name
      print_time(self.name, 5, self.counter)
      print "Exiting " + self.name

def print_time(threadName, counter, delay):
   while counter:
      if exitFlag:
         threadName.exit()
      time.sleep(delay)
      print "%s: %s" % (threadName, time.ctime(time.time()))
      counter -= 1

# Create new threads
thread1 = myThread(1, "Thread-1", 1)
thread2 = myThread(2, "Thread-2", 2)

# Start new Threads
thread1.start()
thread2.start()

print "Exiting Main Thread"
```

This "threading" module includes useful functions for synchronizing, such as lock(). If you import the Queue module, it allows you to set a multithread queue and control it!

## Sources

[Python Multithreading](https://www.tutorialspoint.com/python/python_multithreading.htm)
