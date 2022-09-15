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

