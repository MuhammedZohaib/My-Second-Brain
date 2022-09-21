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

Difference b/w value type and refrence type.

Write Attributes first and then methods in a class.
The order doesn't matter in java we can call method anywhere in the class.


# Constructor:




