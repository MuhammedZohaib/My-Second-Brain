# Resources:

1. MIT Course Youtube Series
2. MyCode School YT Series
3. Algorithms Design Manual by Steven S. Skiena
4. Algorithms By Robert Sedgewick, Kevin Wayne
5. Intro to Data Structures and Algorithms by Google (Udacity)

# Algorithms:
1. Sorting
2. Recursion
3. Searching
4. Cache Algorithms
5. Tree Algorithms
6. Greedy Algorithms
7. BackTracking
8. Substring Search
9. Suffix Arrays
10. Dynamic Programming
11. Divide and Conquer
12. Branch and Bound
13. Hashing

## Searching
* Linear Search
* Binary Search
* Depth Search
* Depth First Search
* Breadth Search
* Breadth First Search
* Suffix Arrays Search
* Search Pattern in Text

## Sorting
* Insertion Sort
* Selection Sort
* Heap Sort
* Merge Sort
* Quick Sort
* Counting Sort
* Bubble Sort

## Graphs
* Kruskal's Algo
* Dijkstra's Algo
* Bellman Ford Algo
* Floyd Warshall Algo
* Topological Sort Algo
* Flood Fill Algo
* Lee Algo

## Arrays
* Kadane's Algo
* Floyd's Cycle Detection Algo
* KMP Algo
* Quick Select Algo
* Boyer-Moore Majority Vote Algo

## Basic
* Huffman Coding Compression Algo
* Euclid's Algo
* Union Find Algo

# Data Structures
* Array
* Graph
* Heap
* Linked List
* Stack
* Queue
* Hash Table
* Tree
* Sets
* Maps

## Stack
1. Array
2. Linked List

LIFO data Structure, Last In First Out.

Methods:
- `Push()`
- `Pop()`
- `Peek()`
- `Search()`
- `isEmpty()`

Notes:
- Trying to pop from an empty stack results in `EmptyStackException`.
- The `search` method gives the index of an element (1-indexed) in the stack or -1 if not found.
- Memory can run out if too many items are pushed, resulting in `OutOfMemoryError`.

Applications:
1. Undo/redo features
2. Back/forward in browsers
3. Backtracking algorithms (maze, file directories)
4. Function call stack

## Queue
1. Circular Queue
2. Double Ended Queue
3. Single Ended Queue
4. Priority Queue
5. With array
6. With linked List

FIFO data structure, First In First Out.

Methods:
- `enqueue()` or `add()` -> `offer()` (Add to the tail)
- `dequeue()` or `remove()` -> `poll()` (Remove from the head)
- `peek()` or `element()` -> `peek()`

Notes:
- Methods after the arrow (`->`) are preferred as they do not throw exceptions.
- The `Queue` interface extends the `Collection` class in Java.

Applications:
1. Keyboard buffer (letters appear in the order they are pressed)
2. Printer queues
3. Breadth-first search

## Priority Queue
Serves elements with higher priority first before elements with lower priority.

### Linked List
1. Double Ended Linked List (Head and Tail)
2. Single Ended Linked List (Head Only)

A linked list consists of nodes, each containing data and a reference to the next node.

Types:
- **Singly Linked List**: Each node has a reference to the next node.
- **Doubly Linked List**: Each node has references to both the next and previous nodes.

Methods for Doubly Linked List:
- `addFirst()`
- `addLast()`
- `removeFirst()`
- `removeLast()`
- `getFirst()`
- `getLast()`

Advantages over arrays:
- Dynamic size
- Ease of insertion and deletion

Disadvantages:
- Slower access time for random elements

### Binary Tree
- A type of tree where each node has at most two children.
- Properties: Root, Parent, Child, Sibling, Leaf, Internal Node, Degree, Level, Height, Depth, Path, Sub-tree.

Operations:
- `size(root)`: Returns the total number of nodes.
- `isEmpty(root)`: Checks if the tree is empty.
- `root()`: Returns the root node of the tree.
- `parent(node)`: Returns the parent of a node.
- `children(node)`: Returns a list of all children of a node.
- `isInternal(node)`: Checks if a node is internal.
- `isExternal(node)`: Checks if a node is a leaf.
- `isRoot(node)`: Checks if a node is the root.

