#                     Home Task 1
# Question No. 1:
Program To compute the Area and Perimeter of a circle provided the radius of circle.

## Pseudo Code:
1. First we'll create a `Circle` Class and take the radius as `double` datatype also make it `private`  . We'll also declare PI as a final datamember and assign it value **3.1412**.
2. As the `double radius` is private we cannot call it from main function so we'll use setter and getter function to pass the valus from main function into the `radius` datamember.
3. Then we'll make two methods named as `computeArea()` and `computePerimeter()`  and write the logic in them.
4. After we have made our class we'll make a main class which will conatin our main function.
5. In the main function we'll make a new object from our class `Circle`
6. We'll take value from the user using a `Scanner`.
7. We'll pass the value from user into `Setter Function`
8. The area and perimeter will be computed after we call the `computeArea()`  and `computePerimeter()` in main function.
9. Close the `Scanner`  at the end of main function.

## Circle Class:
```java
public class Circle {
    private double radius;
    final double PI = 3.1412;

    public void setRadius(double i){
        radius = i;
    }
    public double getRadius(){
        return radius;
    }
    public double computeArea(){
        return PI * Math.pow(getRadius(),2);
    }
    public double computePerimeter(){
        return 2 * PI * getRadius();
    }
}
```

## Main Class:
```Java
import java.util.Scanner;
public class Main {
    public static void main(String[] args){
        Circle myCircle =  new Circle();
        System.out.print("Enter The Radius Of Circle: ");
        Scanner input = new Scanner(System.in);
        double userPrompt = input.nextDouble();
        myCircle.setRadius(userPrompt);
        System.out.printf("\nThe Area of Circle with %.2f radius is %.2f  ",userPrompt,myCircle.computeArea());
        System.out.printf("\nThe Perimeter of Circle with %.2f radius is %.2f\n ",userPrompt,myCircle.computePerimeter());
    }
}

```
# Output:
![[Pasted image 20220919220904.png]]


# Question No.2:
Program to compute the Area and Perimeter of a Rectangle Provided the lenght and width of Rectangle.

## Pseudo Code:
1. We'll make a Class `Rectangle`  and it'll have two datamembers as `int length` , `int height`  and two methods as `int getArea()`  and `getPerimeter()`.
2. We'll simply apply the logic of Area and Perimeter in both methods respectively.
3. After we have made `Rectangle` Class we'' make a new class `Main` which'll have our main function.
4. In main function we'll make a new object from class `Rectangle`  and also declare a new `Scanner` which'll take input from the user.
5. We'll take the value of `length` and `height` from the user and pass them in the methods.
6. we'll print the `return`  value of both methods at the end and close the `Scanner`.

## Rectangle Class:
```java
class Rectangle{
    int length;
    int height;
    int getArea(){
        return length * height;
    }
    int getPerimeter(){
        return (length * 2) + (height * 2);
    }
}
```

## Main Class:
```Java
import java.util.Scanner;

public class Main {
    public static void main(String[] args)
    {
        Rectangle obj = new Rectangle();
        Scanner input = new Scanner(System.in);
        System.out.print("Enter the Length of Rectangle ");
        obj.length = input.nextInt();
        System.out.print("Enter the Height of Rectangle ");
        obj.height = input.nextInt();
        System.out.println("\nThe Area of Rectangle is: " 
        +obj.getArea());
        System.out.println("The Perimeter of Rectangle is: " 
        +obj.getPerimeter());
        input.close();
    }
}
```

# Output:
![[Pasted image 20220919222743.png]]

# Question No. 3
Program to Compute the Quadratic Roots provided the value of `a` , `b`  and `c` . we'll use `setter` and `getter` functions and ignore the iota case.

## Pseudo Case:
1. We'll declare a class `QudraticRoots` it'll have three `private` datamembers `int a,b,c;` and two methods `computeRoots()` and `displayRoots`.
2. we'll declare three `setter` and `getter` function to obtain and `return` the values into private functions.
3. Once the values are passed from `Main` function into `setter` and `getter` funtions we'll pass these values into `computeRoots()`  method. This method will have `double[]` data type because it'll return two roots so we'll store them in an `Array` and return the whole value. Also we'll use `Math.abs` to ignore the iota case.
4. After computation of roots we'll pass the `return` Array into `displayRoots` method to print the roots on screen.

## Rectangle Class:
```Java
class QuadraticRoots{
    private int a,b,c;
    public void setA(int i){
        a = i;
    }
    public int getA() {
        return a;
    }
    public void setB(int j){
        b = j;
    }
    public int getB() {
        return this.b;
    }
    public void setC(int k){
        c = k;
    }
    public int getC() {
        return this.c;
    }
    public double[] computeRoots(){
        double[] roots = new double[2]; //Declaring an Array
        double square1 = Math.pow(b,2); // Taking b square
        double product4AC = 4 * (a * c);// Computing value of 4ac
        double subtraction = Math.abs(square1 - product4AC); //Using Math.abs to ignore iota values
        double squareRoot = Math.sqrt(subtraction); //Taking square root of (b^2-4ac)
        double multiply2A = 2 * a; // computing value of 2a
        double add = -b + squareRoot; //calculation for positive root
        double sub = -b - squareRoot; //calculation for negative root
        roots[0] = (add / multiply2A); //root 1
        roots[1] = (sub / multiply2A); //root 2
        return roots; //returning array which contains the value of roots
    }
    public void displayRoots(double[] roots){
        System.out.printf("\nThe roots are: (%.4f, %.4f)\n", roots[0], roots[1]); //A function which displays the
                                                                                // value of roots
    }
}
```

## Main Class:

```Java
import java.util.Scanner;

public class Main {
        public static void main(String[] args){
            QuadraticRoots qRObject = new QuadraticRoots();
            Scanner input = new Scanner(System.in);

            System.out.print("Enter The Value of A ");
            qRObject.setA(input.nextInt());
            System.out.print("Enter The Value of B ");
            qRObject.setB(input.nextInt());
            System.out.print("Enter The Value of C ");
            qRObject.setC(input.nextInt());
            System.out.println("\nThe Value of A is " +qRObject.getA() +"m");
            System.out.println("The Value of B is " +qRObject.getB() +"m");
            System.out.println("The Value of C is " +qRObject.getC() +"m");
            double[] roots = qRObject.computeRoots();
            qRObject.displayRoots(roots);

        }
    }

```

# Output:
![[Pasted image 20220919224104.png]]
