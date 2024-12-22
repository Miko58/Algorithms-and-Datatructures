# Algorithms-and-Datatructures
Welcome to my repository where I solve and document exercises from the subject Algorithms & Data Structures. This repository will serve as a progressive record of my work, including code, explanations, and analyses for each exercise.

## Table of contents
- [Introduction](#introduction)
- [Exersizes](#exersizes)
    - [C++ Basics, Complexity, and ADT](#lesson1)
        - [Exersize 1](#exersize1)
        - [Exersize 2](#exersize2)
        - [Exersize 3](#exersize3)
        - [Exersize 4](#exersize4)
        - [Exersize 5](#exersize5)
- [How to use this repository](#howtouse)

## Introduction
This repository contains my solutions to various exercises as part of the course Algorithms and datastructures. Each exercise is designed to build understanding of key concepts through programming, analysis, and implementation. The solutions will be updated as new exercises are completed.

## Exersizes
## C++ Basics, Complexity, and ADT
### Exersize 1
Write a program that:

    1. Generates M random integers and stores them in vector.

    2. Generates another N random integers and counts how many of them are already present in the vector, using an iterator.

Estimate the worst-case complexity of the program.

### Exersize 2
What is the time complexity (Big-O) of myMethod?

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

## How to use this repository
    1. Navigate to the folder corresponding to the desired exersize.
    2. Each folder contains:
        - The solution code
        - A brief explanation and analysis in README.md
        - Any additional resources or data files used
    3. Clone this repository using:
        git clone https://github.com/yourusername/exercise-solutions.git
