# Moore's Law:
Every year or two, the capacities of computers have
approximately doubled inexpensively. This remarkable trend
often is called Moore’s Law, named for the person who
identified it in the 1960s, Gordon Moore, co-founder of Intel
—the leading manufacturer of the processors in today’s
computers and embedded systems.

-> Java Uses Unicode which is composed of 8,16 or 32 bits.

* Analysis
* Requirements
* Design

The software that contains the core components of the operating system is called **The kernel**

-> Windows is built on top of DOS.
-> Apple, founded in 1976 by Steve Jobs and Steve Wozniak
-> Swift --> Introduced in 2014 --> Became open source in 2015
-> Android is based on Linux Kernel and Java.
-> Android apps can also be developed in C and C++.
->Python -> 1991
->Ruby -> Mid 1990

# Types of Errors:
1. Run time Error
2. Fatal Run time Error
3. Non-Fatal Runtime Error

-> By default, package `java.lang`  is imported in every Java program; thus, classes in java.lang are the only ones in the Java API that do not require an import declaration.

-> The int values you use in a program may not contain commas; however, for
readability, you can place underscores in numbers. So 60_000_000 represents the int value 60,000,000

-> Exception Handling and fault tolerant.
-> Portions of statements that contain calculations are called expressions.
-> redundant means not necessary.

# Precedence:
\1. Multiplication, division and remainder operations are applied first. If an
expression contains several such operations, they’re applied from left to
right. Multiplication, division and remainder operators have the same level
of precedence.
2. Addition and subtraction operations are applied next. If an expression
contains several such operations, the operators are applied from left to
right. Addition and subtraction operators have the same level of
precedence.

Never Use `printf` to print a `String` while taking input from the user as it can result in security breach as malicious user can supply format specifier and execute through `printf`.

# Inheritance:
*When creating a class, rather than declaring completely new members, you can designate that the new class should inherit the members of an existing class. The existing class is called the super-class, and the new class is the subclass*

***Inheritance is sometimes referred to as specialization.*

## *Protected Members:*
*A class’s `public` members are accessible wherever the program has a reference to an object of that class or one of its sub classes. A class’s `private` members are accessible only within the class itself. In this section,we introduce the access modifier `protected`. Using protected access offers an intermediate level of access between public and private.*

We use `.super` to refer to the parent class.

## *Behavior of Constructors in Inheritance:*
Constructors are not inherited.