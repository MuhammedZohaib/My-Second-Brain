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

Shaodow Parameters -> When we use same parameter names in class this is known as Shadow Parameters. We use `this` keyword to refer to the shadow parameters.

The `static` method belongs to class if we directly change the value in a `static` method it'll change the value of all the associated objects of that `class` while if we make a new object and change the value of that `static` method it'll only change the value of that method of new object.
method -> `static` is know as instance method.


We can use loops to make 100s of objects from a `class` and later store them as a collection.

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
