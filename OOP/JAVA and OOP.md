# Recommended Book: 
Java How to Program.
Java Has Object Technology Concept.
Information Hiding on advance Level.

# Diff. b/w class and obj:
* Drawing a class
Drawing is a class is like making a blueprint for making objects with certain properties and objects. This doesn't allocate any space in memory.
* Buiding an Object
Building an Object is like making a new object from a class. it allocates space in system memory and can use properties and methods of its class.

# Instantaion:
Creating an Object from its class is known as instantaion of its class. Because object is an instance/image of its class.

# Reuse:
Declaring Classes allow reuse of code.
Saves Time and Effort.

# Inheritence:
In inheritance we inherit properties and methods from a class to create another class and can be modified later.
Save time while creating new classes.

# Building Block Approach of Java:
We Can re-use available blocks of code in Java.

## Insatnce Variable:
An _instance variable_ is a variable which is declared in a class but outside of constructors, methods, or blocks.
Value of the attribute in the object is know as Instance Object.

# Object-Oriented Analysis and Design
* Code
* Analysis
* Requirements
* Design

# Intro To JAVA:
"Write Once, Run Everywhere".
Gives Portability. 
Oracle in 2009.

Java has rich class libraries.
Import Libraries as Java API.

## Phases in Java Programming:
* Edit 
* Compile
* Load
* Verify
* Execute

We use .`java` extension at the end of java file.

# Compiling of A Java Program:
When we compile a Java program it does'nt convert our code to machine language rather it converts it to **Bytecode**
After Compilation is successful it creates a `.class` file which contains bytecode of source code.
Bytecodes are executed by JVM{Java Virtual Machine}.
Class Name and File name should be same in Java.

* Loads a program into memory
* Bytecode Verification

Gives us Just in TIme Compilation.
*  Source code to Bytecode
* Bytecode to Machine Language

# Java Syntax:
Public -> Available To all
Private -> Ownership of some entity

Only one Public class can be used.
further sub-classes can be used more than once.
Pascal case is used for classes and camel case of variables.
`String[]`  is a datatype.
`main` indicates that execute this function first.
`args`  -> arguments which can be given after compiliation while running program in Terminal.

we Use `%s` for string as format specifier.

## Input:
```java
//This is used to print only string
System.out.println("Hello");

//This can be used to print variables and other datatypes
System.out.printf("Hello %s", String[]);

```
## Output:
```Java
/*we can use this to do mathematical claculations and print in terminal as output*/
System.out.println(3 + 3);
```

we can also use 
```java
System.out.print("Hello World! ");
```

# Variables:
Following are the datatypes:
* `String`
* `int`
* `float`
* `char`
* `boolean`

## Declaring a variable:
```java
type variableName = value;
```
As,
```java
String name = "John";
System.out.println(name);
```
 we can create a variable that can store numbers we can approach as:
```java
int myNum = 15;
System.out.println(myNum);
```

if we want to create a constant variable then we use `final` keyword.
```java
final int myNum = 15;
//The value of myNum can't be changed it'll always be 15.
```

Other examples of variables are:
```java
int myNum = 5;
float myFloatNum = 5.99f;
char myLetter = 'D';
boolean myBool = true;
String myText = "Hello";
```

# Displaying Varibales:
We use `println` to display variables and use + symbol for concatenation.

```java
String name = "John";
System.out.println("Hello " + name);
```

further on concatenation :

```java
String firstName = "John ";
String lastName = "Doe";
String fullName = firstName + lastName;
System.out.println(fullName);
```

for displaying variable we use formatted print method as:
```java
public class DisplayVariable{
	public static void main(String[] args){
		int x = 1;
		int y = 2;
		int sum;
		sum = x + y;
		System.out.printf("The sum of %d and %d is %d\n", x, y, sum);
	}
}
```

We can declare multiple variables separated by commas , as:

```java
int x = 5, y = 6, z = 50;
System.out.println(x + y + z);
```

we can assign multiple variables same value by using = sign as:

