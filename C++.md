# C++ Programming Concepts

C++ is a popular programming language with a main use in Game Development. It introduces new concepts and is known for its object-oriented nature.

## Hello World in C++

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

## Printing Output

```cpp
std::cout << "Output here" << std::endl;
cout << "Output here";
string name = "zohaib";
cout << "My name is " << name;
```

## Escape Sequences

```cpp
"\n";   // New line
endl;   // New line
"\t";   // Horizontal Tab space
"\\";   // Insert backslash character
"\"";   // Insert Double Quote
```

## Comments

```cpp
// This is a Comment
/* This is a multiline comment
   see it works
   This is still a comment */
```

## Variables or DataTypes

```cpp
int
double
char
string
bool

// _type_ _variableName_ = _value_;
int age = 21;
```

## Naming Conventions

1. Can have numbers, letters, and underscores
2. Must begin with a letter or underscore
3. Variable names are case-sensitive
4. No symbols or whitespaces
5. Reserved words can't be used as variable names

## Constants

```cpp
const int myAge = 21;
// The variable myAge is now unchangeable and read-only.
```

## User Inputs

```cpp
string x;
cout << "Enter your name:\t"; // Insertion Operator
cin >> x; // Extraction Operator
cout << x;
getline(cin, variable);
```

## Dynamic Array (Ambiguous Way)

```cpp
int *list = (int*) malloc(3 * sizeof(int)); // Dynamic Array of size 3
list[0] = 1; // Adding elements to dynamic array
list[1] = 2; list[2] = 3;

// Need to add more elements to the array, so making a temporary array of size 4
int *tmp = (int*) malloc(4 * sizeof(int));
// Deep copy old elements of Array into new temporary Array
for(int i = 0; i < 3; i++) {
    tmp[i] = list[i];
}
// Adding new element to the temporary array
tmp[3] = 4;
// Free the memory of the old/original array
free(list);
// Point it at the new temporary array
list = tmp;

// Prompt the elements of dynamically resized array
for(int i = 0; i < 4; i++) {
    cout << list[i];
    cout << "\n";
}
// Free the original array to return the memory
free(list);
```

In the above example, we dynamically allocated an array of size 3 into the heap, added elements to it, expanded it to size 4, and then free the memory.

## Dynamic Array

```cpp
// Create a dynamic array of size 5
int *ptr = (int *) malloc(5 * sizeof(int));
// Adding elements to Array
ptr[0] = 1;
ptr[1] = 2;
ptr[2] = 3;
ptr[3] = 4;
ptr[4] = 5;

// Reallocating the size of ptr array
int *tmp = (int *) realloc(ptr, 7 * sizeof(int));
// Adding more elements to the resized Array
tmp[5] = 6;
tmp[6] = 7;

// Prompting the elements of the array
for(int i = 0; i < 7; i++) {
    cout << tmp[i];
}
// Free heap allocation after use
free(tmp);
```

```cpp
// Give clean blocks with no garbage values
int *ptr = (int *) calloc(5, sizeof(int));
```

Using the following, we can access memory in any way we want:

```cpp
struct
*
.
-> // Go to a memory and look into it, syntactic sugar for * and .
```

- A Pointer typically takes 8 bytes or 64 bits of space in memory.
- We are always making a trade between space and time: either use more space and save time, or use more time and save space.

This Markdown structure organizes your notes into sections, provides code snippets with proper formatting, and improves the readability of your content.