### Binary Search Tree (BST)
- A type of binary tree where each node's left child is less than its value, and its right child is greater.

Methods:
- `insert(data)`: Inserts data into the tree.
- `search(data)`: Searches for data in the tree.
- `remove(data)`: Removes data from the tree.

Traversals:
- Breadth-First Search (BFS)
- Depth-First Search (DFS)
  - Pre-order (Node, Left, Right)
  - In-order (Left, Node, Right)
  - Post-order (Left, Right, Node)

### Hash Tables
- Key-value pairs organizing data for fast insertion, deletion, and lookup.
- Uses a hash function to compute the index of an entry.
- Collisions can occur when multiple keys hash to the same index.
- Techniques to handle collisions: Separate Chaining, Open Addressing.
- Time complexity: O(1) for average case (no collisions).

## Graphs
- Graphs are collections of nodes (vertices) and edges.
- Undirected Graph: Edges have no direction.
- Directed Graph (Digraph): Edges have a direction.
- Representations: Adjacency Matrix, Adjacency List.

### Binary Trees
- A type of tree where each node has at most two children.
- Terms: Root, Edge, Parent, Child, Sibling, Leaf, Internal Node, Degree, Level, Height, Depth, Path, Sub-tree.

### Tree ADT (Abstract Data Type)
- Methods: size, isEmpty, root, parent, children, isInternal, isExternal, isRoot.

### Binary Tree ADT
- Methods: left, right, hasLeft, hasRight, siblings.

## Merge Sort
- A divide-and-conquer sorting algorithm.
- Divides the input array into two halves, sorts them, and then merges them.
- Time complexity: O(n log n).

### Quick Sort
- A divide-and-conquer sorting algorithm.
- Chooses a pivot, partitions the array into two sub-arrays, and recursively sorts them.
- Time complexity: O(n log n) average, O(n^2) worst-case.

### Recursion
- A technique where a function calls itself to solve a smaller problem.
- Used in advanced sorting algorithms and tree navigations.
- Easier to read and write, but sometimes slower and uses more memory.

### Hash Tables
- Key-value pairs organizing data for fast insertion, deletion, and lookup.
- Utilizes a hash function to compute the index of an entry.
- Collisions occur when multiple keys hash to the same index.
- Techniques to handle collisions: Separate Chaining, Open Addressing.
- Time complexity: O(1) for average case (no collisions).

## Graphs
- Graphs are collections of nodes (vertices) and edges.
- Representations: Adjacency Matrix, Adjacency List.
- Graph types: Undirected, Directed.

### Binary Trees
- A type of tree where each node has at most two children.
- Terms: Root, Edge, Parent, Child, Sibling, Leaf, Internal Node, Degree, Level, Height, Depth, Path, Sub-tree.

### Tree ADT (Abstract Data Type)
- Methods: size, isEmpty, root, parent, children, isInternal, isExternal, isRoot.

### Binary Tree ADT
- Methods: left, right, hasLeft, hasRight, siblings.

## Merge Sort
- A divide-and-conquer sorting algorithm.
- Divides the input array into two halves, sorts them, and then merges them.
- Time complexity: O(n log n).

### Quick Sort
- A divide-and-conquer sorting algorithm.
- Chooses a pivot, partitions the array into two sub-arrays, and recursively sorts them.
- Time complexity: O(n log n) average, O(n^2) worst-case.

### Recursion
- A technique where a function calls itself to solve a smaller problem.
- Used in advanced sorting algorithms and tree navigations.
- Easier to read and write, but sometimes slower and uses more memory.

### Hash Tables
- Key-value pairs organizing data for fast insertion, deletion, and lookup.
- Utilizes a hash function to compute the index of an entry.
- Collisions occur when multiple keys hash to the same index.
- Techniques to handle collisions: Separate Chaining, Open Addressing.
- Time complexity: O(1) for average case (no collisions).

## Graphs
- Graphs are collections of nodes (vertices) and edges.
- Representations: Adjacency Matrix, Adjacency List.
- Graph types: Undirected, Directed.
