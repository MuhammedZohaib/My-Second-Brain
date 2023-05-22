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

``` java
 Node head;  
 Node tail;  
int count = 0;  
  
  
public void insertLast(int Data){  
    Node newNode = new Node(Data);  
    if(head == null){  
        head = newNode;  
        tail = newNode;  
    }  
    else{  
        Node tmp = head;  
        while (tmp.next != null){  
            tmp = tmp.next;  
        }  
        tmp.next = newNode;  
        tail = newNode;  
    }  
    count++;  
}  
public void insertStart(int Data){  
    Node newNode = new Node(Data);  
    if(head == null){  
        head = newNode;  
        tail = newNode;  
    }  
    else{  
        newNode.next = head;  
        head = newNode;  
    }  
    count++;  
}
public void display() {  
    Node tmp = head;  
    while (tmp != null){  
        System.out.print(tmp.getData()+" ");  
        tmp = tmp.next;  
    }  
}
```

# Trees:
Insertion and Searching is efficient. 
Every individual element is known as a node. Each node stores actuall data and refrence to the next node.

## Terminologies:
- `Root`: First Node is known as root node. Every tree must have a root node. It is the origin of a tree. There should be only one root node in any tree.
- `Edge:` In any tree the connecting link between any two nodes is known as an edge. Tree with N node will have N-1 edges.
- `Parent:` In a tree, The predecessor of any node is known as Parent Node. "*The node which has a child.*"
- `Child:` In a tree, the node which is decendant of any node is known as a child. A Parent can have any number of childs in a tree.
- `Siblings:` In a tree, nodes which belong to same Parent are called as siblings.
- `Leaf:` The node which does not have a child is known as leaf node. A node with no child. Leaf nodes are also known as external nodes or terminal nodes.
- `Internal Nodes:` The node which has atleast one child is known as internal node. They are also known as non-terminal nodes.
- `Degree:` The total number of children of a node is known as it's degree. while the highest degree among all nodes is known as the degree of the tree. 
- `Level:` The root node is at level 0 similary the childs are on Level 1 and the level keep on increasing.
- `Height:` The total number of edges from leaf node to a particular node in the longest  
  path is called as HEIGHT of that Node. The height of root node is said to be the height of the tree. while the height of all leaf nodes is 0.
- `Depth:` The total number of edges from root node to a particular node is called  
  as DEPTH of that Node. The total number of edges from root node to a leaf node in the  
  longest path is said to be Depth of the tree. Depth of root node is 0.
- `Path:` The sequence of nodes and edges from one node to another is known as path between that two nodes.
- `Sub-tree:` Every child node forms a sub-tree on it's parent node. Every Parent node forms a sub tree.

## Representations:
1. List Representation
2. Left Child - Right Sibling Representation

## Binary Tree:
Binary tree is a special type of tree data structure in which every node can have a maximum of 2 children. One is known as left child and the other is known as right child. A tree in which every node can have a maximum of two children is called as Binary Tree. Every node can have either 0 children or 1 child or 2 children but not more than 2 children

### Types of Binary Trees:
- `Strictly Binary Tree`: Every Node must have 2 children or none. Also known as Full-Binary Tree or Proper Binary Tree or 2-Tree.
- `Complete Binary Tree:` In a complete binary tree each level should have 2^n nodes where n is number of level. At level 2 there should be 4 nodes and 8 nodes at level 3. Also known as Perfect Binary tree.
- `Extenden Binary Tree:` A binary tree can be converted into Full Binary tree by adding dummy nodes to existing nodes wherever required. The full binary tree obtained by adding dummy nodes to a binary tree is called as Extended Binary Tree.

# Tree as ADT:
- `size(root)` return the total number of nodes
- `isEmpty(root)` wether tree is empty or not
- `root()` returns the root node of tree
- `parent(node)` returns parent of the node
- `children(node)` returns list of all childs of node
- `isInternal(node)` return true if node is not a leaf node 
- `isExternal(node)` return true if node is a leaf
- `isRoot(node)` return true if node is a root node

## Binary Tree ADT:
- `left(node)` returns left child of node
- `right(node)` returns right child of node
- `hasLeft(node)` tells if a node has left child or not
- `hasRight(node)` tells if a node has right child or not
- `siblings(node)` returns sibling of given node

# Tree Traversals:
Visiting each node of tree once
- Breadth First Search (Level Traversal- Complete one level first and then move to the next level) (Queue is used in BFS)
- Depth First Search 
  - Pre-Order (Simple DFS) (Node, left, right)
  - In-Order (Left, Right, Node)
  - Post-Order (Left, Node, Right)


