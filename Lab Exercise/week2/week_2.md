# Week 2: String, Overflow and Type Casting

## Overview
Welcome to your second week of learning C programming! 
This week, we will cover the basics of writing and running a simple C program. By the end of this tutorial, you will:
- Overflow, Underflow
- Handling String with <string.h> 
- Type Casting/Conversion

---

## ** 1. Overflow (10 min)**
You should always be careful of the range of values

### **Example:** Overflow!
```c
#include<stdio.h>
#define MAX 214783647
#define MIN -2147483648
int main(){

    printf("max value: %d\n",MAX);
    printf("min value: %d\n",MIN);

    printf("max +1 value: %d\n",MAX+1);
    printf("min -1 value: %d\n",MIN-1);

}
```

### **Exercise 1 (5 min):**
Check the maximum and minimum values of other data types and see what happens when you go beyond the range of values

---

## **2. String (15 min)**
There are lots of functions in stirng.h that we can use when we deal with a string.

### **Functions in <string.h>**
<img src="./strings.JPG"/>

### **Example:** Using Variables
```c
#include <stdio.h>
#include <string.h>
int main() {
    char hello[20]="hello";
    char world[20]="world";
    printf("%s%s\n",hello,world);
    strcat(hello,world);
    printf("%s and length of hello string is: %d\n",hello,strlen(hello));
    return 0;
}
```

### **Exercise 2 (10 min):**
Create a program that introduce yourself by getting input of your last name, first name and age.
*Please get input of your last, middle, first name seperately and print if by putting your name in one string variable.
(Output Ex. Hello, my name is JinseSeo and I am 24 years old. Nice to meet you!)

---

## **3. Typecasintg  (20 min)**
You can converse data type 

### **Example:** User Input
```c
#include<stdio.h>

int main(){

    int a=100;
    int b=3;
    float c=3.33;
    printf("%d and %f \n", a/b, (float)a/b);

    printf("%d and %f\n", (int)c, c);
    
    c=a/b;
    a=3.33;
    printf("%f and %d\n", c, a);
    return 0;
}
```

### **Exercise 3 (10 min):**
Write a program that ask score of Math, English, Korean and print the average score to the second decimal place.

### **Example Output:**
Your average score is 54.25

---

## **4. Assignment (10 min) a personal information output program:
Inspired by previous assignments, let's create a structured task:

### **Task:** Write a C program that a personal information output program. Your program should:
1. Ask the user for their last name, first name, age, gender (M/F), height (in cm) and weight (in kg).
2. Askt the user for their scores of Math, English, Korean and Art.
3. Print all this information using proper formatting.

BMI = Kg/m^2

### **Example Output:**
```
You are JinseSeo, 24 years old and your gender is "M"
Your BMI is 21.749418
Your average score is 54.25
```

---

## **Summary & Wrap-Up (10 min)**
This week, we covered:
- Writing a simple C program
- Overflow, Underflow
- Utilizing String functions 
- Type casting/conversion

### **Next Week:** Basic C Programming - loops

Happy coding! 🚀
