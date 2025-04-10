# Week 5: Function

## **Overview**
Welcome to Week 5 of C programming! This week, we will explore functions that make your code simple and reusable. By the end of this tutorial, you will:
- Understand how to use functions
- Understand the difference between call by value and call by referecne 
- Understand how to use recursive functions.

### **Time Breakdown**
- **Introduction to a function**
- **Call by Value, Call by reference**
- **Recursion Fuction**
- **Exercises & Q/A**

---

## **1. Understanding the Function**
Function can make your code short and reusable

### **Example:** How to define and use functions
```c
#include<stdio.h>

int sum1(int a, int b) {
    return a + b;
}

int sum2(int a, int b);

void print_hello();

void main(){
    int num1,num2;

    printf("Please enter two numbers: ");
    scanf("%d %d", &num1, &num2);

    int sum_of_func1= sum1(num1, num2);

    printf("Sum1: %d\n", sum_of_func1);
    printf("Sum2: %d\n", sum2(num1, num2));

    print_hello();
}

int sum2(int a, int b) {
    return a + b;
}

void print_hello() {
    printf("Hello, World!\n");
}
```
### **Example Output:**
```
Please enter two numbers: 2 3
Sum1: 5
Sum2: 5
Hello, World!
```

---

## **2. Call by value, Call by reference **


### **Example:** Change numbers in the functions
```c
#include<stdio.h>

void I_cannot_change_num(int a, int b) {
    a=20;
    b=30;
    printf("Inside I_cannot_change_num: %d, %d\n", a, b);
}

void I_can_change_num(int *a, int *b) {
    *a=20;
    *b=30;
    printf("Inside I_can_change_num: %d, %d\n", *a, *b);
}
void main(){
    int num1,num2;
    printf("Please enter two numbers: ");
    scanf("%d %d", &num1, &num2);

    printf("=====================================\n");
    
    printf("Before I_cannot_change_num: %d, %d\n", num1, num2);
    I_cannot_change_num(num1, num2);
    printf("After I_cannot_change_num: %d, %d\n", num1, num2);

    printf("=====================================\n");

    printf("Before I_can_change_num: %d,%d\n", num1, num2);
    I_can_change_num(&num1, &num2);
    printf("After I_can_change_num: %d, %d\n", num1, num2);

    printf("=====================================\n");

}


```
### **Example Output:**
```
Please enter two numbers: 2 3
=====================================
Before I_cannot_change_num: 2, 3
Inside I_cannot_change_num: 20, 30
After I_cannot_change_num: 2, 3
=====================================
Before I_can_change_num: 2,3
Inside I_can_change_num: 20, 30
After I_can_change_num: 20, 30
=====================================
```

---

## **3. Recursive Function **
It is a different way of expressing loop

### **Example:** calculate the sum from 0 to n
```c
#include<stdio.h>

// similar to recurrence relation
int recursive_sum(int n){
    if(n==0){
        return 0;
    }
    return n + recursive_sum(n-1);
}

void main(){
    int num;
    printf("Please enter a number: ");
    scanf("%d",&num);
    int sum = recursive_sum(num);

    printf("sum is: %d \n",sum);
}


```
### **Example Output:**
```
Please enter a number: 5
sum is: 15
```



---

### **Exercise 1:** Make a swap function.
1. Input two numbers
2. change the value of each variable
3. print the result 
### **Example Output **
```
Please enter two numbers: 1 2
Before swap num: num1 = 1, num2 = 2
After swap num: num1 = 2, num2 = 1
```

### **Exercise 2: Make a program hadling 1-dimension matrix (array) ** 

You need to write these functinos:

- void set_matrix(int ary[], int len);  
-set the matrix in ascending order from 0 to len

- void reverse_matrix(int ary[], int len);  
-Reverse the order of the array  

- void print_matrix(int ary[], int len);  
-Print out all numbers in the array  

Hint* 
1. Size of ary varies everytime. Use a sizeof() function to get a length of array
2. Array is handled in the way of Call By Reference. You don't need to care about pointer!

### **Example Output (for `n = 9`):**
```
===== After set_matrix function =====
Matrix: 0 1 2 3 4 5 6 7 8 
===== After reverse_matrix function =====
Matrix: 8 7 6 5 4 3 2 1 0 
```

### **Exercise 3:** Write a program that calculate the Factorial using recursive function and for/while loop.**
You need to make 2 functions to calculate the fatorial of input number. One uses recursive function and the other one uses for or while loop.

### **Example Output **

```
Please enter a number: 5
Factorial of 5 using recursive function is 120
Factorial of 5 using for loop is 120
```

---

## **Bonus Challenge: Make a program that check if the string is palindrome or not (회문)**

Input could be entered both in lowercase and uppercase.

### **Example Output **
```
Please enter a string: Kayak
It is a palindrome!

Please enter a string: superman
It is not a palindrome

Please enter a string: exex
It is not a palindrome!

```

## **Bonus Challenge: Tower of Hanoi**
If you are interested in the recursive function, solve this problem!

Korean ver.
https://www.acmicpc.net/problem/11729

Englih ver.
https://leetcode.com/discuss/post/5272714/tower-of-hanoi-by-satvikmpatil-owd6/

---

## **Summary & Wrap-Up**
This week, we covered:
- Basic rules of functinos
- Defference between call by value and call by reference
- Recursive Function

### **Next Week:** 

Happy coding! 🚀
