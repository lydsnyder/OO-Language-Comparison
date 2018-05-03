# Singleton

### How is a singleton implemented?
```C++
class Singleton
{
    private:
        static Singleton* instance;
        // private constructor to force use of
        // getInstance() to create Singleton object
        Singleton();

    public:
        /* Static access method. */
        static Singleton* getInstance();
};

Singleton* Singleton::getInstance()
{
    if (instance == NULL)
        instance = new Singleton();
    return instance;
}

```

### Can the singleton instance be lazily instantiated?
Yes, singletons can be lazy instantiated by making them static inside the function but it is not thread safe because it creates two objects for one singleton when running two threads for example.
```C++
static Object& getInstance()
{
	static Object instance;
	return instance;
}
```
