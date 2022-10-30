Till now we have `Arrays` for storing data but they are not enough, Thats why we need `Collections`

> Why Arrays aren't Good Enough?

Because we need to specifiy the length of the array. with only Arrays we cannot make a resiable array. we must define the size of array first before we can use it.
If we use only arrays in our programs our code will be extensive and we'll have to do alot of effort which will reduce productivity.

**Collections of Collections:**
-> Collections
   --> **List** {Array List, Linked List}
   --> **Set**{Hash Set} ,**Sorted Set**{Tree Set}
   -->**Queue** {Priority List},**Double Ended Queue**{Linked List, Array Deque}
   -->**Map** {Hash Map},**Sorted Map**{Tree Map}

Map is a collection of pairs.

A collection has two or more than two components.
**Interfaces**
* Multiple Different Data Structures
* Functional Characteristics
* Prefer as Variable Type

**Implementation of Interfaces**
* Specific data structures.
* Performance Characteristics
* Concrete and Instantiation

`Are elements keyed or not?`
> `Order is Important?
> If order is important use sorted map else use map
> `Elements must be unique?
> If Order is important then use sorted set else use set
> `Does Insertion Order Matter?
> If insertion order matter use Double end Que else use list.

![[Pasted image 20221014031827.png]]

**Collection Behavior:**
1. `size()`
2. `isEmpty()`
3. `add(element)`
4. `addAll(collection)` 
5. `remove(element)`
6. `removeAll(collection)`
7. `retainAll(collection)`
8. `contains(element)`
9. `containsAll(collection)`
10. `clear()`
11. `removeIf(product -> product.weight() > 20)`
12. `iterator()`
13. `hasNext()`
14. `next()`
15. `indexOf()`
16. `lastIndexOf()`
17. 

Lists are the most popular form of collection

1. Array Lists
2. Linked Lists

**Key Features Of Lists:**
* Lists are collections with iteration order {Every Element in the list has an index associated with it which determines its position in the list. starts from 0} 
```java
void add(int index, E e);
E get(int index);
E remove(int index);
E set(int index, E element);
boolean addAll(int index, Collection c);
```

Sub lists are views. Over ranges of Lists
Modifying the view modifies the list.

```java
List subList(int fromIndex, int toIndex);
```

```java
list.sort(Comparator<? Super E > comparator)
```

# Storing Value form user in Array List:
```java
import java.util.ArrayList;  
import java.util.Scanner;  
  
public class Main {  
    public static void main(String[] args) {  
        Scanner input = new Scanner(System.in);  
        var products = new ArrayList<>();  
        System.out.print("Enter Products to add to wishlist or quit to exit\t");  
        while(input.hasNextLine()){  
            String user = input.nextLine();  
            if(user.equals("quit")){  
                break;  
            }  
            else {  
                products.add(user);  
            }  
        }  
        System.out.println(products);  
  
    }  
}
```
