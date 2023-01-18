# Recommended Book: 
Java How to Program.


Java Has Object Technology Concept.
Information Hiding on advance Level.

# Diff. b/w class and obj:
* Drawing a class
Drawing is a class is like making a blueprint for making objects with certain properties and objects. This doesn't allocate any space in memory.
* Building an Object
Building an Object is like making a new object from a class. it allocates space in system memory and can use properties and methods of its class.

# Instantiation:
Creating an Object from its class is known as instantiation of its class. Because object is an instance/image of its class.

# Reuse:
Declaring Classes allow reuse of code.
Saves Time and Effort.

# Inheritance:
In inheritance we inherit properties and methods from a class to create another class and can be modified later.
Save time while creating new classes.

**Super-Class, Base Class, Parent Class** -> *Parent*
**Sub-Class, Derived Class, Child Class** -> *child*
To inherit from a class, use the `extends` keyword.

```java
class Vehicle {
  protected String brand = "Ford";        // Vehicle attribute
  public void honk() {                    // Vehicle method
    System.out.println("Tuut, tuut!");
  }
}

class Car extends Vehicle {
  private String modelName = "Mustang";    // Car attribute
  public static void main(String[] args) {

    // Create a myCar object
    Car myCar = new Car();

    // Call the honk() method (from the Vehicle class) on the myCar object
    myCar.honk();

    // Display the value of the brand attribute (from the Vehicle class) and the value of the modelName from the Car class
    System.out.println(myCar.brand + " " + myCar.modelName);
  }
}
```

We set the **brand** attribute in **Vehicle** to a `protected` access modifier. If it was set to `private`, the Car class would not be able to access it.

If you don't want other classes to inherit from a class, use the `final` keyword.

#### Why And When To Use "Inheritance"?
- It is useful for code re-usability: reuse attributes and methods of an existing class when you create a new class.

*Call the constructor of the Employee super-class with n, s, year,
month, and day as parameters:*
```java
public Manager(String name, double salary, int year, int month, int day)
{
super(name, salary, year, month, day);
bonus = 0;
}
```

```java
//Form Class to Class
extends
//Form Interface to Interface
extends
//Form Interface to Class
implements
```


# Polymorphism:
Polymorphism means "many forms", and it occurs when we have many classes that are related to each other by inheritance.**Polymorphism** uses inherited methods to perform different tasks. This allows us to perform a single action in different ways.

```java
class Animal {
  public void animalSound() {
    System.out.println("The animal makes a sound");
  }
}

class Pig extends Animal {
@Override
  public void animalSound() {
    System.out.println("The pig says: wee wee");
  }
}

class Dog extends Animal {
@Override
  public void animalSound() {
    System.out.println("The dog says: bow wow");
  }
}
```



# Building Block Approach of Java:
We Can re-use available blocks of code in Java.

## Instance Variable:
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
* Load into memory
* Byte-code Verification
* Execute

We use .`java` extension at the end of java file.

# Compiling of A Java Program:
When we compile a Java program it doesn't convert our code to machine language rather it converts it to **Byte-code**
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
`args`  -> arguments which can be given after compilation while running program in Terminal.

we Use `%s` for string as format specifier.

## Input:
`println`  has new line.

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
In Java Variables are known as Data Members.
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

# Displaying Variables:
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

# Datatypes:
```java
int myNum = 5;               // Integer (whole number)
float myFloatNum = 5.99f;    // Floating point number
char myLetter = 'D';         // Character
boolean myBool = true;       // Boolean
String myText = "Hello";     // String
```

There are two types of data types:
* Primitive Datatypes
* Non-Primitive Datatypes

### Primitive Datatypes:
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



### Non-Primitive Datatypes:
Non-primitive data types are called **reference types** because they refer to objects.
The main difference between **primitive** and **non-primitive** data types are:
-   Primitive types are predefined (already defined) in Java. Non-primitive types are created by the programmer and is not defined by Java (except for `String`).
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

#### Java Strings:
Strings are used for storing text.
A `String` variable contains a collection of characters surrounded by double quotes.
```java
String greeting = "Hello";
```

