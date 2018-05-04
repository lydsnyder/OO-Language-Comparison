# Errors and exception handling - - [Python](https://github.com/lydsnyder/OO-Language-Comparison/blob/master/Python/contents.md)

In Python, there are syntax errors and exceptions.

Syntax errors are like any other language, parsing errors.

Exceptions handling is done with try statements.

```python
>>> while True:
...     try:
...         x = int(input("Please enter a number: "))
...         break
...     except ValueError:
...         print("Oops!  That was no valid number.  Try again...")
...
```

The try statement works as follows.

* First, the try clause (the statement(s) between the try and except keywords) is executed.
* If no exception occurs, the except clause is skipped and execution of the try statement is finished.
* If an exception occurs during execution of the try clause, the rest of the clause is skipped. Then if its type matches the exception named after the except keyword, the except clause is executed, and then execution continues after the try statement.
* If an exception occurs which does not match the exception named in the except clause, it is passed on to outer try statements; if no handler is found, it is an unhandled exception and execution stops with a message as shown above.

It is good practice to have more than one clause to have specific handling.

## Sources

[Handling Exceptions](https://docs.python.org/3/tutorial/errors.html#handling-exceptions)
