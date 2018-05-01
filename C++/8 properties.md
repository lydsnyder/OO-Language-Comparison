# Properties

### Getters and setters…write your own or built in?
You need to write your own getters and setters.
```C++
private:
  char grade;
public:
  char getGrade(){
    return grade;
  }
  void setGrade(char grade){
    this.grade = grade;
  }
```
### Backing variables?
A private field that stores the data exposed by a public property is called a backing store or backing field. However, it is not available in C++.
### Computed properties?
Unfortunately, C++ does not support computed properties. Properties in C++ involve writing out each function for each setter and getter.