### String Methods:
* `.lenght()`  It gives you the length of the string.
* `.toUpperCase()` Converts string to Upper Case
* `.toLowerCase()` Converts string to Lower Case
* `.indexOf("Part of String")` Gives the Index Number of specific text in String
* `.concate()` sum up two strings
* `.string1.equals(string2)` Check whether `string1` is equal to `string2` (Case Sensitive).
* `.string1.equalsIgnoreCase(string2)` (Not case Sensitive)
* `.lastIndexOf("")` last occurrence of sub string.
* `.replace("Substring", "New Substring") `
* `.substring`
* `.split("-")`
* `.trim()`  removes extra white spaces form `String`
* 


# Java Type Casting

Type casting is when you assign a value of one primitive data type to another type.
In Java, there are two types of casting:
-   **Widening Casting** (automatically) - converting a smaller type to a larger type size  
    `byte` -> `short` -> `char` -> `int` -> `long` -> `float` -> `double`  
-   **Narrowing Casting** (manually) - converting a larger type to a smaller size type  
    `double` -> `float` -> `long` -> `int` -> `char` -> `short` -> `byte`




# Inserting Special Chracters:
* `\'` This will insert single quote
* `\"` This will insert double quote
* `\\` This will insert Backslash
* `\n` New line
* `\r` Moves cursor to start of line
* `\t` Tab Spacing
* `\b` Backspace
* `\f` Form Feed

# Java Math:
* `Math.max(x,y)` It is used to find maximum of two values
* `Math.min(x,y)` It is used to find minimum of two values
* `Math.sqrt(x)` It gives square root of a value
* `Math.abs(x)` It converts negative values to positive values
* `Math.random()` It will generate a random number between 0.0 and 1.0
* `Math.pow(x,2)` It will give us power of a number x

# Java Booleans:
The Boolean value of an expression is the basis for all Java comparisons and conditions.

# Java If...Else:
Supported Conditions:
* `a < b`
* `a <= b`
* `a > b`
* `a >=b`
* `a == b`
* `a != b`

Java has the following conditional statements:
* `if`
* `else`
* `else if`
* `switch`

## Terniary Operator:
```java
variable = (condition) ? expressionTrue :  expressionFalse;
```

```java
String result = (time < 18) ? "Good day." : "Good evening.";
```

# Switch:
```java
switch(expression) {
  case x:
    // code block
    break;
  case y:
    // code block
    break;
  default:
    // code block
}
```

# While:
The number of loop through the code is not defined in while loop
```java
int i = 0;
while (i < 5) {
  System.out.println(i);
  i++;
}
```
# DO While:
```java
do {
  // code block to be executed
}
while (condition);
```

# For Loop:
When you know exactly how many times you want to loop through a block of code, use the `for` loop instead of a `while` loop:
```java
for (statement 1; statement 2; statement 3) {
  // code block to be executed
}
```

```java
for (int i = 0; i < 5; i++) {
  System.out.println(i);
}
```

# For Each Loop:
There is also a "**for-each**" loop, which is used exclusively to loop through elements in an arrays:
```java
for (type variableName : arrayName) {
  // code block to be executed
}
```

```java
String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
for (String i : cars) {
  System.out.println(i);
}
```

## Java Arrays

Arrays are used to store multiple values in a single variable, instead of declaring separate variables for each value.

To declare an array, define the variable type with **square brackets**:
```java
String[] cars;
```
```java
String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
```
```java
int[] myNum = {10, 20, 30, 40};
```
 We can access the number of elements of the string by using index number.
 The number of element in an array is known as index number.
 It starts with 0.
  
## Two Dimensional Arrays:
A multidimensional array is an array of arrays.
To create a two-dimensional array, add each array within its own set of **curly braces**:
```java
int[][] myNumbers = { {1, 2, 3, 4}, {5, 6, 7} };
```
**myNumbers** is now an array with two arrays as its elements.
To access the elements of the **myNumbers** array, specify two indexes: one for the array, and one for the element inside that array. This example accesses the third element (2) in the second array (1) of myNumbers:

