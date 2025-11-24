# Java Concurrency
## Index:
 1. Synchronizers
 2. Executors
 3. Concurrent Collections
 4. The Fork/Join Framework

## Basics
What is Concurrency?
 - Concurrency means dealing with multiple tasks/things at a same time.

>[!Note]
>Multithreading is the mechanism or tool used by Java to achieve concurrency in Java applications

>[!warning]
>Concurrency ≠ Parallelism <br> Concurrency ≠ Multithreading

## Synchronizers
Problem without Synchronization:
In a multi-threaded environment, when multiple threads wants to access and modify the same data simultaneously, the final state of the data becomes unpredictable, leading to a condition called, Race Condition. 
 Example:  (Bank Account)
  1. A persons Bank Account balance is R1000
  2. Thread-A(deposits-R100): Reads the Balance R1000
  3. Thread-B(withdraw-R200): Reads the balance R1000
  4. Thread-B calculates and writes the new balance(R1000-R200=R800)
  5. Thread-A calculated and writes the new balance(R1000+R100=R1100)
  6. Final Balance: R1100, the R800 withdrawl was lost! The correct balance should have been R900.

Synchronization solves this by forcing Thread-A and Thread-B to access the balance sequentially(one after another).

What is Synchronization ?
>Synchronization is a process of controlling access to shared resource by multiple threads. It ensures that only one thread can execute a specific piece of code or access a particular shared variable at a time.

How to implement Synchronization ?
1. Using ```synchronized``` keyword
    a. Synchronized Methods
    b. Synchronized Blocks
2. The ```volatile``` Keyword
3. Concurrency Utilities (```java.util.concurrent.locks```)

### When to use and When to avoide synchronization?

<img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/c4a80b6b-3e50-449a-9d8b-fac680f6e892" />


  

## Executor Framework
>It manages the thread execution.

### Executor Framework Heirarchy
<img width="710" height="400" alt="image" src="https://github.com/user-attachments/assets/707a056c-46ea-4bc2-8e50-35487ec1b342" />



