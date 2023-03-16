# Resources:

1. `MIT Course Youtube Series`
2. `MyCode School YT Series`
3. `Algorithms Design manuale by Steven S. Skiena`
4. `Algorithms By Robert Sedgewick, Kevin Wayne`
5. `Intro to Data Structures and Algoritms by Google (Udacity)`


# Algorithms:
1. `Sorting`
2. `Recursion`
3. `Searching`
4. `Cache Algorithms`
5. `Tree Algorithms`
6. `Greedy Algorithms`
7. `BackTracking`
8. `Substring Search`
9. `Suffix Arrays`
10. `Dynamic Programming`
11. `Divide and Conquer`
12. `Branch and Bound
13. `Hashing`



## Searching
* `Linear Search`
* `Binary Search`
* `Depth Search`
* `Depth First Search`
* `Breadth Search`
* `Breadth First Search`
* `Suffix Arrays Search`
* `Search Pattern in Text`x

## Sorting
* `Insertion Sort`
* `Selection Sort`
* `Heap Sort`
* `Merge Sort`
* `Quick Sort`
* `Counting Sort`
* `Bubble Sort`

## Graphs
* `Kruskal's Algo`
* `Dijkstra's Algo`
* `Bellman Ford Algo`
* `Floyd Warshall Algo`
* `Topological Sort Algo`
* `Flood Fill Algo`
* `Lee Algo`

## Arrays
* `Kadane's Algo`
* `Floyd's Cycle Detection Algo`
* `KMP Algo`
* `Quick Select Algo`
* `Boyer- More Majority vote Algo`

## Basic
* `Huffman Coding Compression Algo`
* `Euclid's Algo`
* `Union Find Algo`


# Data Structures
* Array
* Graph
* Heap
* Linked List
* Stack
* Queue
* Hash Table
* Tree
* `Sets`
* `Maps`


O(n^2)
O(n log n)
O(n)
O(log n)
O(1)


## Stack
1. Array
2. Linked List
LIFO data Structure, Last In First Out.  

```java
Push() 
Pop() 
Peek()
Search()
isEmpty()
```

* If we try to pop from empty stack `EmptyStackException`
* The search method of Stack gives the index of element in the stack if it is present in the stack else it returns -1. Also the index start from last element pushed and it starts from 1 instead of 0.
* We can run out of memory in stack if we push too many items then it throws `OutOfMemoryError`

APPLICATIONS:
1. undo/redo features
2. back forward in browsers
3. backtracking algorithms (maze, file directories)
4. function call stack


## Queue
1. Circular Queue
2. Double Ended Queue
3. Single Ended Queue
4. Priority Queue
5. With array
6. With linked List

FIFO, First In First Out
We maintain head and tail in the queue. FIrst come first serve mechanism is followed.
In java if we want to instantiate a queue it'll not allow us to do because in java queue is an interface.  Priority Queue and Linked List implements queue interface. Queue Interface extends Collection class. 

```java
// method after the arrow are prefered because these methods does not throw exceptions
enqueue(),add() -> offer() //Add to the tail 
dequeue(),remove() -> poll() //Remove from the head
peek(),element() -> peek()

isEmpty()
size()
contains()
```

APPLICATIONS:
1. Keyboard Buffer (Letters Appear in the order they are pressed)
2. Printer Queues
3. Breadth-first Search

## Priority Queue
Serves elements with higher priority first before elements with lower priority.


### Linked List
1. Double Ended Linked List (Head and Tail)
2. Single Ended Linked List (Head Only)

Has advantage over array. Consists of nodes. Node contains two parts one is the data part and other is the address part. In a singly linked list each node knows the location or address of the next node. We need to main only a head in the singly linked list. The end of the singly linked list is determined by the null in the address block.
Doubly linked list (Memory Inefficient) even require more space because it need to store two address along with the data. We maintain both head and tail along with a previous and next memory block in the node. The major benefit is we can traverse from head to tail or from tail to head.  In java By default a doubly linked list is created. The doubly linked list implements the deque or double ended queue interface. 
Linked list behaves as a stack
```java
//Doubly Linked List
addFirst()
addLast()
removeFirst()
removeLast()
getFirst()
getLast()

offerFirst()
offerLast()
pollFirst()
pollLast()
peekFirst()
peekLast()
```
Linked Lists are bad at searching. 
* Insertion and deletion is O(1) while searching is O(n) in singly linked list
* 


