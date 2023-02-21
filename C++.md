Popular programming language main use is in Game Development. Some concepts are new in c++ And also it is object oriented.

### Hello World in C++

```cpp
#include <iostream>  
using namespace std;  
  
int main() {  
  cout << "Hello World!";  
  return 0;  
}
```

OR

```cpp
#include <iostream>  
  
int main() {  
    std::cout << "Hello, World!" << std::endl;  
    return 0;  
}
```

### Print Output

```cpp
std::cout << "Output here" <<std::endl;
cout << "Output here";
string name = "zohaib";
cout <<"My name is" <<name;
```

### Escape Sequences

```cpp
"\n";   //New line
endl;   //New line
"\t";   //Horizontal Tab space
"\\";   //Insert backslash character
"\"";   //Insert Double Quote
```

### Comments

```cpp
//This is a Comment
/*This is a multiline comment
see it works
This is still a comment*/
```


### Variables or DataTypes
```cpp
int
double
char
string
bool

//_type_ _variableName_ = _value_;
int age = 21;
```


### Naming Conventions
1. Can have numbers, letters and underscores
2. must begin with letter or underscore
3. Variable names are case sensitive
4. No symbols or Whitespaces
5. Reserved words can't be used as variable names

### Constants

```cpp
const int myAge = 21;
//The variable myAge is now unchangeable and is read-only.
```

### User Inputs
```cpp
string x;
cout << "Enter your name:\t";
cin >> x;
cout << x;
```

