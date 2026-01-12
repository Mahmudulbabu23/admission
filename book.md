# BUET M.Sc. CSE & ICT Admission Guide

## Table of Contents
1. [Data Structures & Algorithms](#data-structures--algorithms)
2. [Programming & OOP](#programming--oop)
3. [Database Management Systems](#database-management-systems)
4. [Computer Networks](#computer-networks)
5. [Operating Systems](#operating-systems)
6. [Software Engineering](#software-engineering)
7. [Discrete Mathematics](#discrete-mathematics)
8. [Theory of Computation](#theory-of-computation)
9. [Digital Logic Design](#digital-logic-design)
10. [Practice Questions](#practice-questions)

---

## Data Structures & Algorithms

### Time Complexity Analysis
- **Big O Notation**: Upper bound of algorithm complexity
  - O(1) - Constant time
  - O(log n) - Logarithmic time
  - O(n) - Linear time
  - O(n log n) - Linearithmic time
  - O(n²) - Quadratic time
  - O(2ⁿ) - Exponential time

### Common Data Structures

#### 1. Arrays
- **Time Complexity**:
  - Access: O(1)
  - Search: O(n)
  - Insert: O(n)
  - Delete: O(n)

#### 2. Linked Lists
- **Types**: Singly, Doubly, Circular
- **Time Complexity**:
  - Access: O(n)
  - Search: O(n)
  - Insert: O(1) at head
  - Delete: O(1) with pointer

#### 3. Stacks
- **Operations**: Push, Pop, Peek
- **Applications**: Expression evaluation, backtracking, function calls
- **Time Complexity**: O(1) for all operations

#### 4. Queues
- **Types**: Simple Queue, Circular Queue, Priority Queue, Deque
- **Applications**: BFS, Scheduling, Resource sharing
- **Time Complexity**: O(1) for enqueue/dequeue

#### 5. Trees
- **Binary Tree**: Max 2 children per node
- **Binary Search Tree (BST)**: Left < Root < Right
- **AVL Tree**: Self-balancing BST
- **Red-Black Tree**: Self-balancing with color property
- **Heap**: Complete binary tree (Min-heap/Max-heap)

**Tree Traversals**:
- Inorder: Left → Root → Right
- Preorder: Root → Left → Right
- Postorder: Left → Right → Root
- Level Order: BFS approach

#### 6. Graphs
- **Representation**: Adjacency Matrix, Adjacency List
- **Types**: Directed, Undirected, Weighted, Unweighted

**Graph Algorithms**:
- **BFS**: O(V + E) - Shortest path in unweighted graph
- **DFS**: O(V + E) - Cycle detection, topological sort
- **Dijkstra's**: O((V + E) log V) - Shortest path with non-negative weights
- **Bellman-Ford**: O(VE) - Shortest path with negative weights
- **Floyd-Warshall**: O(V³) - All pairs shortest path
- **Prim's/Kruskal's**: O(E log V) - Minimum Spanning Tree

#### 7. Hash Tables
- **Collision Resolution**: Chaining, Open Addressing (Linear Probing, Quadratic Probing, Double Hashing)
- **Average Time Complexity**: O(1) for insert, delete, search
- **Load Factor**: α = n/m (n = elements, m = table size)

### Sorting Algorithms

| Algorithm | Best | Average | Worst | Space | Stable |
|-----------|------|---------|-------|-------|--------|
| Bubble Sort | O(n) | O(n²) | O(n²) | O(1) | Yes |
| Selection Sort | O(n²) | O(n²) | O(n²) | O(1) | No |
| Insertion Sort | O(n) | O(n²) | O(n²) | O(1) | Yes |
| Merge Sort | O(n log n) | O(n log n) | O(n log n) | O(n) | Yes |
| Quick Sort | O(n log n) | O(n log n) | O(n²) | O(log n) | No |
| Heap Sort | O(n log n) | O(n log n) | O(n log n) | O(1) | No |
| Counting Sort | O(n + k) | O(n + k) | O(n + k) | O(k) | Yes |
| Radix Sort | O(d(n + k)) | O(d(n + k)) | O(d(n + k)) | O(n + k) | Yes |

### Dynamic Programming
- **Principles**: Optimal substructure, Overlapping subproblems
- **Approaches**: Top-down (Memoization), Bottom-up (Tabulation)
- **Classic Problems**:
  - Fibonacci sequence
  - Knapsack problem (0/1, Unbounded)
  - Longest Common Subsequence (LCS)
  - Longest Increasing Subsequence (LIS)
  - Matrix Chain Multiplication
  - Edit Distance

### Greedy Algorithms
- **Principle**: Make locally optimal choice at each step
- **Examples**:
  - Activity Selection
  - Huffman Coding
  - Fractional Knapsack
  - Coin Change (for some coin systems)

---

## Programming & OOP

### Object-Oriented Programming Concepts

#### 1. Classes and Objects
- **Class**: Blueprint/template for objects
- **Object**: Instance of a class
- **Constructor**: Special method to initialize objects
- **Destructor**: Cleanup method when object is destroyed

#### 2. Four Pillars of OOP

**Encapsulation**:
- Bundling data and methods together
- Data hiding using access modifiers (public, private, protected)
- Getters and setters for controlled access

**Inheritance**:
- Code reusability through parent-child relationship
- Types: Single, Multiple, Multilevel, Hierarchical, Hybrid
- **Method Overriding**: Child redefines parent's method

**Polymorphism**:
- **Compile-time (Static)**: Method Overloading, Operator Overloading
- **Run-time (Dynamic)**: Method Overriding, Virtual Functions

**Abstraction**:
- Hiding implementation details
- Abstract classes and interfaces
- Show only essential features

#### 3. Advanced OOP Concepts
- **Virtual Functions**: Enable dynamic binding
- **Pure Virtual Functions**: Make class abstract
- **Friend Functions**: Access private members of a class
- **Static Members**: Shared across all instances
- **this Pointer**: Points to current object

### Programming Languages

#### C/C++
- **Pointers**: Store memory addresses
- **Memory Management**: malloc(), calloc(), free(), new, delete
- **Pass by Value vs Pass by Reference**
- **Structures vs Classes**: Default access (public vs private)
- **STL**: vector, map, set, queue, stack, priority_queue

#### Java
- **JVM, JRE, JDK**: Runtime environment hierarchy
- **Garbage Collection**: Automatic memory management
- **Exception Handling**: try-catch-finally, throw, throws
- **Collections Framework**: List, Set, Map interfaces
- **Multithreading**: Thread class, Runnable interface

#### Python
- **Data Types**: List, Tuple, Dictionary, Set
- **List Comprehension**: Concise list creation
- **Lambda Functions**: Anonymous functions
- **Decorators**: Modify function behavior
- **Generators**: Yield values lazily

---

## Database Management Systems

### Database Models
- **Hierarchical**: Tree structure
- **Network**: Graph structure
- **Relational**: Tables with relationships
- **Object-Oriented**: Objects with methods

### Relational Database Concepts

#### 1. Keys
- **Primary Key**: Unique identifier for records
- **Foreign Key**: Reference to primary key in another table
- **Candidate Key**: Minimal superkey
- **Super Key**: Set of attributes that uniquely identify tuples
- **Composite Key**: Primary key with multiple attributes

#### 2. Normalization
Purpose: Reduce redundancy and dependency

- **1NF**: Atomic values, no repeating groups
- **2NF**: 1NF + No partial dependency
- **3NF**: 2NF + No transitive dependency
- **BCNF**: 3NF + Every determinant is a candidate key
- **4NF**: BCNF + No multi-valued dependencies
- **5NF**: 4NF + No join dependencies

#### 3. SQL Queries

**DDL (Data Definition Language)**:
```sql
CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    age INT,
    department VARCHAR(50)
);

ALTER TABLE students ADD COLUMN email VARCHAR(100);
DROP TABLE students;
TRUNCATE TABLE students;
```

**DML (Data Manipulation Language)**:
```sql
INSERT INTO students VALUES (1, 'John', 22, 'CSE');
UPDATE students SET age = 23 WHERE id = 1;
DELETE FROM students WHERE id = 1;
SELECT * FROM students WHERE age > 20;
```

**Joins**:
- **INNER JOIN**: Matching records from both tables
- **LEFT JOIN**: All from left + matching from right
- **RIGHT JOIN**: All from right + matching from left
- **FULL OUTER JOIN**: All records from both tables
- **CROSS JOIN**: Cartesian product

**Aggregate Functions**: COUNT(), SUM(), AVG(), MIN(), MAX()

**GROUP BY & HAVING**:
```sql
SELECT department, COUNT(*)
FROM students
GROUP BY department
HAVING COUNT(*) > 5;
```

#### 4. Transactions (ACID Properties)
- **Atomicity**: All or nothing
- **Consistency**: Database remains in valid state
- **Isolation**: Concurrent transactions don't interfere
- **Durability**: Committed changes persist

#### 5. Indexing
- **Purpose**: Speed up query retrieval
- **Types**: Primary, Secondary, Clustered, Non-clustered
- **B-Tree**: Most common indexing structure
- **B+ Tree**: All data in leaf nodes

#### 6. Concurrency Control
- **Lock-based**: Shared lock, Exclusive lock
- **Two-Phase Locking (2PL)**: Growing phase, Shrinking phase
- **Timestamp-based**: Order transactions by timestamps
- **Deadlock**: Circular wait condition

---

## Computer Networks

### OSI Model (7 Layers)

1. **Physical Layer**: Bits transmission, cables, hubs
2. **Data Link Layer**: Frames, MAC addresses, switches, error detection
3. **Network Layer**: Routing, IP addresses, routers
4. **Transport Layer**: TCP/UDP, end-to-end communication
5. **Session Layer**: Session management
6. **Presentation Layer**: Data formatting, encryption
7. **Application Layer**: HTTP, FTP, SMTP, DNS

### TCP/IP Model (4 Layers)
1. **Network Interface**: OSI Physical + Data Link
2. **Internet**: IP, ICMP, ARP
3. **Transport**: TCP, UDP
4. **Application**: HTTP, FTP, SMTP

### Important Protocols

#### IP Addressing
- **IPv4**: 32-bit (4 octets) - e.g., 192.168.1.1
- **IPv6**: 128-bit - e.g., 2001:0db8:85a3::8a2e:0370:7334
- **Classes**: A (1-126), B (128-191), C (192-223), D (Multicast), E (Reserved)
- **Subnetting**: Dividing network into smaller subnetworks
- **CIDR Notation**: 192.168.1.0/24

#### TCP vs UDP

| Feature | TCP | UDP |
|---------|-----|-----|
| Connection | Connection-oriented | Connectionless |
| Reliability | Reliable | Unreliable |
| Order | Ordered delivery | No ordering |
| Speed | Slower | Faster |
| Use Cases | HTTP, FTP, Email | Streaming, Gaming, DNS |

#### HTTP Methods
- **GET**: Retrieve data
- **POST**: Submit data
- **PUT**: Update resource
- **DELETE**: Remove resource
- **PATCH**: Partial update

#### DNS (Domain Name System)
- Translates domain names to IP addresses
- **Hierarchy**: Root → TLD → Authoritative
- **Record Types**: A, AAAA, CNAME, MX, NS, TXT

### Network Devices
- **Hub**: Broadcasts to all ports (Layer 1)
- **Switch**: Forwards to specific port using MAC (Layer 2)
- **Router**: Routes between networks using IP (Layer 3)
- **Gateway**: Protocol converter
- **Firewall**: Security barrier

### Network Security
- **Encryption**: Symmetric (AES), Asymmetric (RSA)
- **SSL/TLS**: Secure communication protocol
- **VPN**: Virtual Private Network
- **Firewall Types**: Packet filtering, Stateful, Application-level

---

## Operating Systems

### Process Management

#### Process States
1. **New**: Being created
2. **Ready**: Waiting for CPU
3. **Running**: Executing
4. **Waiting**: Waiting for I/O
5. **Terminated**: Finished execution

#### Process Scheduling Algorithms

| Algorithm | Description | Pros | Cons |
|-----------|-------------|------|------|
| FCFS | First Come First Served | Simple | Convoy effect |
| SJF | Shortest Job First | Minimum avg waiting time | Starvation possible |
| Priority | Based on priority | Flexible | Starvation |
| Round Robin | Time quantum | Fair, no starvation | Context switching overhead |
| Multilevel Queue | Multiple queues | Flexible | Complex |

#### Context Switching
- Saving state of current process
- Loading state of next process
- Overhead but necessary for multitasking

### Memory Management

#### Memory Allocation
- **Contiguous**: Single, Partitioned (Fixed, Dynamic)
- **Fragmentation**:
  - External: Free memory scattered
  - Internal: Allocated memory unused

#### Paging
- Divide memory into fixed-size pages
- Page Table maps logical to physical addresses
- **Page Fault**: Requested page not in memory

#### Segmentation
- Divide memory into logical segments
- Segment Table tracks segment locations

#### Virtual Memory
- Allows execution of processes larger than physical memory
- **Demand Paging**: Load pages only when needed
- **Page Replacement Algorithms**:
  - FIFO (First In First Out)
  - LRU (Least Recently Used)
  - Optimal (Replace page not used for longest time)

### Deadlock

#### Necessary Conditions
1. **Mutual Exclusion**: Resource cannot be shared
2. **Hold and Wait**: Process holds resource while waiting
3. **No Preemption**: Resource cannot be forcibly taken
4. **Circular Wait**: Circular chain of waiting processes

#### Handling Deadlock
- **Prevention**: Eliminate one necessary condition
- **Avoidance**: Banker's Algorithm
- **Detection and Recovery**: Detect cycle, kill processes
- **Ignore**: Ostrich approach

### File Systems
- **File**: Named collection of related information
- **Directory**: Contains files and subdirectories
- **File Allocation Methods**:
  - Contiguous: Sequential blocks
  - Linked: Pointers to next block
  - Indexed: Index block with pointers

### Synchronization

#### Critical Section Problem
- **Mutual Exclusion**: Only one process in critical section
- **Progress**: Selection of next process cannot be postponed
- **Bounded Waiting**: Limit on waiting time

#### Solutions
- **Semaphore**: Integer variable for signaling
  - Binary (Mutex): 0 or 1
  - Counting: Any non-negative value
- **Monitor**: High-level synchronization construct
- **Mutex Lock**: Binary lock for mutual exclusion

---

## Software Engineering

### Software Development Life Cycle (SDLC)

#### 1. Waterfall Model
- Sequential phases
- **Phases**: Requirements → Design → Implementation → Testing → Maintenance
- **Pros**: Simple, structured
- **Cons**: Inflexible, late testing

#### 2. Agile Model
- Iterative and incremental
- **Principles**: Customer collaboration, responding to change
- **Frameworks**: Scrum, Kanban
- **Pros**: Flexible, early delivery
- **Cons**: Requires experienced team

#### 3. Spiral Model
- Risk-driven approach
- Combines iterative and waterfall
- **Phases**: Planning → Risk Analysis → Engineering → Evaluation

#### 4. V-Model
- Verification and Validation model
- Testing phase for each development phase

### Software Testing

#### Testing Levels
1. **Unit Testing**: Individual components
2. **Integration Testing**: Combined components
3. **System Testing**: Complete system
4. **Acceptance Testing**: User requirements

#### Testing Types
- **Functional**: Black box, testing features
- **Non-functional**: Performance, security, usability
- **Regression**: After changes, ensure existing features work
- **Smoke Testing**: Basic functionality check

#### White Box vs Black Box
- **White Box**: Test internal logic, know code
- **Black Box**: Test functionality, ignore implementation

### Design Patterns

#### Creational Patterns
- **Singleton**: Single instance
- **Factory**: Create objects without specifying exact class
- **Builder**: Construct complex objects step by step

#### Structural Patterns
- **Adapter**: Interface compatibility
- **Decorator**: Add functionality dynamically
- **Facade**: Simplified interface

#### Behavioral Patterns
- **Observer**: Notify dependents of changes
- **Strategy**: Encapsulate algorithms
- **Command**: Encapsulate requests

### UML Diagrams
- **Class Diagram**: Classes and relationships
- **Use Case Diagram**: System functionality
- **Sequence Diagram**: Object interactions over time
- **Activity Diagram**: Workflow
- **State Diagram**: Object states

---

## Discrete Mathematics

### Set Theory
- **Operations**: Union (∪), Intersection (∩), Difference (−), Complement (')
- **Laws**: De Morgan's, Associative, Commutative, Distributive
- **Cartesian Product**: A × B = {(a,b) | a ∈ A, b ∈ B}
- **Power Set**: 2^n subsets for n elements

### Relations
- **Properties**:
  - Reflexive: (a,a) for all a
  - Symmetric: (a,b) → (b,a)
  - Transitive: (a,b) ∧ (b,c) → (a,c)
  - Antisymmetric: (a,b) ∧ (b,a) → a=b
- **Equivalence Relation**: Reflexive + Symmetric + Transitive
- **Partial Order**: Reflexive + Antisymmetric + Transitive

### Functions
- **Injective (One-to-One)**: Different inputs → Different outputs
- **Surjective (Onto)**: Every output has input
- **Bijective**: Both injective and surjective

### Graph Theory
- **Euler Path**: Visit every edge exactly once
- **Euler Circuit**: Euler path returning to start
- **Hamiltonian Path**: Visit every vertex exactly once
- **Hamiltonian Circuit**: Hamiltonian path returning to start

**Conditions**:
- Euler Circuit: All vertices have even degree
- Euler Path: Exactly 2 vertices have odd degree

### Combinatorics
- **Permutation**: P(n,r) = n!/(n-r)!
- **Combination**: C(n,r) = n!/(r!(n-r)!)
- **Binomial Theorem**: (a+b)ⁿ = Σ C(n,k) aⁿ⁻ᵏ bᵏ
- **Pigeonhole Principle**: n+1 pigeons, n holes → at least 1 hole has 2+ pigeons

### Logic
- **Propositional Logic**: AND (∧), OR (∨), NOT (¬), IMPLIES (→), IFF (↔)
- **Truth Tables**: Evaluate logical expressions
- **Tautology**: Always true
- **Contradiction**: Always false
- **Logical Equivalence**: p ≡ q

### Number Theory
- **GCD**: Greatest Common Divisor - Euclidean Algorithm
- **LCM**: Least Common Multiple - LCM(a,b) = (a×b)/GCD(a,b)
- **Prime Numbers**: Divisible only by 1 and itself
- **Modular Arithmetic**: (a mod n)

---

## Theory of Computation

### Automata Theory

#### Finite Automata (FA)
- **DFA (Deterministic)**: One transition per input symbol
- **NFA (Non-deterministic)**: Multiple transitions possible, ε-transitions
- **Conversion**: NFA → DFA (Subset Construction)
- **Minimization**: Reduce states in DFA

#### Regular Languages
- **Regular Expression**: Pattern matching notation
- **Operations**: Union, Concatenation, Kleene Star
- **Pumping Lemma**: Test if language is regular

#### Context-Free Grammar (CFG)
- **Production Rules**: S → aSb | ε
- **Derivation**: Leftmost, Rightmost
- **Parse Tree**: Graphical representation
- **Ambiguity**: Multiple parse trees for same string

#### Pushdown Automata (PDA)
- FA + Stack
- Recognizes context-free languages
- **Deterministic PDA**: Subset of context-free languages

#### Turing Machine
- Infinite tape, read/write head
- **Types**: Deterministic, Non-deterministic, Multi-tape
- Most powerful computational model

### Complexity Classes
- **P**: Problems solvable in polynomial time
- **NP**: Problems verifiable in polynomial time
- **NP-Complete**: Hardest problems in NP
- **NP-Hard**: At least as hard as NP-Complete
- **P vs NP**: Unsolved problem

### Decidability
- **Decidable**: Algorithm exists to solve
- **Undecidable**: No algorithm can solve
- **Halting Problem**: Undecidable

---

## Digital Logic Design

### Number Systems
- **Binary**: Base 2 (0, 1)
- **Octal**: Base 8 (0-7)
- **Decimal**: Base 10 (0-9)
- **Hexadecimal**: Base 16 (0-9, A-F)

**Conversions**: Between bases using division/multiplication

### Boolean Algebra
- **Operations**: AND (·), OR (+), NOT (')
- **Laws**:
  - Identity: A + 0 = A, A · 1 = A
  - Null: A + 1 = 1, A · 0 = 0
  - Idempotent: A + A = A, A · A = A
  - Complement: A + A' = 1, A · A' = 0
  - De Morgan's: (A + B)' = A' · B', (A · B)' = A' + B'

### Logic Gates
- **Basic**: AND, OR, NOT
- **Universal**: NAND, NOR
- **Special**: XOR, XNOR

### Combinational Circuits
- **Adder**: Half Adder, Full Adder
- **Subtractor**: Half Subtractor, Full Subtractor
- **Multiplexer (MUX)**: 2ⁿ inputs → 1 output
- **Demultiplexer (DEMUX)**: 1 input → 2ⁿ outputs
- **Encoder**: 2ⁿ inputs → n outputs
- **Decoder**: n inputs → 2ⁿ outputs

### Sequential Circuits
- **Flip-Flops**: SR, D, JK, T
- **Registers**: Store data (Shift Register, Universal Register)
- **Counters**: Count events (Synchronous, Asynchronous)

### K-Map (Karnaugh Map)
- Simplify Boolean expressions
- Group 1s in powers of 2 (1, 2, 4, 8)
- **Prime Implicant**: Maximum group
- **Essential Prime Implicant**: Must be included

---

## Practice Questions

### Data Structures

**Q1:** What is the time complexity of searching in a balanced BST?
**A:** O(log n)

**Q2:** Which traversal of BST gives sorted order?
**A:** Inorder traversal

**Q3:** What is the worst-case time complexity of Quick Sort?
**A:** O(n²) when pivot selection is poor

**Q4:** Which data structure is used for BFS?
**A:** Queue

**Q5:** What is the space complexity of Merge Sort?
**A:** O(n)

### DBMS

**Q1:** What is the main purpose of normalization?
**A:** Reduce redundancy and dependency

**Q2:** Difference between DELETE and TRUNCATE?
**A:** DELETE is DML (can be rolled back), TRUNCATE is DDL (cannot be rolled back)

**Q3:** What is a transaction?
**A:** Logical unit of work that must be completed entirely or not at all

**Q4:** Which normal form eliminates transitive dependency?
**A:** 3NF (Third Normal Form)

**Q5:** What is indexing?
**A:** Data structure technique to speed up data retrieval operations

### Networks

**Q1:** Which layer of OSI model provides end-to-end communication?
**A:** Transport Layer

**Q2:** Default subnet mask for Class C?
**A:** 255.255.255.0

**Q3:** Which protocol is connectionless?
**A:** UDP

**Q4:** Port number for HTTP?
**A:** 80

**Q5:** What does DNS do?
**A:** Translates domain names to IP addresses

### Operating Systems

**Q1:** What is context switching?
**A:** Saving and loading process states when switching between processes

**Q2:** Which page replacement algorithm is optimal?
**A:** Replace page that won't be used for longest time (theoretical)

**Q3:** What is thrashing?
**A:** Excessive paging causing system slowdown

**Q4:** Necessary conditions for deadlock?
**A:** Mutual Exclusion, Hold and Wait, No Preemption, Circular Wait

**Q5:** Difference between process and thread?
**A:** Process has separate memory space, threads share memory within process

### OOP

**Q1:** What is polymorphism?
**A:** Ability to take multiple forms (compile-time and run-time)

**Q2:** Difference between abstract class and interface?
**A:** Abstract class can have implementation, interface only declarations (Java 7)

**Q3:** What is encapsulation?
**A:** Bundling data and methods together, hiding internal details

**Q4:** Can constructor be virtual?
**A:** No, constructors cannot be virtual

**Q5:** What is multiple inheritance?
**A:** Class inheriting from multiple parent classes

---

## Study Tips

### Preparation Strategy
1. **Understand Concepts**: Don't just memorize, understand the logic
2. **Practice Coding**: Implement algorithms and data structures
3. **Solve Previous Papers**: Identify patterns in questions
4. **Time Management**: Allocate time to each topic based on weightage
5. **Revision**: Regular revision of important formulas and concepts
6. **Mock Tests**: Take practice tests under timed conditions

### Important Topics by Weightage
**High Priority:**
- Data Structures & Algorithms (30-35%)
- Programming & OOP (20-25%)
- DBMS (15-20%)

**Medium Priority:**
- Computer Networks (10-15%)
- Operating Systems (10-15%)

**Standard Coverage:**
- Software Engineering (5-10%)
- Discrete Mathematics (5-10%)
- Theory of Computation (5%)
- Digital Logic (5%)

### Common Mistakes to Avoid
1. Neglecting basic concepts
2. Not practicing coding problems
3. Ignoring previous year questions
4. Poor time management during exam
5. Not revising regularly

### Resources
- **Books**: Cormen (Algorithms), Tanenbaum (OS, Networks), Navathe (DBMS)
- **Online Platforms**: LeetCode, HackerRank, GeeksforGeeks
- **Practice**: Solve at least 200+ coding problems
- **YouTube**: CS50, MIT OCW, Abdul Bari

---

## Quick Reference Formulas

### Time Complexity
- **Logarithmic growth**: log₂(1024) = 10
- **Factorial**: 10! = 3,628,800
- **Powers of 2**: 2¹⁰ = 1024, 2²⁰ = 1,048,576

### Network Calculations
- **Subnetting**: Hosts = 2ⁿ - 2 (n = host bits)
- **IPv4 addresses in /24**: 256 addresses (254 usable)

### Probability
- **P(A ∪ B)**: P(A) + P(B) - P(A ∩ B)
- **Conditional**: P(A|B) = P(A ∩ B) / P(B)

### Combinatorics
- **Permutation**: P(n,r) = n!/(n-r)!
- **Combination**: C(n,r) = n!/(r!(n-r)!)

---

**Best of luck with your BUET M.Sc. CSE & ICT admission preparation! 🎯**

*Note: This guide covers fundamental topics. Supplement with practice problems and detailed study of each area.*

---

## Exam Snapshot & Plan

- **Typical format (confirm with latest notice)**: 100 marks, 90–120 minutes, mostly MCQ + a few short answers; negative marking often 0.25 per wrong MCQ.
- **Subject weight (typical)**: DSA 25–30, Programming/OOP 15–20, DBMS 10–15, OS 10–15, Networks 10–15, Discrete Math/Logic 10–15, Others 5–10.
- **Tools allowed**: Usually none beyond pen/pencil; assume no calculator—practice mental math for log, exponent, probability.

### 30-Day Intensive Plan (adjust per need)
1. **Days 1–5**: DSA core (sorting, searching, trees, graphs); daily 15 MCQs + 2 coding problems.
2. **Days 6–8**: DP/Greedy patterns; solve 10 DP + 10 greedy problems.
3. **Days 9–11**: OOP + Language specifics (C/C++/Java/Python idioms, memory, exceptions).
4. **Days 12–14**: DBMS (SQL joins, indexing, normalization, transactions) with 30 SQL drills/day.
5. **Days 15–17**: OS (process/thread, scheduling calculations, paging, deadlock, synchronization).
6. **Days 18–20**: Networks (subnetting, TCP/UDP, HTTP, DNS, routing basics); 20 subnet drills/day.
7. **Days 21–22**: Discrete Math/Logic/TOC (grammar, automata, pumping lemma quick checks, combinatorics).
8. **Days 23–24**: Digital Logic (K-map simplification drills, number system conversions).
9. **Days 25–27**: Mixed mock tests (2 per day, timed); review errors same day.
10. **Days 28–30**: Revision decks—formulas, tricky MCQs, previously wrong questions.

### Rapid Revision Sheets (print/flashcards)
- **DSA**: Traversal orders, heap rules, graph algorithm complexities.
- **OS**: Deadlock conditions, page replacement traits, scheduling formulas.
- **DB**: Normal forms, join semantics, transaction isolation levels.
- **Networks**: Port numbers, OSI/TCP-IP mapping, CIDR to hosts, TCP vs UDP traits.
- **Math/Logic**: Combinatorics formulas, probability identities, DFA/NFA closure properties.

---

## Deeper Topic Notes

### Data Structures & Algorithms (Expanded)
- **Recurrence Cheats**: T(n)=2T(n/2)+n → O(n log n); T(n)=T(n/2)+1 → O(log n); T(n)=T(n-1)+n → O(n²).
- **BST Validity (range method)**: Recursively enforce (min,max) bounds; fails if any node violates bound.
- **Graph Cycle Checks**: Undirected—DFS parent tracking or DSU; Directed—DFS color/recursion stack.
- **Topological Sort**: Only for DAG; Kahn’s BFS (in-degree) or DFS post-order reversed.
- **Shortest Paths**: Dijkstra fails on negative edges; use Bellman-Ford (detects negative cycle if extra |V|-th relaxation succeeds).
- **MST**: Kruskal (sort edges + DSU) vs Prim (PQ). Cut property: lightest edge crossing any cut is in some MST.
- **Heaps**: Build-heap O(n); heapify O(log n); k-largest via min-heap of size k O(n log k).
- **String Algorithms**: KMP prefix function π[i]; LPS array for pattern; Rabin-Karp rolling hash to cut average time.

### Programming & OOP (Expanded)
- **C/C++ gotchas**: Dangling pointer after free/delete; shallow vs deep copy; rule of 3/5 (copy ctor, copy assign, dtor, move ctor, move assign).
- **Java**: Checked vs unchecked exceptions; `equals()`/`hashCode()` contract; `String` immutability; `ArrayList` vs `LinkedList` complexity.
- **Python**: Mutable default arg pitfall; list vs tuple vs set performance; `__slots__` to reduce memory; generator expressions for streaming.
- **Design Principles**: SOLID quick refs—SRP (one reason to change), OCP (open for extension, closed for modification), LSP (substitutability), ISP (specific interfaces), DIP (depend on abstractions).

### DBMS (Expanded)
- **Normalization workflow**: 1NF (atomic) → 2NF (no partial on candidate keys) → 3NF (no transitive) → BCNF (every determinant is key). Stop at 3NF if BCNF causes loss of dependency and non-key FDs are rare.
- **Isolation Levels (ANSI)**: Read Uncommitted (dirty reads), Read Committed (no dirty), Repeatable Read (no non-repeatable), Serializable (no phantom). MySQL InnoDB: RR default with gap locks to reduce phantoms.
- **Index selection**: Use on high-selectivity columns; avoid on low-selectivity booleans; composite index (A,B) helps queries filtering A then B; beware write overhead.
- **Query tuning checklist**: Covering index, avoid SELECT *, filter early, use EXPLAIN, ensure proper JOIN order and predicates on indexed columns.
- **ER to Relational**: Strong entity → table; weak entity → table with PK = {owner FK + partial key}; 1:N place FK on N; M:N resolve with associative table.

### Computer Networks (Expanded)
- **Subnet Drill**: For /27 → 32 addresses, 30 usable, block size 32; examples: 10.0.0.0/27, 10.0.0.32/27, ...; broadcast = last IP in block.
- **CIDR Aggregation**: Combine consecutive blocks if aligned; e.g., two /25 contiguous → /24.
- **TCP details**: 3-way handshake (SYN, SYN-ACK, ACK); congestion control (slow start, congestion avoidance, fast retransmit/recovery); flow control via window size.
- **DNS resolution path**: Stub resolver → recursive resolver → root → TLD → authoritative; caching at each hop.
- **HTTPS**: TLS handshake establishes symmetric keys; certificates bind domain to public key; HSTS forces HTTPS.

### Operating Systems (Expanded)
- **Scheduling calculations**:
  - Waiting Time = Turnaround - Burst.
  - Turnaround = Completion - Arrival.
  - In RR, count multiple waits between quanta.
- **Effective Access Time (paging + TLB)**: EAT = h×(t_mem + t_hit) + (1-h)×(t_mem + t_miss); with page fault, add page fault service cost (very high).
- **Deadlock avoidance (Banker’s)**: Safe sequence exists if, after allocation, remaining need ≤ available for some process sequence.
- **Readers-Writers patterns**: Writer preference vs reader preference; starvation trade-offs.
- **Synchronization bugs**: Missed wakeups, priority inversion (mitigate by priority inheritance), holding locks during blocking I/O.

### Discrete Math & TOC (Expanded)
- **Inclusion-Exclusion (2 sets)**: |A∪B| = |A|+|B|−|A∩B|; (3 sets) add +|A∩B∩C| after alternating signs.
- **Recurrence (linear homogeneous)**: a_n = c1 a_{n-1} + c2 a_{n-2}; solve via characteristic r²−c1 r−c2=0.
- **Pumping Lemma (regular)**: For long enough string s=xyz, |xy|≤p, |y|>0, ∀i≥0, xy^i z in language. Use to derive contradiction (choose i=0 or 2).
- **CFG to PDA idea**: Push start symbol, replace with RHS, match input; stack enables nested structure.

### Digital Logic (Expanded)
- **Boolean simplification quickies**: Absorption A + A'B = A + B; Consensus AB + A'C + BC = AB + A'C.
- **Adder timings**: Ripple-carry delay grows with n; carry-lookahead uses generate/propagate to cut delay.
- **Number system practice**: Convert 0.375₁₀ → 0.011₂ (multiply fractional part by 2 repeatedly).
- **K-map grouping rules**: Only powers of 2; wrap-around allowed; prefer largest groups; essential prime implicants must be selected.

---

## Worked Examples

### Subnetting Example
Given 192.168.10.0/26:
- Block size = 64; subnets: 192.168.10.0/26, 192.168.10.64/26, 192.168.10.128/26, 192.168.10.192/26.
- For 192.168.10.130: subnet network = 192.168.10.128, broadcast = 192.168.10.191, first host = 192.168.10.129, last host = 192.168.10.190.

### Scheduling Example (SJF, non-preemptive)
Processes: P1 (arr 0, burst 7), P2 (arr 2, burst 4), P3 (arr 4, burst 1), P4 (arr 5, burst 4)
- Order: P1 (0–7), P3 (7–8), P2 (8–12), P4 (12–16)
- Turnaround: P1=7, P2=10, P3=4, P4=11
- Waiting: P1=0, P2=6, P3=3, P4=7
- Avg Waiting = (0+6+3+7)/4 = 4; Avg TAT = (7+10+4+11)/4 = 8

### Normalization Check
Relation R(StudentID, CourseID, Instructor, InstructorPhone)
- FDs: StudentID,CourseID → Instructor, InstructorPhone; Instructor → InstructorPhone
- Partial/Transitive? Composite key {StudentID,CourseID}. Instructor depends only on key (good), InstructorPhone depends on Instructor (transitive). To reach 3NF: split R1(StudentID,CourseID,Instructor) and R2(Instructor,InstructorPhone).

### DP Example (LCS length)
Strings X=“ABCBDAB”, Y=“BDCAB”
- dp[i][j] = 0 if i=0 or j=0; if X[i-1]==Y[j-1], dp[i][j]=1+dp[i-1][j-1]; else max(dp[i-1][j], dp[i][j-1]).
- Final LCS length = 4 (e.g., “BCAB” or “BDAB”).

### Graph Cycle (Directed)
- Use DFS with recursion stack. If visiting node v finds neighbor already in recursion stack, cycle exists.

---

## Practice Set (Fresh)

1. **DSA**: For array of n numbers, which algorithm gives O(n) expected time to find k-th smallest? **Ans**: Randomized Quickselect.
2. **DSA**: In a min-heap, what are possible positions of second smallest key? **Ans**: One of the children of root.
3. **Programming**: In C++, what happens if copy ctor is not defined but class manages raw heap pointer? **Ans**: Default shallow copy → double free/UB; define rule of 3/5.
4. **OOP**: Which SOLID principle is about small, cohesive interfaces? **Ans**: Interface Segregation Principle.
5. **DBMS**: Which isolation level prevents dirty reads but allows non-repeatable reads? **Ans**: Read Committed.
6. **DBMS**: Why can an index slow down writes? **Ans**: Each insert/update/delete must maintain index pages.
7. **Networks**: What is MSS in TCP? **Ans**: Maximum Segment Size—largest data chunk in a segment (excludes TCP/IP headers).
8. **Networks**: Which record maps domain to mail server? **Ans**: MX record.
9. **OS**: In paging, what is internal fragmentation size bound? **Ans**: At most one page minus 1 byte per process.
10. **OS**: Name two conditions removed to prevent deadlock. **Ans**: Break hold-and-wait (allocate all at once) or allow preemption/circular-wait ordering.
11. **Discrete Math**: Number of onto functions from set of size 4 to set of size 3? **Ans**: 3!·S(4,3)=6·6=36 (Stirling S(4,3)=6).
12. **TOC**: Is union of two regular languages regular? **Ans**: Yes (closure under union); construct product automaton.
13. **Digital Logic**: Minimal SOP of F(A,B)=Σm(1,2,3)? **Ans**: A'B + AB' (via K-map).
14. **Probability**: Two independent events A,B with P(A)=0.3, P(B)=0.5. P(A∪B)? **Ans**: 0.3+0.5−0.15=0.65.
15. **Math**: Ways to arrange word “BANANA”? **Ans**: 6!/(3!2!)=60.

---

## Mock Test Blueprint (Self-check)
- **Sections**: 60 MCQ (1 mark each), 10 short (2 marks each), 2 coding/analytical (5 marks each). Time: 100 minutes.
- **Passing target**: Aim 70+; with negative marking 0.25, accuracy threshold ≥80%.
- **Attempt order**: (1) High-confidence MCQ pass; (2) Short answers; (3) Revisit unsure MCQ; (4) Coding/analytical last if time is enough.
- **Error log**: After each mock, tag mistakes: concept, formula, reading, speed. Fix top 3 recurring errors next day.

---

## Final Week Checklist
- 3 full-length mocks (alternate days) + same-day review.
- Re-solve all previously wrong questions until 100% correct twice.
- Refresh: subnet sizes, page replacement traits, join types, normalization rules, DFA/NFA properties, K-map groups.
- Sleep, hydrate, and carry required documents early.
