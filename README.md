# Algorithms-and-Datatructures
Welcome to my repository where I solve and document exercises from the subject Algorithms & Data Structures. This repository will serve as a progressive record of my work, including code, explanations, and analyses for each exercise.

## Table of contents
- [Introduction](#introduction)
- [Exersizes](#exersizes)
    - [C++ Basics, Complexity, and ADT](#c-basics-complexity-and-adt)
        - [Exersize 1](#exersize-1)
        - [Exersize 2](#exersize-2)
        - [Exersize 3](#exersize-3)
        - [Exersize 4](#exersize-4)
        - [Exersize 5](#exersize-5)
    - [Elementary data structures and their processing](#elementary-data-structures-and-their-processing)
- [How to use this repository](#how-to-use-this-repository)

## Introduction
This repository contains solutions and documentation for exercises from the "Algorithms & Data Structures" course, part of the Software Technology program at Aarhus University. The course, taken in the third semester of the program, covers a range of fundamental topics including programming, complexity analysis, and the implementation of various data structures and algorithms.

In this repository, you'll find my approach to solving different exercises, along with explanations and analyses for each one. The exercises are designed to deepen the understanding of key concepts in algorithms and data structures through practical coding and problem-solving.

The repository is structured to reflect the progression of the course, with updates as new exercises are completed.

## Exersizes
## C++ Basics, Complexity, and ADT
### Exersize 1
Write a program that:

    1. Generates M random integers and stores them in vector.

    2. Generates another N random integers and counts how many of them are already present in the vector, using an iterator.

Estimate the worst-case complexity of the program.

### Exersize 2
What is the time complexity (Big-O) of myMethod?
```cpp
int myMethod(int N)
{
    int x = 0;
    int y = 0;
    for(int i = 0; i <N; i++)
        for(int j = 0; j < N; j++)
            for(int k = 0; k < N * sqrt(N); k++)
                x++;

    for(int i = 0; i < N * N; i++)
        y++;

    return x + y;
}
```

### Exersize 3
For each of the following four program fragments:

    - Give an analysis of the running time in Big-O notation.

    - Implement the code inside a C function, and give the running time for several values of N.

    - Compare your analysis with the actual running times.

    - Does compiling/running programs with the -O optimization flag change anything in your analysis?

1. program fragment:
```cpp
sum = 0;
for (i = 0; i < n; i++)
    sum++;
```   
2. program fragment:
```cpp
sum = 0;
for (i = 0; i < n; i++)
    for (j = 0; j < n; j++)
        sum++;
```  
3. program fragment:
```cpp
sum = 0;
for (i = 0; i < n; i++)
    for (j = 0; j < n * n; j++)
        sum++;
```
4. program fragment:
```cpp
sum = 0;
for (i = 0; i < n; i++)
    for (j = 0; j < i; j++)
        sum++;
```
### Exersize 4
Write an implementation of the ADT MaxHeap described below. The implementation must be done by using the standard class `vector` from C++. If you need to iterate through the vector, you must use an iterator and its methods and operators `begin()`, `end()`, `++`, and `*`.
```cpp
class MaxHeap
{
    public:
    //is the heap empty?
    virtual bool isEmpty() const = 0;

    //number of elements in the heap
    virtual int size() = 0;

    //number of elements in the heap
    virtual void insert(const int x) = 0;

    //find the maximum element in the heap
    virtual const int findMax() const = 0;

    // delete and return the maximum element of the heap
    virtual int deleteMax() = 0;
};
```
What is the time complexity of the five operations of MaxHeap?  You must argue for your answers

Make a new implementation of the MaxHeap using a `List`. Make sure to use the List interface where possible.

### Exersize 5
Create and implement a C++ class called `Library` that manages books. Each book (which should also be a class) has an identifier (an integer provided when creating the book) and a category (an integer between 0 and 15 inclusive, provided when constructing the book). The `Library` class should allow the following functionalities:

- **Adding new books** to the library.
- **Borrowing books** from the library.
- **Returning borrowed books**.
- **Displaying all available books** and **borrowed books**.
- A function that returns the number of books in a given category.
- When adding a new book, issue a warning (to `std::cout`) if the number of books in any category exceeds twice the average number of books per category, to ensure the user maintains a balanced library.

A main function should test all features of the library. Below is the provided starting point for the code that you can modify to implement this:

```cpp
int main() {
    Library myLibrary;

    // Adding books to the library
    myLibrary.addBook(1, 3); // Book ID: 1, Category: 3
    myLibrary.addBook(2, 7); // Book ID: 2, Category: 7
    myLibrary.addBook(3, 3); // Book ID: 3, Category: 3
    myLibrary.addBook(4, 15); // Book ID: 4, Category: 15
    myLibrary.addBook(5, 3); // Book ID: 5, Category: 3 (Warning should trigger here)
    myLibrary.addBook(6, 0); // Book ID: 6, Category: 0

    // Display all books in the library
    std::cout << "\nAll books in the library:\n";
    myLibrary.displayAllBooks();

    // Display available books in the library
    std::cout << "\nAvailable books in the library:\n";
    myLibrary.displayAvailableBooks();

    // Borrow a book by ID
    std::cout << "\nBorrowing Book ID 2:\n";
    if (myLibrary.borrowBook(2)) {
        std::cout << "Book ID 2 borrowed successfully.\n";
    } else {
        std::cout << "Failed to borrow Book ID 2.\n";
    }

    // Attempt to borrow the same book again
    std::cout << "\nAttempting to borrow Book ID 2 again:\n";
    if (myLibrary.borrowBook(2)) {
        std::cout << "Book ID 2 borrowed successfully.\n";
    } else {
        std::cout << "Failed to borrow Book ID 2.\n";
    }

    // Display borrowed books
    std::cout << "\nBorrowed books in the library:\n";
    myLibrary.displayBorrowedBooks();

    // Return a borrowed book by ID
    std::cout << "\nReturning Book ID 2:\n";
    if (myLibrary.returnBook(2)) {
        std::cout << "Book ID 2 returned successfully.\n";
    } else {
        std::cout << "Failed to return Book ID 2.\n";
    }

    // Display available books after returning a book
    std::cout << "\nAvailable books in the library after returning Book ID 2:\n";
    myLibrary.displayAvailableBooks();

    // Display the number of books in a specific category
    int categoryToCheck = 3;
    std::cout << "\nNumber of books in category " << categoryToCheck << ": "
              << myLibrary.countBooksInCategory(categoryToCheck) << std::endl;

    return 0;
}
```
Justify the choice of the data structures you chose to maintain the books in the library.

Provide the complexity of each operation in the library, and justify.

## Elementary data structures and their processing
### Exersize 1 - List Abstract Data Type (ADT) and Linked List
Implement the List ADT using a linked list that you implement from scratch. Use the code provided in Week 2 as a starting point, and write the main function that tests your implementation. Your linked list should support the following operations:
- Insertion at the beginning, middle (given a position), and end of the list.
- Deletion of an element from the beginning, middle (given a position), and end of the list.
- Check if a given element exists in the list.
- Traverse the list to print all elements.

Additionally, add a function to reverse the list and test it.

### Exersize 2 - Implementing a Stack Using an Array
Implement a stack using an ordinary array. The stack should be initialized with a size parameter that defines the initial size of the stack. The default constructor should create a stack with 100 elements as the initial size. When `push(...)` is called and the stack is full, a new array should be allocated with double the size. The content of the old array should be copied to the new one, and the old array should be deleted. Analyze the running time of the stack operations `push` and `pop` in terms of the number of elements `N` it stores.

### Exersize 3 - Queue Using Stack(s)
Implement a queue using stack(s). The implementation must be a template and use the Stack ADT presented in the course. There is no requirement for the implementation to be efficient, but you cannot use the internal structure of the stack nor an iterator for the stack.

### Exersize 4 - Hash Table Operations with Chaining, Linear Probing, and Quadratic Probing
Let `T` be a hash-table of size 7 with the hash function `h(x) = x mod 7`. Write down the entries of `T` after the keys 5, 28, 19, 15, 20, 33, 12, 17, 33, and 10 have been inserted using:
- Chaining
- Linear probing
- Quadratic probing

Also, calculate the load factor (λ) in the three cases.

### Exersize 5 - Implement a Set Using a Queue, List, or Stack ADT
Implement a Set using either a Queue, List, or Stack ADT as presented in the course. There is no requirement for the implementation to be efficient, but you cannot use the internal structure of the ADT nor an iterator for the ADT.

### Exersize 6 - Implement a Dictionary/Map Using STL Vector
Implement a Dictionary (or Map) using an STL vector. The elements of the vector (for the implementation) must be an STL `pair` representing the (key, value).

### Exersize 7 - Old Exam Question


## How to use this repository
1. Navigate to the folder corresponding to the desired exersize.
2. Each folder contains:
    - The solution code
    - A brief explanation and analysis in README.md
    - Any additional resources or data files used
3. Clone this repository using:

    git clone https://github.com/Miko58/Algorithms-and-Datatructures.git
