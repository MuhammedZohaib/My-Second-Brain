Access Modifiers:
 * public 
 * private
 * protected
 * default

Use of access modifiers:
One complete file of code is known as package.

A package with public access modifiers can be accessed in another separate package.

Data members with private access modifiers can't even be used in main() function. We use 
`Setter`
`Getter`

to access data members and methods of a private class/object.

```java
private String a = "Zohaib";

public void setName(String n){
name = n;
}
public String getName(String n){
return name;
}
```

```java
public void setId(i){
int i;
}
public void getId(i){
return id;
}
```

```java
/**
*This is a multiline comment
*Ok
*Mohammed Zohaib
*OOP
**/
```

`java.lang` is a default package it is automatically imported.
String are non-primtitve data types they have there own methods and properties.
Non-Primitive datatypes are also known as Reference datatyes.
The variables in a class are known as attributes.
To create a String as a attribute we need to make `Constructor` because `String ` is a refrence datatype and is a type of `class`

we can make more than one object from a object.

Difference b/w value type and refrence type.

Write Attributes first and then methods in a class.
The order doesn't matter in java we can call method anywhere in the class.

Once we assign a variable a value through scanner it becomes `static`
# Constructor:
There are two types of constructors:
* Non-Parameterized -> No Parameters
* Parameterized -> Has Parameters

We can make more than one constructor in a `class`

constructor has the same name as of the `class` name. Constructor is a special method of a class which can take parameters.

# Functions:
Functions can of two types:
1. User defined functions
2. In-built functions

A function can be recursive and can be non-recursive.

`reutrn type functionName(arguments)`

Example of a recursive function:

```java
public static int facrtorial(int num){
	if (num<=1){
	return 1;
	}
	return num * factorial(num - 1);
}
```


The below is know as Type Casting:
```java
int x = (int) 5.6;
//It will convert 5.6 to int type 5.
//Results in data loss
```

```java
double y = 5.5;
int x = (int) y;
```

`char` can have only one character we can use numbers also as `char`

`String`  is a special class.
If we compare two `String` using == it'll actually compare the location of memory rather than content of the `String`  so we use `.equals` method of `String` to compare two `Strings`

To compare `int` type we use ==

# LOOPS:
1. Initialization
2. Condition
3. Termination



Argument Promotion -> Going from small data type to big data type.
Like from `int` to `double`

Overloading -> Same method name with different datatype and different arguments.

In `static` methods we can simply use the method by using the `class` name.
`static` methods doesn't need new object to be accessed it can be simply accessed by using class name.

```java
className.methodName();
```

Shadow Parameters -> When we use same parameter names in class this is known as Shadow Parameters. We use `this` keyword to refer to the shadow parameters.

The `static` method belongs to class if we directly change the value in a `static` method it'll change the value of all the associated objects of that `class` while if we make a new object and change the value of that `static` method it'll only change the value of that method of new object.
method -> `static` is know as instance method.


We can use loops to make 100's of objects from a `class` and later store them as a collection.

```java
int x = 5; //primitive Datatype
Integer y = 4; //object(Instance of a class) or Class Type
/* The class Type gives us number of methods to apply.*/
```

`null` -> absence of a value

We can make multiple classes and instantiate the object of one class into another class.

```java
class Main{
	public static main void(String[] args){
		Name object = new Name();
		object.myAge.age; //We are accessing age field of class Age
		}
	}
```

```java
class Name{
	String x;
	Age myAge = new Age();
}
```

```java
class Age{
	int age;
}
```


# Arguments and Parameters:
The datatypes/values/inputs we pass to a method are known as arguments.

The variables that we use in blue print of a method are known as parameters.
`Arguments` are the value we pass when we call a method.
>we can say that `parameters` are the placeholders of `arguments`.

```java
public int sum(int num1, int num2){ //here num1 and num2 are parameters
	return num1 + num2;
}
```

```java
	sum(2,3); //here 2,3 are known as arguments
```

# Method Overloading:
-> Type Promotion.
Same name for methods with different parameters or different datatypes.
We can also use type promotion along with method overloading.
We can also overload `main` function.



# Arrays:
In Java every array is an object. we can store both primitive and non-primitive data types in it.
There is no pass by reference in Java. But we can still achieve it.
The number of rows and column of Arrays is same in C language. But we can also use jagged array in Java which have different number of rows and columns.

* Rectangular Array
* Jagged Array/ Ragged Array

```java
//Example of Jagged/ Ragged Array
BankAccount[][] jArray = new BankAccount[3][];  
jArray[0] = new BankAccount[1];  
jArray[1] = new BankAccount[3];  
jArray[2] = new BankAccount[2];
```

Index number should be non-negative

## Declaring An Array:
```java 
int [] c = new int [12];
// Can also be done in two steps

int[] c;
c = new int [12];

int[] array1,array2;  //both are arrays

int array1[], array2; //array1 is array while array2 is variable
```

Type array is a reference to an object.

Partially Filled Arrays.
Dynamically Filled Arrays.
Array initialiser List.

Simple for loop is known as counter control loop.
Enhanced for loop can only be used to iterate over the elements of an Array.

`.length`  gives the length of Array.

```java
int [][] arr2D = new int[2][3];

for(int i = 0; i < arr2D.length; i++){
	for(int j = 0; j < arr2D[i].length; j++){
	
	}
}

for(int[] x: arr2D){
	for(int y : x){
	}
}
```

The `.add()` method in array works as it takes the array as argument takes the length of the array and add the element to the array as the array now has one more index place for element because we added 1 to the `array lenght`

**Auto-Boxing:** Automatic conversion of primitive types to the object of their corresponding wrapper classes is known as auto-boxing.

**Unboxing:** It is just the reverse process of auto-boxing. Automatically converting an object of a wrapper class to its corresponding primitive type is known as unboxing.

```java
JOptionPane.showInputDialog();
//Opens a dialog box like prompt
```

# Iterator Object:
It is used to iterate over a collection like Array List
```java
Iterator<ObjectsInArrayLists> iterator = arrayLists.iterator();  
if( control == 'p') {  
    while(iterator.hasNext()){  
        System.out.print(iterator.next().toString()+" ");  
    }  
}
```

Java conserves storage by maintaining only one copy of each method per class this method is invoked by every object of the class. Each object, on the other hand, has its own copy of the class’s instance variables.

```java
throw new IllegalArgumentException("Type Exception Here");
```

* ***Default values (zero for primitive numeric types, false for
   boolean values and null for references)**

* *Classes should never have public non-constant data, but declaring data public static final enables you to make constants available to clients of your class.*

* Another common use for access methods is to test whether a condition is true or false—such methods are often called predicate methods. 

>Use a static variable when all objects of a class must use the same copy of the variable.
>Referring to this in a static method is a compilation error.

```java
NumberFormat.getCurrencyInstance().format(amount)
```

# Command Line Arguments:
```java
public class Message
{
public static void main(String[] args)
{
if (args.length == 0 || args[0].equals("-h"))
System.out.print("Hello,");
else if (args[0].equals("-g"))
System.out.print("Goodbye,");
// print the other command-line arguments
for (int i = 1; i < args.length; i++)
System.out.print(" " + args[i]);
System.out.println("!");
}
}
```

# Making A .jar file:
```java
jar cvf jarFileName file1 file2...

```

# Override:
To change the functionality of a in built method so it work only with the class in which it is overridden.