```java
int[][] myNumbers = { {1, 2, 3, 4}, {5, 6, 7} };
int x = myNumbers[1][2];
System.out.println(x); // Outputs 7
```

# Object Creation:

```java
Animal a = new Animal();
```

 We use . notation to call data members and methods of an object.

# Package Keyword:
Makes whole code as a package.

```java
Package class_name;
```

# Import Keyword:
```java
import java.*;
```

# Bitwise Operators:
* `~` Compliment
* `&` and
* `|` or
* `^` xor
* `<<` Shift two bits to left
* `>>` Shift two bits to right

# Java Methods:
A **method** is a block of code which only runs when it is called.
You can pass data, known as parameters, into a method.
Methods are used to perform certain actions, and they are also known as **functions**.
Why use methods? To reuse code: define the code once, and use it many times.

Create a method inside Main:

```java
public class Main {
  static void myMethod() {
    // code to be executed
  }
}
```

# Java Method Parameters:
Information can be passed to methods as parameter. Parameters act as variables inside the method.

```java
public class Main {
  static void myMethod(String fname, int age) {
    System.out.println(fname + " is " + age);
  }

  public static void main(String[] args) {
    myMethod("Liam", 5);
    myMethod("Jenny", 8);
    myMethod("Anja", 31);
  }
}
```

The `void` keyword, used in the examples above, indicates that the method should not return a value. If you want the method to return a value, you can use a primitive data type (such as `int`, `char`, etc.) instead of `void`, and use the `return` keyword inside the method:

# Java Method Overloading:
With **method overloading**, multiple methods can have the same name with different parameters:

```java
static int plusMethod(int x, int y) {
  return x + y;
}

static double plusMethod(double x, double y) {
  return x + y;
}

public static void main(String[] args) {
  int myNum1 = plusMethod(8, 5);
  double myNum2 = plusMethod(4.3, 6.26);
  System.out.println("int: " + myNum1);
  System.out.println("double: " + myNum2);
}
```

Multiple methods can have the same name as long as the number and/or type of parameters are different.

# Java Scope:
In Java, variables are only accessible inside the region they are created. This is called **scope**.

## Block Scope:
A block of code refers to all of the code between curly braces `{}`.
Variables declared inside blocks of code are only accessible by the code between the curly braces, which follows the line in which the variable was declared:

```java
public class Main {
  public static void main(String[] args) {

    // Code here CANNOT use x

    { // This is a block

      // Code here CANNOT use x

      int x = 100;

      // Code here CAN use x
      System.out.println(x);

   } // The block ends here

  // Code here CANNOT use x

  }
}
```

In Simple words we can say that there are ni global variiables in Java.

# Java Recursion:
Recursion is the technique of making a function call itself. This technique provides a way to break complicated problems down into simple problems which are easier to solve.
Recursion may be a bit difficult to understand. The best way to figure out how it works is to experiment with it.

# Relational Operators:
* `==`
* `<`
* `>`
* `>=`
* `<=`
* `!=`

# Java Classes/Objects

Java is an object-oriented programming language.
Everything in Java is associated with classes and objects, along with its attributes and methods. For example: in real life, a car is an object. The car has **attributes**, such as weight and color, and **methods**, such as drive and brake.
The variables declared in a class are known as Attributes.

A Class is like an object constructor, or a "blueprint" for creating objects

```java
public class Main {
  int x = 5;
}
``````java
public class Main {
  int x = 5;
}
```


