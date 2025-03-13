# Week 1: Introduction to C Programming (Solution)

## Overview
This week, we will cover the basics of writing and running a simple C program. By the end of this tutorial, you will:
- Understand the structure of a C program
- Learn how to use `printf()` for output
- Take user input using `scanf()`
- Work with basic data types and variables


## **1. Writing Your First C Program **
A C program consists of functions and statements enclosed in `{}`. Every program starts with a `main()` function. Below is a simple C program that prints "Hello, World!" to the screen.


### **Exercise 1 Solution:**
Modify the above program to print your name instead of "Hello, World!".
```c
#include <stdio.h>

int main() {
    printf("Hello, my name is John!\n");
    return 0;
}
```

---

## **2. Variables and Data Types**
Variables are used to store data. In C, you must declare a variable before using it.


### **Exercise 2 Solution:**
Create a program that declares variables for your name, age, and favorite number, then prints them.
```c
#include <stdio.h>

int main() {
    char name[] = "John";
    int age = 25;
    int favoriteNumber = 7;
    
    printf("Name: %s\n", name);
    printf("Age: %d\n", age);
    printf("Favorite Number: %d\n", favoriteNumber);
    
    return 0;
}
```

---


### **Exercise 3 Solution:**
Write a program that asks the user for their name and age, then prints a greeting message.
```c
#include <stdio.h>

int main() {
    char name[50];
    int age;
    
    printf("Enter your name: ");
    scanf("%s", name);
    printf("Enter your age: ");
    scanf("%d", &age);
    
    printf("Hello %s, you are %d years old.\n", name, age);
    
    return 0;
}
```

---

## **4. Assignment : Medical Checkup Program**
### **Task:** Write a C program that simulates a basic medical checkup.

### **Solution:**
```c
#include <stdio.h>

int main() {
    int age;
    char gender;
    float height, weight, temperature;
    char bloodType;
    
    printf("How old are you? ");
    scanf("%d", &age);
    printf("What is your gender (M/F)? ");
    scanf(" %c", &gender);
    printf("What is your height (in meters)? ");
    scanf("%f", &height);
    printf("What is your weight (in kilograms)? ");
    scanf("%f", &weight);
    printf("What is your blood type (A, B, O)? ");
    scanf(" %c", &bloodType);
    printf("What is your body temperature? ");
    scanf("%f", &temperature);
    
    printf("\nYou are %d years old and your gender is \"%c\".\n", age, gender);
    printf("Your height and weight are %.2f m, %.2f kg.\n", height, weight);
    printf("Your blood type is '%c'.\n", bloodType);
    printf("Your body temperature is %.2f degrees Celsius.\n", temperature);
    
    return 0;
}
```

---


## **Next Week:** Basic C Programming - Arithmetic Operations and Control Statements

Happy coding! 🚀
