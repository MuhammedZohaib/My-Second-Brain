* Writing Bugs 
* Fixing Codes

Bugs are there in the code you just haven't found them yet.

1. Spelling Errors/ Syntax Error.

**Verification:** Did You built it correctly?
**Validation:** Did You build the correct thing?

Verification Error -> Code is Incorrect (Fix the code)
Validation Error -> Doing the wrong thing (Change the code to something different)
New Feature -> No code exists yet (Add code for new feature)

Verification Errors can be easily detected by compiler (Objective & Binary)

Validation focuses on stakeholders need (Not usually syntax error)
Communication is important. (Have a clear communication)
* Unclear Requirements
* Visual / Data Differences
* Business Logic Changes
* Missing Feature (After Usage)

```java

String test = 
"""
hello
This is a multiline valid string
Yay!!!
""";
```

Using assignment opertor(=) instead of comparison operator( == ).

Use `.equals()` to compare two objects.

Use Break statment after every case in a switch.

```java
switch (color){
 case "red" -> System.out.println("In red");
 case "orange" -> System.out.println("In orange");
 case "yellow" -> System.out.println("In yellow");
 default -> System.out.println("In default");
}
```

>There are two hard problems in computer science: cache invalidation, naming things, and off-by-1-errors.

# Off-by-1 Error:
1. Using < instead of <= (Starting or Stopping at wrong index)
2. Infinite Loops


>Debugging is twice as hard as wiriting the code in the first place. Therefore, if you write the code as cleverly as possible, you are by defination, not smart enough to debug it.

* Small Focused methods vs. one giant method
* Group with packages and classes
* Blank Lines, Identification, Spaces
* See Structure and flow of code
* Representative variable names
* Avoid Excessive Abbreviations

**Easier To Read Easier To Debug**

Use libraries instead of building your own already debugged.
We read stack traces from bottom to top.

>*Find The Problem, Fix The Problem*

Debugging is an iterative process.

```java
logger.warn("");
logger.error("");
```

Run-time exceptions are not checked by the compiler.
**Common Runtime Exceptions:**
* NullPointerException (Pointing at a Null Value)
* IndexOutOfBoundException (Refrencing an index which doesn't exist)
* ArithematicException (divide by zero)
* ConcurrentModificationException

We make configuration files to make sure that our program is linked to proper Development database and production Database.

Heap -> Memory Available for Java Execution
Garbage Collection -> Clearing Unused Item from Heap
OutOfMemoryError -> No more heap space available

**Common Causes of OutOfMemoryError**
1. Heap Size isn't big enough
2. Memory Leak (Object that cannot be garbage collected) {Use Memory Profiling Tools}
3. Slow Garbage Collector (More Processing Power, eco mode of hardware)


**Stop the world Garbage Collection:**
Program execution is suspended while Garbage collection completes.
Delay or Longer Response Time

# Try Catch Block:
```java
  try (Scanner input = new Scanner(System.in)) {
            RandomNumberGenerator object = new RandomNumberGenerator();

            System.out.print("Enter a Number\t");
            int number;
            number = input.nextInt();

            System.out.print("Generating a random number between 0 and " + Math.abs(number));
            char quit = 0;

            while (quit != 'q') {
                object.setUserInput(number);
                object.RandomNumber();
                System.out.print("\nEnter 'r' to generate another random number or 'q' to quit the program\t");
                quit = input.next().charAt(0);
            }
        } catch (InputMismatchException e) {
            System.out.println("This is not a Number You Dumdass");;
        }
```