```java
int x, y, z;
x = y = z = 50;
System.out.println(x + y + z);
//Output will be 150
```

All variable should be given unique names which are known as identifiers.

# DataTypes:
```java
int myNum = 5;               // Integer (whole number)
float myFloatNum = 5.99f;    // Floating point number
char myLetter = 'D';         // Character
boolean myBool = true;       // Boolean
String myText = "Hello";     // String
```

There are two types of data types:
* Primitive DataTypes
* Non-Primitive DataTypes

### Primitive DataTypes:
-> `byte` 1-byte
-> `short` 2-bytes
-> `int` 4-bytes
-> `long` 8-bytes
->`float` 4-bytes
->`double` 8-bytes
->`boolean` 1-bit
->`char`  2-byte

These are further divided into two types:
* Integer Types `byte` `short` `int` `long` 
* Floating Types `float` `double`

#### Byte:
Can store values from -128 to 127. It can be used instead of int to save memory.

#### Short:
The `short` data type can store whole numbers from -32768 to 32767.

#### Int:
The `int` data type can store whole numbers from -2147483648 to 2147483647.

#### Long:
The `long` data type can store whole numbers from -9223372036854775808 to 9223372036854775807.
**Important:**
```java
long myNum = 15000000000L;
```

#### Float and Double:
The `float` and `double` data types can store fractional numbers. Note that you should end the value with an "f" for floats and "d" for doubles.
```java
float myNum = 5.75f;
```
```java
double myNum = 19.99d;
```

A floating point number can also be a scientific number with an "e" to indicate the power of 10.

#### Boolean Type:
A boolean data type is declared with the `boolean` keyword and can only take the values `true` or `false`.
```java
boolean isJavaFun = true;
boolean isFishTasty = false;
System.out.println(isJavaFun);     // Outputs true
System.out.println(isFishTasty);   // Outputs false
```

#### Characters:
The `char` data type is used to store a **single** character. The character must be surrounded by single quotes, like 'A' or 'c'.
```java
char myGrade = 'B';
System.out.println(myGrade);
```

Alternatively, if you are familiar with ASCII values, you can use those to display certain characters:
```java
char myVar1 = 65, myVar2 = 66, myVar3 = 67;
System.out.println(myVar1);
System.out.println(myVar2);
System.out.println(myVar3);
```

#### Strings:
The `String` data type is used to store a sequence of characters (text). String values must be surrounded by double quotes.

```java
String greeting = "Hello World";
System.out.println(greeting);
```



### Non-Primitive DataTypes:
Non-primitive data types are called **reference types** because they refer to objects.
The main difference between **primitive** and **non-primitive** data types are:
-   Primitive types are predefined (already defined) in Java. Non-primitive types 
 are created by the programmer and is not defined by Java (except for `String`).
-   Non-primitive types can be used to call methods to perform certain operations, while primitive types cannot.
-   A primitive type has always a value, while non-primitive types can be `null`.
-   A primitive type starts with a lowercase letter, while non-primitive types starts with an uppercase letter.
-   The size of a primitive type depends on the data type, while non-primitive types have all the same size.

Examples of non-primitive types are [Strings](https://www.w3schools.com/java/java_strings.asp), [Arrays](https://www.w3schools.com/java/java_arrays.asp), [Classes,](https://www.w3schools.com/java/java_classes.asp) [Interface](https://www.w3schools.com/java/java_interface.asp), etc. You will learn more about these in a later chapter.

->`String`
->`Arrays`
->`Classes`
->`Object`
->`Interface`


# Java Type Casting

Type casting is when you assign a value of one primitive data type to another type.
In Java, there are two types of casting:
-   **Widening Casting** (automatically) - converting a smaller type to a larger type size  
    `byte` -> `short` -> `char` -> `int` -> `long` -> `float` -> `double`  
-   **Narrowing Casting** (manually) - converting a larger type to a smaller size type  
    `double` -> `float` -> `long` -> `int` -> `char` -> `short` -> `byte`







