# Types

### What types does the language support?
* Character types
  * char
  * char16_t
  * char32_t
  * wchar_t
* Integer types (signed)
  * signed char
  * signed short int
  * signed int
  * signed long int
  * signed long long int
* Integer types (unsigned)
  * unsigned char
  * unsigned short int
  * unsigned int
  * unsigned long int
  * unsigned long long int
* Floating-point types
  * float
  * double
  * long double
* Boolean types
  * bool
* Void type
  * void
* Null pointer
  * decltype(nullptr)

### Are both reference and value types supported?
Both reference and value types are supported when assigning a variable or passing variable to an another function.
```C++
int add(int x, int y){ // Pass by value
  return x+y;
}
int subtraction(int *x, int *y){ // Pass by reference
  return x-y;
}
int main(){
  int x = 2;
  int y = 3;
  int sum = add(x,y);
  int sub = subtraction(&x,&y);
}
```
### Can new value types be created?
* Structs is a group of data elements grouped together under one name
```C++
struct type_name{
  member_type1 member_name1;
  member_type2 member_name2;
  member_type3 member_name3;
} object_names;
```
* Unions declaration and use are similar to structs, but all its members share the same physical space in memory. Modifying one of the members will affect all the other members.
```C++
union type_name{
  member_type1 member_name1;
  member_type2 member_name2;
  member_type3 member_name3;
} object_names;
```
* Enumeration is a distinct type whose value is restricted to a range of values. Default values start at zero for the first constant and increase by one.
```C++
enum colors_t {red, green, blue}
```
