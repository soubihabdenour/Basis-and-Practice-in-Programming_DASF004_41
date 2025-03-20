# Week 1: String, Overflow and Type Casting (Solution)

## Overview
Welcome to your second week of learning C programming! 
This week, we will cover the basics of writing and running a simple C program. By the end of this tutorial, you will:
- Overflow, Underflow
- Handling String with <string.h> 
- Type Casting/Conversion


## **1. Overflow **
Check the maximum and minimum values of other data types and see what happens when you go beyond the range of values


### **Exercise 1 Solution:**

```c
#include<stdio.h>
#define MAX 2147483647
#define MIN -2147483648

int main(){

    // int -2147483648 ~ 214783647
    printf("max +1 value: %d\n",MAX+1);
    printf("min -1 value: %d\n",MIN-1);

    // char -128 ~ 127
    char charMax=127;
    char charMin=-128;
    printf("max+1 value of char: %c\n",charMax+1);
    printf("min-1 value of char: %c\n",charMin-1);

    // float 1.0e-45f ~ 3.4e38f
    float floatmax=3.4e38f;
    float floatmin=1.0e-45f;
    printf("overflow value of float: %f\n", floatmax*2.0f);
    printf("underflow value of float: %f\n", floatmin/2.0f);

    return 0;
}
```

---

## **2. String**
Create a program that introduce yourself by getting input of your last name, first name and age.
*Please get input of your last, middle, first name seperately and print if by putting your name in one string variable.
(Output Ex. Hello, my name is JinseSeo and I am 24 years old. Nice to meet you!)


### **Exercise 2 Solution:**
Create a program that declares variables for your name, age, and favorite number, then prints them.

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

---


## **3. Typecasintg**

### **Exercise 3 Solution:**
Write a program that ask score of Math, English, Korean and print the average score to the second decimal place.
```c
#include<stdio.h>

int main(){
    int math;
    int english;
    int korean;
    printf("Please input your Math score: \n");
    scanf("%d",&math);
    printf("Please input your English score: \n");
    scanf("%d",&english);
    printf("Please input your Korean score: \n");
    scanf("%d",&korean);

    printf("Your average score is: %.2f\n",(float)(math+english+korean)/3);

  
}
```

---

## **4. Assignment : a personal information output program**
### **Task:** 
1. Ask the user for their last name, first name, age, gender (M/F), height (in cm) and weight (in kg).
2. Askt the user for their scores of Math, English, Korean and Art.
3. Print all this information using proper formatting.
   
### **Solution:**
```c
#include<stdio.h>
#include<string.h>


int main(){
    int age;
    char gender;
    float height;
    float weight;
    char Lastname[20];
    char Firstname[10];
    int Math;
    int English;
    int Korean;
    int Art;

    printf("Please type your Last name, First name, age, gender(M/F), height (cm), and weight(kg)\n");
    scanf("%s %s %d  %c %f %f", Lastname, Firstname, &age, &gender, &height, &weight);
    
    printf("Please input your scores of Math, English, Korean, and Art\n");
    scanf(" %d %d %d %d", &Math, &English, &Korean, &Art);
    
    printf("You are %s, %d years old and your gender is \"%c\"\n", strcat(Firstname,Lastname), age, gender);
    height /=100; // cm to meter
    printf("Your BMI is %f\n",weight/(height*height));
    printf("Your average score is %.2f\n",(Math+English+Korean+Art)/4.0);

}
```

---


## **Next Week:** Basic C Programming - Loops
Happy coding! 🚀