Remember from the [Java Syntax chapter](https://www.w3schools.com/java/java_syntax.asp) that a class should always start with an uppercase first letter, and that the name of the java file should match the class name.

Create an object called "`myObj`" and print the value of x:

```java
public class Main {
  int x = 5;

  public static void main(String[] args) {
    Main myObj = new Main();
    System.out.println(myObj.x);
  }
}
```

# Static Vs Public:
Attributes and methods can have either `static`  or `public`
`static` means it can be called form the main function without creating a new object of the `class` while `public` methods can only be accessed by objects.

```java
public class Main {
  // Static method
  static void myStaticMethod() {
    System.out.println("Static methods can be called without creating objects");
  }

  // Public method
  public void myPublicMethod() {
    System.out.println("Public methods must be called by creating objects");
  }

  // Main method
  public static void main(String[] args) {
    myStaticMethod(); // Call the static method
    // myPublicMethod(); This would compile an error

    Main myObj = new Main(); // Create an object of Main
    myObj.myPublicMethod(); // Call the public method on the object
  }
}
```


## Calling Methods:
The dot (`.`) is used to access the object's attributes and methods.
To call a method in Java, write the method name followed by a set of parentheses **()**, followed by a semicolon (`;`).
A class must have a matching filename (`Main` and **Main.java**).

# Java Consturctors:
A constructor in Java is a **special method** that is used to initialize objects. The constructor is called when an object of a class is created. It can be used to set initial values for object attributes.

```java
// Create a Main class
public class Main {
  int x;  // Create a class attribute

  // Create a class constructor for the Main class
  public Main() {
    x = 5;  // Set the initial value for the class attribute x
  }

  public static void main(String[] args) {
    Main myObj = new Main(); // Create an object of class Main (This will call the constructor)
    System.out.println(myObj.x); // Print the value of x
  }
}

// Outputs 5
```

**Important:**
Note that the constructor name must **match the class name**, and it cannot have a **return type** (like `void`).
Also note that the constructor is called when the object is created.
All classes have constructors by default: if you do not create a class constructor yourself, Java creates one for you. However, then you are not able to set initial values for object attributes.

## Constructor Parameters

Constructors can also take parameters, which is used to initialize attributes.

The following example adds an `int y` parameter to the constructor. Inside the constructor we set x to y (x=y). When we call the constructor, we pass a parameter to the constructor (5), which will set the value of x to 5:

```java
public class Main {
  int x;

  public Main(int y) {
    x = y;
  }

  public static void main(String[] args) {
    Main myObj = new Main(5);
    System.out.println(myObj.x);
  }
}

// Outputs 5
```

# JAVA Modifiers:
## Access Modifiers 
Controls the access level

-> `class` can either be `public` means available to all or `default` means available in same package only. `default` is set if we don't specify any access modifier.
-> For `attributes` `methods` and `constructors` we can use 
* `public` (The code is accessible for all classes) 
* `private` (The code is only accessible within the declared class)
* `default` (The code is only accessible in the same package. This is used when you don't specify a modifier.)
* `protected` (The code is accessible in the same package and **sub-classes**)


## Non-Access Modifiers
Do not control access level, but provides other functionality.
-> `class` can either be
* `final` (The class cannot be inherited by other classes)
* `abstract` (The class cannot be used to create objects. To access an abstract class, it must be inherited from another class)
-> For `attributes` and `methods`
* `final` (Attributes and methods cannot be overridden/modified)
* `static` (Attributes and methods belongs to the class, rather than an object)
* `abstract` (Can only be used in an abstract class, and can only be used on methods. The method does not have a body, for example **abstract void run();**. The body is provided by the subclass (inherited from).)
* `transient` (Attributes and methods are skipped when serializing the object containing them).
* `synchronzied` (Methods can only be accessed by one thread at a time)
* `volatile` (The value of an attribute is not cached thread-locally, and is always read from the "main memory")

->A `static` method means that it can be accessed without creating an object of the class.
->An `abstract` method belongs to an `abstract` class, and it does not have a body.


# Inner Classes:
In Java, it is also possible to nest classes (a class within a class). The purpose of nested classes is to group classes that belong together, which makes your code more readable and maintainable.
To access the inner class, create an object of the outer class, and then create an object of the inner class:

```java
class OuterClass {
  int x = 10;

  class InnerClass {
    int y = 5;
  }
}

public class Main {
  public static void main(String[] args) {
    OuterClass myOuter = new OuterClass();
    OuterClass.InnerClass myInner = myOuter.new InnerClass();
    System.out.println(myInner.y + myOuter.x);
  }
}
```

Inner classes are a security mechanism in Java. We know a class cannot be associated with the access modifier `private`, but **if we have the class as a member of other class**, then the inner class can be made private. And this is also used to access the private members of a class.


