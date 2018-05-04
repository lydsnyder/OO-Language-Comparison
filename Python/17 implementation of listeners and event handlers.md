# Implementation of listeners and event handlers - [Python](https://github.com/lydsnyder/OO-Language-Comparison/blob/master/Python/contents.md)

It appears that Python's implementation of listeners and event handlers is sometimes inspired by C#'s approach. A simple implementation from [here](https://emptypage.jp/notes/pyevent.en.html).

```python
# event.py (simple)

class Event(object):

    def __init__(self):
        self.handlers = []

    def add(self, handler):
        self.handlers.append(handler)
        return self

    def remove(self, handler):
        self.handlers.remove(handler)
        return self

    def fire(self, sender, earg=None):
        for handler in self.handlers:
            handler(sender, earg)

    __iadd__ = add
    __isub__ = remove
__call__ = fire
```

It does seem that event systems are crowd-sourced. As shown in this stackoverflow [here](https://stackoverflow.com/questions/1092531/event-system-in-python).

" The most basic style of event system is the 'bag of handler methods', which is a simple implementation of the Observer pattern. Basically, the handler methods (callables) are stored in an array and are each called when the event 'fires'.

The disadvantage of these event systems is that you can only register the handlers on the actual Event object (or handlers list). So at registration time the event already needs to exist.

That's why the second style of event systems exists: the publish-subscribe pattern. Here, the handlers don't register on an event object (or handler list), but on a central dispatcher. Also the notifiers only talk to the dispatcher. What to listen for, or what to publish is determined by 'signal', which is nothing more than a name (string). "
