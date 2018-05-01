# Comparisons of references and values

### How are values compared? (i.e. comparing two strings)

Strings are compared with the std::string::compare(), public member function of string class:

```C++
if(s1.compare(s2) == 0){
  // They match
}
```
Other data types are compared with the == operator.
